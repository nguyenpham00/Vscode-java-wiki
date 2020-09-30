Under the hood, instead of `javac`, vscode-java uses [ECJ](https://stackoverflow.com/a/3061680/753170), a Java 15 compiler provided by [Eclipse JDT](https://www.eclipse.org/jdt/core/). It is used to compile against all other versions of Java. 
But the ECJ compiler [only supports the latest JDK release when it comes to preview features](https://bugs.eclipse.org/bugs/show_bug.cgi?id=549258#c15). It means that, since vscode-java 0.68.0, **preview features can not be enabled for projects compiling against Java 14 (or older)**, even if you configured the proper runtime. Those projects need to be updated to use Java 15 in vscode-java.

It's recommended you configure the `java.configuration.runtimes` preference in your user's settings.json:
```json
"java.configuration.runtimes": [
  {
    "name": "JavaSE-15",
    "path": "/path/to/jdk-15",
    "default": true
  },
],
```
Now, depending on the style of Java projects you use, there are different ways to enable preview features. 

# Standalone Java files
When you open standalone Java files (i.e. which have no Eclipse/Maven/Gradle settings), preview features are enabled by default, without warnings, if vscode-java was started with a JDK 15 or `JavaSE-15` is set to be the default in `java.configuration.runtimes`.

# Maven projects
Maven projects need to have the `--enable-preview` flag added to the maven-compiler-plugin configuration, in their pom.xml:
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>foo.bar</groupId>
  <artifactId>demo</artifactId>
  <version>0.0.1-SNAPSHOT</version>
 <properties>
  	<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
  </properties>
  <build>
    <plugins>
      <plugin>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.8.1</version>
        <configuration>
          <release>15</release>
          <compilerArgs>--enable-preview</compilerArgs>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>
```

# Eclipse projects

Eclipse projects need to add the the following preferences to `.settings/org.eclipse.jdt.core.prefs`:
```
eclipse.preferences.version=1
org.eclipse.jdt.core.compiler.codegen.inlineJsrBytecode=enabled
org.eclipse.jdt.core.compiler.codegen.targetPlatform=15
org.eclipse.jdt.core.compiler.codegen.unusedLocal=preserve
org.eclipse.jdt.core.compiler.compliance=15
org.eclipse.jdt.core.compiler.debug.lineNumber=generate
org.eclipse.jdt.core.compiler.debug.localVariable=generate
org.eclipse.jdt.core.compiler.debug.sourceFile=generate
org.eclipse.jdt.core.compiler.problem.assertIdentifier=error
org.eclipse.jdt.core.compiler.problem.enumIdentifier=error
org.eclipse.jdt.core.compiler.release=enabled
org.eclipse.jdt.core.compiler.source=15

org.eclipse.jdt.core.compiler.problem.enablePreviewFeatures=enabled
org.eclipse.jdt.core.compiler.problem.reportPreviewFeatures=ignore
```

# Gradle projects
**:warning: Gradle 6.7 minimum is required to build Java 15 projects.** 

Gradle projects can also maintain the same `.settings/org.eclipse.jdt.core.prefs` file. Alternatively, adding an `eclipse.jdt.file.withProperties` hook in build.gradle is possible, but requires the gradle `compileJdt` task *to be invoked manually*, as [Buildship](https://github.com/eclipse/buildship), the underlying Gradle integration tool, [doesn't invoke it](https://discuss.gradle.org/t/when-does-buildship-eclipse-customization-run/20781/2) :

```groovy
plugins {
    // Apply the java-library plugin to add support for Java Library
    id 'java-library'
    id 'eclipse'
}
sourceCompatibility = JavaVersion.VERSION_15
targetCompatibility = JavaVersion.VERSION_15

repositories {
     jcenter()
}
compileJava {
    options.compilerArgs += ["--enable-preview"]
}
compileTestJava {
    options.compilerArgs += ["--enable-preview"]
}
//Buildship doesn't use that hooks (https://discuss.gradle.org/t/when-does-buildship-eclipse-customization-run/20781/2)
//you need to run `gradle eclipse` separately
eclipse.jdt.file.withProperties { props ->
    props['org.eclipse.jdt.core.compiler.problem.enablePreviewFeatures']= 'enabled'
    props['org.eclipse.jdt.core.compiler.problem.reportPreviewFeatures']= 'ignore'
}

test {
    jvmArgs '--enable-preview'
}
```
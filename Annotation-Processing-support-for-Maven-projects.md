While `Annotation Processing` is not directly available from the jdt.ls back-end, it's still possible to have a mostly working dynamic Annotation Processing support for Maven projects, if you're ready to make some modifications to your pom.xml.

In this example, we'll configure a project to enable the [AutoValue](https://github.com/google/auto/) annotation processor. We'll basically be delegating the Annotation Processing role to the [apt-maven-plugin](https://github.com/querydsl/apt-maven-plugin), instead of maven-compiler-plugin.

First of all, we need to define the destination folder for generated code as a Maven property. Here, the code will be generated under the project's `target/generated-sources/java` folder:

```xml
  <properties>
    ...
    <generatedSources>${project.build.directory}/generated-sources/java</generatedSources>
  </properties>
```

Then, add the [auto-value](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.google.auto.value%22%20AND%20a%3A%22auto-value%22) dependency:

```xml
  <dependencies>
    ...
    <dependency>
      <groupId>com.google.auto.value</groupId>
      <artifactId>auto-value</artifactId>
      <version>1.5.3</version>
    </dependency>
  </dependencies>
```

Finally, we'll configure 3 maven plugins:
- maven-compiler-plugin: to disable default annotation processing
- apt-maven-plugin: to make `com.google.auto.value.processor.AutoValueProcessor` generate code under ${generatedSources}
- build-helper-maven-plugin: to add ${generatedSources} to the project's source classpath (a jdt.ls requirement, stock Maven doesn't need it actually):

```xml
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.7.0</version>
        <configuration>
          <!-- Need to disable default annotation processing since apt-maven-plugin takes over -->
          <compilerArgument>-proc:none</compilerArgument>
        </configuration>
      </plugin>
      <plugin>
        <groupId>com.mysema.maven</groupId>
        <artifactId>apt-maven-plugin</artifactId>
        <version>1.1.3</version>
        <executions>
          <execution>
            <goals>
              <goal>process</goal>
            </goals>
            <configuration>
              <outputDirectory>${generatedSources}</outputDirectory>
              <processors>
                <processor>com.google.auto.value.processor.AutoValueProcessor</processor>
              </processors>
            </configuration>
          </execution>
        </executions>
      </plugin>
      <plugin>
        <groupId>org.codehaus.mojo</groupId>
        <artifactId>build-helper-maven-plugin</artifactId>
        <version>3.0.0</version>
        <executions>
          <execution>
            <!-- Need to ensure the generated source folder is added to the project classpath, in jdt.ls -->
            <id>add-source</id>
            <phase>generate-sources</phase>
            <goals>
              <goal>add-source</goal>
            </goals>
            <configuration>
              <sources>
                <source>${generatedSources}</source>
              </sources>
            </configuration>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>
```

Now abstract classes annotated with @AutoValue will get their immutable implementation automatically generated after save:

<img width="1439" alt="AutoValue in vscode-java" src="https://user-images.githubusercontent.com/148698/35247062-f7c3a830-ff96-11e7-8456-54652547e216.png">


## Disclaimer

We have not extensively tested this solution. Running annotation processors each time, for each changed class, might cause some server slugginess or cause unexpected large memory consumption, and it might not scale for large-ish codebases.


vscode-java requires a [Java Development Kit](https://adoptopenjdk.net/) to run (NOT A JRE!). Since vscode-java 0.65.0, **Java 11 is the _minimum_ required version**. 

Setting the JDK
===============
The path to the Java Development Kit is searched in the following order:

- the `java.home` setting in VS Code settings (workspace then user settings)
- the `JDK_HOME` environment variable
- the `JAVA_HOME` environment variable
- on the current system path

Note: The path should end at the parent folder that contains the `bin` folder.
Example Path: **Use `/usr/lib/jvm/java-11`** if `bin` exists at `/usr/lib/jvm/java-11/bin`.

This JDK will be used to launch the Java Language Server. And by default, will be used to compile your projects.

If you need to compile your projects against a different JDK version, it's recommended you configure the `java.configuration.runtimes` property in your user settings, eg:
<a name="java.configuration.runtimes"></a>
```json
"java.configuration.runtimes": [
  {
    "name": "JavaSE-1.8",
    "path": "/path/to/jdk-8",
  },
  {
    "name": "JavaSE-11",
    "path": "/path/to/jdk-11",
  },
  {
    "name": "JavaSE-14",
    "path": "/path/to/jdk-14",
    "default": true
  },
]
```
The default runtime will be used when you open standalone Java files.

**⚠ Simply defining JavaSE-11 in `java.configuration.runtimes` is not enough for vscode-java to start, `java.home` (or any of its alternative environment variables) still need to point to a valid JDK 11 location.**

About the Java 11 requirement<a name="jdk11.requirement"></a>
============================
The Eclipse Platform has decided to require Java 11 as the minimum requirement for its September 2020 release. See https://www.eclipse.org/lists/eclipse-pmc/msg03821.html.

Because vscode-java depends on the[Eclipse JDT.LS](https://github.com/eclipse/eclipse.jdt.ls), the same requirement applies to vscode-java but on a more agressive timeline: vscode-java usually consumes JDT.LS builds that depend on bleeding edge JDT features, effectively shipping pre-release versions of Eclipse Platform/JDT. As of July 22nd, 2020, Java 11 is now required for **running** vscode-java.


### Do I need to migrate my projects to Java 11?

**NO you don't**! Well you should, be we're not here to judge. It is still possible to compile/run Java applications from Java 1.5 to 14, provided the proper [`java.configuration.runtimes`](#java.configuration.runtimes) are configured in the user's settings.json.

### My Gradle version does not support Java 11
You can set the `java.import.gradle.java.home` preference to specifically run the Gradle Daemon using a prior version of Java. However, this only works for Gradle >= 4.7. 

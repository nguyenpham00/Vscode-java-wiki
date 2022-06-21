vscode-java requires a [Java Development Kit](https://adoptium.net/) to run.

Setting the JDK
===============
- Platform Versions


Since vscode-java 1.2.0, it publishes platform specific versions to Microsoft VS Code marketplace. And the platform versions have JRE 17 embedded in Java extension for platforms such as `win32-x64`, `linux-x64`, `linux-arm64`, `darwin-x64`, `darwin-arm64`. The embedded JRE will be used to launch the Java Language Server by default. Users are only responsible for configuring **Project JDKs** to compile your Java projects. For example, if you are working on JDK 8, you only need to install JDK 8 and no longer need to install JDK 17 additionally.

However, if you want to use a different JDK to start the Java Language Server, you can use the setting `java.jdt.ls.java.home` to do so.

- Universal Version

For some other extension marketplaces (e.g. Open VSX), they haven't supported platform specific versions yet and will still use the universal version without embedded JRE.

In the universal version, the path to the Java Development Kit is searched in the following order:
- the `java.jdt.ls.java.home` setting in VS Code settings (workspace then user settings)
- (deprecated, use `java.jdt.ls.java.home` instead). the `java.home` setting in VS Code settings (workspace then user settings)
- the `JDK_HOME` environment variable
- the `JAVA_HOME` environment variable
- on the current system path

Note: The path should end at the parent folder that contains the `bin` folder.
Example Path: **Use `/usr/lib/jvm/java-17`** if `bin` exists at `/usr/lib/jvm/java-17/bin`.

This JDK will be used to launch the Java Language Server. by default, will be used to compile your projects.

- Project JDKs

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
    "name": "JavaSE-17",
    "path": "/path/to/jdk-17",
    "default": true
  },
]
```
The default runtime will be used when you open standalone Java files.


**⚠ For the universal version, simply defining JavaSE-17 in `java.configuration.runtimes` is not enough for vscode-java to start, `java.jdt.ls.java.home` (or any of its alternative environment variables) still needs to point to a valid JDK 17 location.**

About the Java 17 requirement<a name="jdk17.requirement"></a>
============================
This applies mainly to the universal version.

The m2e team has decided to require Java 17 as the minimum requirement for its September 2020 release. See https://github.com/eclipse-m2e/m2e-core/pull/740. We use m2e core components to provide Maven support for the Java language server [Eclipse JDT.LS](https://github.com/eclipse/eclipse.jdt.ls). This requires the entire language server to run on a minimum of Java 17.

Because vscode-java depends on the Eclipse JDT.LS, the same requirement applies to vscode-java but on a more agressive timeline: vscode-java usually consumes JDT.LS builds that depend on bleeding edge JDT features, effectively shipping pre-release versions of Eclipse Platform/JDT. As of Jun, 8, 2022, Java 17 is now required for **running** vscode-java.


### Do I need to migrate my projects to Java 17?

**NO you don't**! Well you should, be we're not here to judge. It is still possible to compile/run Java applications from Java 1.5 to 16, provided the proper [`java.configuration.runtimes`](#java.configuration.runtimes) are configured in the user's settings.json.

### My Gradle version does not support Java 17
You can set the `java.import.gradle.java.home` preference to specifically run the Gradle Daemon using a prior version of Java. However, this only works for Gradle >= 4.7. 

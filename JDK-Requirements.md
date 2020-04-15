vscode-java requires a [Java Development Kit](https://adoptopenjdk.net/) to run. Currently, Java 8 is the minimum required version, but [Java 11 will soon be required](#jdk11.requirement). 

Setting the JDK
===============
The path to the Java Development Kit is searched in the following order:

- the `java.home` setting in VS Code settings (workspace then user settings)
- the `JDK_HOME` environment variable
- the `JAVA_HOME` environment variable
- on the current system path

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

Upcoming Java 11 requirement<a name="jdk11.requirement"></a>
============================
The Eclipse Platform has decided to require Java 11 as the minimum requirement for its September 2020 release. See https://www.eclipse.org/lists/eclipse-pmc/msg03821.html.

Because vscode-java depends on the Eclipse JDT.LS server, that same requirement will apply to future vscode-java releases. But the timeline will be more aggressive: Indeed, vscode-java usually consumes JDT.LS builds that depend on bleeding edge JDT features, so effectively shipping pre-release versions of Eclipse Platform/JDT. Although it's not certain yet, there's a pretty good chance development of those bleeding edge bits will require Java 11 after the June 2020 of Eclipse.
Which means that Java 11 will be required as early as July 2020 for vscode-java.

Please note that it will still be possible to compile/run Java applications from Java 1.5 to 14, provided the proper [`java.configuration.runtimes`](java.configuration.runtimes) are configured in the user's settings.json.

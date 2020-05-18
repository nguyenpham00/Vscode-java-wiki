vscode-java provides partial Gradle support for Java projects, by embedding the [Eclipse Buildship project](https://github.com/eclipse/buildship).


# Known limitations:

- Android projects are not supported
- Kotlin build descriptors (`build.kts`) are not supported 
- ...


# Supported settings:

* `java.import.gradle.enabled` : Enable/disable the Gradle importer.
* `java.import.gradle.home`: setting for GRADLE_HOME.
* `java.import.gradle.arguments`: Arguments to pass to Gradle.
* `java.import.gradle.jvmArguments`: JVM arguments to pass to Gradle.
* `java.import.gradle.wrapper.enabled`: Enable/disable the Gradle wrapper.
* `java.import.gradle.version`: Gradle version, used if the gradle wrapper is missing or disabled.
* `java.import.gradle.offline.enabled`: Enable/disable the Gradle offline mode. Defaults to `false`.
* `java.import.gradle.user.home`: setting for GRADLE_USER_HOME.


# Suspicious gradle wrapper detection <a id="suspicious.wrapper" />

...

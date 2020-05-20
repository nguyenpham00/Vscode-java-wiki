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
When a project uses the gradle wrapper, if `"java.import.gradle.wrapper.enabled"=true` (the default), it will be automatically executed when opening VS Code. There is potential for a bad actor to replace the gradle-wrapper.jar with a malicious binary in a seemingly innocent repository, tricking users into automatically executing malware as soon as the folder is opened. 
In order to mitigate this issue, vscode-java performs integrity checks on any gradle wrapper used to run a build, similar to the [Github Action published by the Gradle team](https://docs.gradle.org/current/userguide/gradle_wrapper.html#wrapper_checksum_verification).   

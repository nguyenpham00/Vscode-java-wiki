vscode-java provides partial Gradle support for Java projects, by embedding the [Eclipse Buildship project](https://github.com/eclipse/buildship).


# Known limitations:

- Android projects are not supported
- Build file validation is limited as Gradle doesn't report exact location of errors
- Only Java files are compiled. Cross-language compilation is not supported.

# Supported settings:
* `java.import.gradle.enabled` : Enable/disable the Gradle importer.
* Specify the Gradle distribution used by the Java extension:
  * `java.import.gradle.wrapper.enabled`: Use Gradle from the 'gradle-wrapper.properties' file. Defaults to `true`.
  * `java.import.gradle.version`: Use Gradle from the specific version if the Gradle wrapper is missing or disabled.
  * `java.import.gradle.home`: Use Gradle from the specified local installation directory or GRADLE_HOME if the Gradle wrapper is missing or disabled and no 'java.import.gradle.version' is specified.
* `java.import.gradle.arguments`: Arguments to pass to Gradle.
* `java.import.gradle.jvmArguments`: JVM arguments to pass to Gradle.
* `java.import.gradle.offline.enabled`: Enable/disable the Gradle offline mode. Defaults to `false`.
* `java.import.gradle.user.home`: setting for GRADLE_USER_HOME.

# Suspicious gradle wrapper detection <a id="suspicious.wrapper" />
When a project uses the gradle wrapper, and `"java.import.gradle.wrapper.enabled"=true` (the default), it will be automatically executed when opening VS Code. 
There is potential for a bad actor to replace the gradle-wrapper.jar with a malicious binary in a seemingly innocent repository, tricking users into automatically executing malware as soon as the folder is opened.

In order to mitigate this issue, vscode-java performs integrity checks on any gradle wrapper used to run a build, similar to the [Github Action published by the Gradle team](https://docs.gradle.org/current/userguide/gradle_wrapper.html#wrapper_checksum_verification). If the wrapper's checksum doesn't match a known good checksum, a security warning is displayed (actually an error, so it stays visible):

 <img width="652" alt="Screen Shot 2020-05-20 at 11 29 20 PM" src="https://user-images.githubusercontent.com/148698/82499371-dc2db400-9af1-11ea-9c55-c721b3f8b8fb.png">

The link opens this page.

If you trust the wrapper to be executed, the application settings.jon will be updated like:

```json
"java.imports.gradle.wrapper.checksums": [
    {
        "sha256": "504b38a11c466aecb2f5c0b0d8ce0ed7ffa810bf70b9b7a599c570051be8fb4e",
        "allowed": true
    }
],
```
and the wrapper will be used.

If you don't trust it, `"allowed":"false"` will be stored. 

The default Gradle version embedded in Buildship will be used to build your project until the wrapper is explicitly trusted.
 

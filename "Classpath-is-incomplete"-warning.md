Whenever a java file is opened, that does not belong to a project (what we call a standalone Java file), vscode-java is unable to compute a proper classpath. It makes it useless to report compilation errors, as the UI would be filled with distracting red errors all over the file, like:

<img src="https://user-images.githubusercontent.com/148698/49049616-bd28bd00-f1ad-11e8-8122-598fb1aee14f.png">

Fortunately, vscode-java is still able to provide useful content-assist for base JDK classes, report syntax errors, compute class outline or allow code navigation. So, instead, the following warning is displayed:

<img width="555" src="https://user-images.githubusercontent.com/148698/37247458-ac9336c8-2480-11e8-85fa-f80ee427b268.png">

If you simply close the message, it will pop up next time a standalone java file will be opened. It’s possible to discard the message permanently, by clicking the `Don’t Show Again` option. 

Should you change your mind, it’s possible to modify that choice in VS Code’s user settings: The `java.errors.incompleteClasspath.severity` key specifies the severity of the message when the classpath is incomplete for a Java file. Supported values are `ignore`, `info`, `warning` and `error`.

You need to open a folder containing a pom.xml, build.gradle or at least default eclipse setting files, so that a complete classpath and project hierarchy can be set.
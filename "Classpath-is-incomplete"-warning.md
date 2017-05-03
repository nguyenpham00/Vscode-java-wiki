Whenever a java file is opened, that does not belong to a project (what we call a standalone Java file), vscode-java is unable to compute a proper classpath. It makes it useless to report compilation errors, as the UI would be filled with distracting red errors all over the file. But vscode-java is still able to provide useful content-assist for base JDK classes, report syntax errors, compute class outline or allow code navigation. So the following warning is displayed:

![](https://cloud.githubusercontent.com/assets/148698/25681391/2667ec7c-3022-11e7-9976-78ecbcdc4870.png)

If you simply close the message, it will pop up next time a standalone java file will be opened. It’s possible to discard the message permanently, by clicking the `Don’t show again` option. 

Should you change your mind, it’s possible to modify that choice in VS Code’s user settings: The `java.errors.incompleteClasspath.severity` key specifies the severity of the message when the classpath is incomplete for a Java file. Supported values are `ignore`, `info`, `warning` and `error`.

You need to open a folder containing a pom.xml, build.gradle or at least default eclipse setting files, so that a complete classpath and project hierarchy can be set.
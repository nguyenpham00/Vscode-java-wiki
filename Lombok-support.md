Starting with version 1.8, Java language server will automatically detect lombok dependencies from project classpath and load them into Java language server. This means that the lombok parameter you configured in `java.jdt.ls.vmargs` setting will be ignored by default. However, you could disable the setting `java.jdt.ls.lombokSupport.enabled` to turn off the built-in lombok support from Java language server, and manually configure your own lombok.jar in `java.jdt.ls.vmargs` setting (e.g. `"java.jdt.ls.vmargs": "-javaagent:/path/to/lombok.jar"`).

> Alternatively, there's a simpler method of enabling lombok support, via the **[Lombok Annotations Support for VS Code](https://marketplace.visualstudio.com/items?itemName=GabrielBB.vscode-lombok)** extension. 

This only works before vscode-java@1.7.0. Starting with version 1.8, if you still wants the Lombok Annotations Support for VS Code extension to work, you have to disable `java.jdt.ls.lombokSupport.enabled` first.

### Known issues
- Lombok versions prior to 1.16.21 prevent the formatter to work properly. Using the [lombok-edge (1.16.21) jar](https://projectlombok.org/download-edge) fixes this issue.
- Lombok is currently not fully compatible with Java 9 and 10


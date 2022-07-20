Starting with version 1.9, Java Language Server provides out-of-the-box Lombok support when you open a Lombok project in VS Code. By default, it uses the built-in Lombok version in the extension to support Lombok annotations in VS Code, or you can choose to use the project's Lombok version in VS Code.
![image](https://user-images.githubusercontent.com/14052197/179914082-9609dc61-6265-487d-8cd3-55e32704ea5d.png)


Since Java extension provides the built-in Lombok support, the lombok parameter you configured in `java.jdt.ls.vmargs` setting will be ignored by default. However, you could disable the setting `java.jdt.ls.lombokSupport.enabled` to turn off the built-in Lombok support from Java language server, and manually configure your own lombok.jar in `java.jdt.ls.vmargs` setting (e.g. `"java.jdt.ls.vmargs": "-javaagent:/path/to/lombok.jar"`).

> Alternatively, there's a simpler method of enabling lombok support, via the **[Lombok Annotations Support for VS Code](https://marketplace.visualstudio.com/items?itemName=GabrielBB.vscode-lombok)** extension. 

This only works before vscode-java@1.7.0. Starting with version 1.8, if you still wants the Lombok Annotations Support for VS Code extension to work, you have to disable `java.jdt.ls.lombokSupport.enabled` first.

### Known issues
- Lombok versions prior to 1.16.21 prevent the formatter to work properly. Using the [lombok-edge (1.16.21) jar](https://projectlombok.org/download-edge) fixes this issue.
- Lombok is currently not fully compatible with Java 9 and 10


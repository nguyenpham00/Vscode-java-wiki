In order to [Lombok support](https://projectlombok.org/), you need to edit the `java.jdt.ls.vmargs` setting in VS Code preferences:

```json
{
"java.jdt.ls.vmargs": "-javaagent:/path/to/lombok.jar -Xbootclasspath/a:/path/to/lombok.jar"
}
```
 
Paths containing spaces should be surrounded by (escaped) double quotes:

```json
{
"java.jdt.ls.vmargs": "-javaagent:\"/spaced path/to/lombok.jar\" -Xbootclasspath/a:\"/spaced path/to/lombok.jar\""
}
```
 
The `a:` prefix in the Xbootclasspath flag is critical, make sure it's added.

Alternatively, there's a simpler method of enabling lombok support, via the **[Lombok Annotations Support for VS Code](https://marketplace.visualstudio.com/items?itemName=GabrielBB.vscode-lombok)** extension.

### Known issues
- Lombok versions prior to 1.16.21 prevent the formatter to work properly. Using the [lombok-edge (1.16.21) jar](https://projectlombok.org/download-edge) fixes this issue.
- Lombok is currently not fully compatible with Java 9 and 10


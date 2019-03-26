You can contribute a VSCode Java Extension to enhance the existing VSCode Java features. Follow these steps to contribute an extension. 

## Server Bundle

## Authoring VSCode Extension
You can follow the tutorial [here](https://code.visualstudio.com/docs/extensions/overview) to start your own VSCode extension

## Modify package.json
Put a [server bundle](https://github.com/eclipse/eclipse.jdt.ls/wiki/Contribute-an-extension-bundle) together with your current VS Code extension (in a `./server` subfolder, for example), and add the following code snippet to the `contributes` section. Thus, the language server will discover your plugin for later usage.
```json
"contributes": {
    "javaExtensions": ["./server/my.java.plugin.jar"],
}
```

## Execute command
If you want to communicate with the plugin, add the following code in your extension:

```js
// This should be your command ("my.java.command") corresponding to your server plug-in extension point registration:
function sendMyCommandToJavaLanguageServer(arg) {
    return executeJavaLanguageServerCommand("my.java.command", arg);
}

// This is the VSCode Java command for language server protocol workspace/executeCommand: 
function executeJavaLanguageServerCommand(...rest) {
    return vscode.commands.executeCommand("java.execute.workspaceCommand", ...rest);
}
```
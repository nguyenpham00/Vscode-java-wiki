Here are a few instructions to help troubleshoot vscode-java.

## Enable logging
When the Java extension fails to work as expected, reading the logs is quite often a good way to understand what the problem is. The Java extension for VS Code is composed of 2 main parts, the client (VS Code) and the server (eclipse.jdt.ls), which means important information can be logged on both components. 

### Turn on message tracing between VS Code and the Java Language Server

It can be useful to trace the communications between VS Code and the Java Language Server. This can be achieved by enabling tracing in VS Code settings. The `java.trace.server` configuration can be set to `verbose` to provide full message logging in the Output view (select `Language support for Java` in the view menu). `java.trace.server` can take 3 values:

- `off` : no trace
- `messages` : logs message **types** exchanged between VS Code and the java server
- `verbose` : logs **JSON** messages exchanged between VS Code and the java server

### Get the vscode-java logs
When the Java extension fails to start, the first thing to look at is the VS Code console. 

- Open the command palette (`F1`)
- select `Developer: Toggle Developer Tools`

The chrome developer tools will open. In the console tab, you will find messages like: 

```
stderr: Mar 30, 2017 3:54:00 PM org.eclipse.lsp4j.jsonrpc.services.GenericEndpoint notify
WARNING: Unsupported notification method: $/setTraceNotification
vscode-icons is active!
Executing /Library/Java/JavaVirtualMachines/jdk-9.jdk/Contents/Home/bin/java -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=1044 --add-modules=ALL-SYSTEM 
--add-opens java.base/java.util=ALL-UNNAMED --add-opens java.base/java.lang=ALL-UNNAMED 
-Declipse.application=org.eclipse.jdt.ls.core.id1 -Dosgi.bundles.defaultStartLevel=4 
-Declipse.product=org.eclipse.jdt.ls.core.product -Dlog.protocol=true -Dlog.level=ALL 
-noverify -Xmx1G -make.it.crash -jar /Users/fbricon/Dev/projects/vscode-java/server/plugins/org.eclipse.equinox.launcher_1.4.0.v20161219-1356.jar 
-configuration /Users/fbricon/Dev/projects/vscode-java/server/config_mac 
-data /Users/fbricon/Library/Application Support/Code/User/workspaceStorage/bdea6df99b92680f795ba5759e96cfc4/redhat.java/jdt_ws
View server logs at /Users/fbricon/Library/Application Support/Code/User/workspaceStorage/bdea6df99b92680f795ba5759e96cfc4/redhat.java/jdt_ws/.metadata/plugins/.log
stderr: Unrecognized option: -make.it.crash
Error: Could not create the Java Virtual Machine.
Error: A fatal exception has occurred. Program will exit.
```

### Get the Java Language Server's workspace logs
The Java Language Server log file might also contain other informations. To access it:

- Open the command palette (`F1`)
- select `Java: Open Java Language Server log file` 

It will open the Java Language Server log file in a new tab.

## Clean the workspace directory
In some occasions, deleting the Java Language Server workspace directory is helpful to go back to a clean slate.
Generally speaking, on the different platforms, the VS Code user workspace storage area can be found under these locations :

- Windows : `%APPDATA%\Code[ - Variant]\User\workspaceStorage\`
- MacOS : `$HOME/Library/Application Support/Code[ - Variant]/User/workspaceStorage/`
- Linux : `$HOME/.config/Code[ - Variant]/User/workspaceStorage/`

**New in 0.33.0**

You can clean the workspace directory in the following way:

- Open the command palette (F1)
- select Java: Clean the Java language server workspace
- click Restart and delete




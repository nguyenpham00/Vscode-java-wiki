Here are a few instructions to help troubleshoot vscode-java.

## Enable logging

### Turn on message tracing between VS Code and the Java Language Server

### Get the vscode-java logs

### Get the Java Language Server's workspace logs

## Clean the workspace directory
In some occasions, deleting the Java Language Server workspace directory is helpful to go back to a clean slate.
If you open the vscode-java logs, you'll see something like:

```
Executing /Library/Java/JavaVirtualMachines/jdk-9.jdk/Contents/Home/bin/java -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=1044 --add-modules=ALL-SYSTEM 
--add-opens java.base/java.util=ALL-UNNAMED --add-opens java.base/java.lang=ALL-UNNAMED 
-Declipse.application=org.eclipse.jdt.ls.core.id1 -Dosgi.bundles.defaultStartLevel=4 -Declipse.product=org.eclipse.jdt.ls.core.product -Dlog.protocol=true -Dlog.level=ALL 
-noverify -Xmx1G -jar /Users/fbricon/Dev/projects/vscode-java/server/plugins/org.eclipse.equinox.launcher_1.4.0.v20161219-1356.jar 
-configuration /Users/fbricon/Dev/projects/vscode-java/server/config_mac 
-data /Users/fbricon/Library/Application Support/Code/User/workspaceStorage/bdea6df99b92680f795ba5759e96cfc4/redhat.java/jdt_ws
```

The `-data` option here gives you the workspace directory, that is `/Users/coolusername/Library/Application Support/Code/User/workspaceStorage/bdea6df99b92680f795ba5759e96cfc4/redhat.java/jdt_ws`

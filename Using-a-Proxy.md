When using the Java extension behind a corporate proxy, you might need to let the Java Language server know how to connect to the Internet, in order to download build runtimes, java dependencies and their sources through that proxy. 
This is done by configuring the `java.jdt.ls.vmargs` setting in VS Code preferences (all on one line):

```json
{
"java.jdt.ls.vmargs": "-Dhttp.proxyHost=webproxy.corp.net -Dhttp.proxyPort=proxyport -Dhttp.proxyUser=user -Dhttp.proxyPassword=password -Dhttps.proxyHost=webproxy.corp.net -Dhttps.proxyPort=proxyport -Dhttps.proxyUser=user -Dhttps.proxyPassword=password"
}
```

You could, in theory, set the proxy settings in VS Code's workspace preferences, but you certainly don't want these sensible settings to be made publicly available. So the user preferences are the preferred choice most of the time. 
However, you need to be aware workspace preferences will override any user preferences, so for instance, memory settings defined in the workspace preferences's `java.jdt.ls.vmargs` would replace proxy settings set the user preferences. 


Set the following property: 
```
"java.settings.url": "/home/<your_name>/settings.prefs",
```

The property can point to an URL or a local file path.

You can also define the settings preferences in your project's [`.settings/org.eclipse.jdt.core.prefs`](https://gist.github.com/snjeza/e59f0ce031f237a9d0f4f2aec404a4bb). It will override global settings.

The best way to create those preferences is to edit it in Eclipse.

In Eclipse, right-click on your project, open `Window` >`Preferences` > `Java Code Style` > `Formatter`,  `Window` >`Preferences` > `Java` > `Code Style` > `Organize Imports`, `Window` >`Preferences` > `Java` > `Compiler` > `Errors/Warnings` and create a new settings file :


The preferences file can be exported using `File` > `Export` > `General` > `Preferences`. You can use this file to define `java.settings.url`.
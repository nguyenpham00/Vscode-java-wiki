In order to use the formatter, you need an Eclipse formatter file like https://raw.githubusercontent.com/google/styleguide/gh-pages/eclipse-java-google-style.xml.

Set the following property: 
```
"java.format.settings.url": "https://raw.githubusercontent.com/google/styleguide/gh-pages/eclipse-java-google-style.xml",
```

The property can point to an URL or a local file path.
If the formatter xml file contains more profiles you will be able to set a profile name as:

```
"java.format.settings.profile": "GoogleStyle",
```

You can also define the formatting preferences in your project's [`.settings/org.eclipse.jdt.core.prefs`](https://gist.github.com/fbricon/30c5971f7e492c8a74ca2b2d7a7bb966). It will override global formatting settings.

Since this is rather tedious, the best way to edit those preferences is to open your project in Eclipse and set the formatting preferences for your project there. 

In Eclipse, right-click on your project, open `Properties` > `Java Code Style` > `Formatter` and create a new formatting profile :
<img width="701" alt="screen shot 2017-08-24 at 2 41 36 pm" src="https://user-images.githubusercontent.com/148698/29683245-a769006a-88db-11e7-87f3-f8d69afd3d9d.png">

Once you save it, `.settings/org.eclipse.jdt.core.prefs` will be updated. This file will need to be copied to all your other projects in the same workspace. 

No it's not an ideal solution, but it should be done only once, unless you regularly change your formatter settings.
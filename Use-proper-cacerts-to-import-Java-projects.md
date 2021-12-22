For some enterprise users, they use custom certificates to override the JDK‘s own cacerts (`<JAVA_HOME>/lib/security/cacerts`), so using the JDK on their machine can build and run their Java application well.

Starting with 1.2.0, Java extension will use an embedded JRE 17 to launch Java extension and import user's Java projects. If user's Maven projects use dependencies from a custom Nexus HTTPS server, Java extension will probably throw PKIX errors.

`
PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target and 'parent.relativePath' points at wrong local POM
`

To mitigate it, users have two approaches to add their custom cert to the JRE runtime.
- Use [keytool](https://docs.oracle.com/en/java/javase/17/docs/specs/man/keytool.html) to import the custom cert to the existing cacerts of the embedded JRE.

   Usually, the location of the embedded JRE cacerts is like `.../.vscode/extensions/redhat.java-1.2.0/jre/17.0.1-macosx-x86_64/lib/security/cacerts`. And you have to update it again if a new redhat.java extension is released.
- (**Recommended**) Use jvm arguments to specify a custom truststore and password.

   Go to user setting `"java.jdt.ls.vmargs"`, and append `"-Djavax.net.ssl.trustStore=custompath/cacerts -Djavax.net.ssl.trustStorePassword=changeit"` to it.

Pls note that, the solution above is just used to solve the certs for project importing. If users want to run or debug their application with a custom cert, they must either add `-Djavax.net.ssl.trustStore` and `-Djavax.net.ssl.trustStorePassword` to `java.debug.settings.vmArgs`, or override `<JAVA_HOME>/lib/security/cacerts` of the installed JDK with their custom certs.

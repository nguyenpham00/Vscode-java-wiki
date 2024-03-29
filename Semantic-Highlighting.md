[Semantic Highlighting](https://code.visualstudio.com/updates/v1_43#_typescript-semantic-highlighting) is a new feature enabled since VS Code 1.43. Color themes can now write [rules](https://code.visualstudio.com/updates/v1_44#_theme-support-for-semantic-tokens) to color semantic tokens reported by this extension. If current color theme does not provide any, you can define your own rules in user settings, e.g.
```jsonc
"editor.semanticTokenColorCustomizations": {
    "rules": {
        "class": "#ff0000", // change color for tokens of type 'class'
        "*.constructor": "#f7c090", // change color for tokens of type '*.constructor'
        "parameter":{
            "foreground": "#00ff0d" // change color for tokens of type 'parameter'
        },
        "*.static":{
            "fontStyle": "italic" // all tokens with modifier 'static' should be of italic style
        },
        "*.readonly":{
            "fontStyle": "bold" // all tokens with modifier 'final' should be of bold style
        }
    }
}
```
More details in [Semantic Highlighting Wiki Page (Token Styling)](https://github.com/microsoft/vscode/wiki/Semantic-Highlighting-Overview#token-styling).

Semantic Highlighting is controlled by the `java.semanticHighlighting.enabled` preference. When enabled, it fixes numerous syntax highlighting issues with the default Java Textmate grammar. However, you might experience different small issues, particularly a delay when it kicks in, as it needs to be computed by the Java Language server, when opening a new file or when typing.

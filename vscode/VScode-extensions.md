# VSCode Extensions

- **Auto Close Tag:** Jun Han
- **Better Comments:** Aaron Bond
- **Color Highlight:** Sergii Naumov
- **CSS Peek:** Pranay Prakash
- **ES7 React Snippets:** dsznajder
- **ESLint:** Dirk Baeumer
- **GlassIt-VSC:** hikarin522
- **GraphQL:** Prisma
- **Path Intellisense:** Christian Kohler
- **Prettier:** Esben Petersen
- **Rainbow Brakets:** 2gua
- **Snazzy Operator:** Aaron Thomas
- **VS Color Picker:** lihui
- **vscode-icons:** VScode Icons Team
- **vscode-styled-components:** Julien Poissonnier
- **CodeMetrics**
- **GitLens**
- **Snazzy Operator**
- **Markdown Preview Enhanced**
- **CSS Peek**


# Settings
```js
{
    "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
    "glassit.alpha": 255,
    "workbench.colorTheme": "Snazzy Operator",
    "workbench.iconTheme": "vscode-icons",
    "editor.fontFamily": "Operator Mono Lig",
    "editor.fontLigatures": true,
    "terminal.integrated.fontFamily": "monospace",
    "editor.fontSize": 18,
    "editor.formatOnSave": true,
    "emojisense.languages": {
        "markdown": true,
        "git-commit": true,
        "plaintext": true,
        "json": true,
        "javascript": true,
        "javascriptreact": true,
        "html": true,
        "css": true,
        "scss": true,
        "sass": true
    }
}
```

If you have any issue with Import Cost Extension then use the following configuration:

```json
{
  // File extensions to be parsed by the Typescript parser
  "importCost.typescriptExtensions": ["\\.tsx?$"],

  // File extensions to be parsed by the Javascript parser
  "importCost.javascriptExtensions": ["\\.jsx?$"],
  // Which bundle size to display
  "importCost.bundleSizeDecoration": "both",

  // Display the 'calculating' decoration
  "importCost.showCalculatingDecoration": true,

  // Print debug messages in output channel
  "importCost.debug": true,
  "importCost.timeout": 432000
}
```

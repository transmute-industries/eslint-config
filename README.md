# @transmute/eslint-config

```
npm i @transmute/eslint-config --save-dev
```

This config setup is meant to be used with VSCode.

Copy `./setup-files` to working directory, next to package.json.

### Manual Setup

Create `.vscode/settings.json` :

```
{
  "editor.formatOnSave": true,
  "javascript.format.enable": false,
  "javascript.referencesCodeLens.enabled": true,
  "editor.rulers": [80],
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.codeLens": false
}

```

Create `.vscode/extensions.json` :

```
{
  // See http://go.microsoft.com/fwlink/?LinkId=827846
  // for the documentation about the extensions.json format
  "recommendations": [
    // Extension identifier format: ${publisher}.${name}. Example: vscode.csharp
    "esbenp.prettier-vscode",
    "codezombiech.gitignore",
    "EditorConfig.EditorConfig"
  ]
}
```

Create `prettier.config.js` :

```
// eslint-disable-next-line
module.exports = require('@transmute/eslint-config/prettier.config.js');
```

Create `.eslintrc` :

```
{
  "extends": ["@transmute/eslint-config/eslint.config.react.json"]
}
```

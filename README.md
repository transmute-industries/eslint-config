# @transmute/eslint-config

```
npm i @transmute/eslint-config --save-dev
```

This config setup is meant to be used with VSCode.

Copy `./setup-files` to working directory, next to package.json.

### Note regarding dependencies

This eslint configuration depends on the following libraries:
- "eslint"
- "eslint-config-airbnb-base"
- "eslint-config-prettier"
- "eslint-plugin-import"
- "eslint-plugin-jest"
- "eslint-plugin-node"
- "eslint-plugin-prettier"
- "eslint-plugin-react"
- "eslint-plugin-security"
- "prettier"

It is tempting to add those as dependencies in `package.json` so that one can just run `npm i --save-dev @transmute/eslint-config` to setup everything in one command, however this does not work.

Indeed some `eslint-config-*` and `eslint-plugin-*` dependencies require a specific version of `eslint` and `prettier` to run, and the setup will break if another dependency in your app requires a different version of `eslint`

Therefore, when you install this library, it is your job to also install all those dependencies and figure which combination of versions work with the other dependencies in your application.

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
module.exports = require('@transmute/eslint-config/prettier.config.json');
```

Create `.eslintrc` :

```
{
  "extends": ["@transmute/eslint-config/eslint.config.react.json"]
}
```

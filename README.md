<div align='center'>
<br>
<img src="./assets/selene.ico" width="100" >
<br>

 <h1>Selene-IDE</h1>

 <div id="badges" align="center">

[![electron](https://github.com/DukeNgn/selene-ide/workflows/electron/badge.svg?branch=master)](https://github.com/DukeNgn/selene-ide/actions?query=branch%3Amaster+workflow%3Aelectron)
[![browser](https://github.com/DukeNgn/selene-ide/workflows/browser/badge.svg?branch=master)](https://github.com/DukeNgn/selene-ide/actions?query=branch%3Amaster+workflow%3Abrowser)

 </div>

 </div>

## Description

Selene is my own customized IDE, based on project [Eclipse Theia](https://github.com/eclipse-theia/theia). One can see this project as an example to illustrate how to create their own Theia-based IDE and tweak it to their needs.

<div align="center">
    <img src="./assets/preview.png" width="700">
</div>

- [Main Theia Repository](https://github.com/eclipse-theia/theia)
- [Visit the Theia website](http://www.theia-ide.org) for more [documentation](http://www.theia-ide.org/doc).

## What's included?

- In addition to the built-in extensions, Selene contains other extensions from open-vsx that I usually use. The full list is in the `package.json` for both `browser` and `electron` target.
- See something you don't like? Delete it from the list of plugins in `package.json` and rebuild the app.

## [Install Selene from release](https://github.com/DukeNgn/selene-ide/releases)

## Build

```
yarn
```

## Electron version

```
yarn build:electron
```

#### Start the electron app

```
yarn start:electron
```

#### Package the application

```
yarn package:electron
```

#### Package a preview version of the application

```
yarn package:preview:electron
```

#### Rebuild Electron version

```
yarn rebuild:electron
```

## Browser version

```
yarn build:browser
```

#### Start the browser version

```
yarn start:browser
```

#### Rebuild Browser version

```
yarn rebuild:browser
```

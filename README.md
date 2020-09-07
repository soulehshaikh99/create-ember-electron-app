<div align="center">
<img alt="Electron Ember Crossover Banner" src="https://raw.githubusercontent.com/soulehshaikh99/assets/master/create-electron-framework-app/readme/svg/Electron_Ember.svg" width="580" />
</div>
<br />
The boilerplate code to get started creating Cross-platform Desktop Apps with Electron and Ember as front-end technology.
<br />
<br />
<div align="center">

[![forthebadge](http://forthebadge.com/images/badges/built-by-developers.svg)](http://forthebadge.com)&nbsp;&nbsp;&nbsp;&nbsp;[![forthebadge](http://forthebadge.com/images/badges/makes-people-smile.svg)](http://forthebadge.com)<br />

[![forthebadge](http://forthebadge.com/images/badges/uses-html.svg)](http://forthebadge.com)&nbsp;&nbsp;&nbsp;[![forthebadge](http://forthebadge.com/images/badges/uses-css.svg)](http://forthebadge.com)&nbsp;&nbsp;&nbsp;[![forthebadge](http://forthebadge.com/images/badges/uses-js.svg)](http://forthebadge.com)

[![js-standard-style](https://cdn.rawgit.com/feross/standard/master/badge.svg)](https://github.com/feross/standard)

</div>

## ✒️ Overview

The aim of this project is to provide Web Developers using `ember` the power to create cross-platform desktop apps using `electron`.

#### 🧐 What packages does the project use?

**`electron`** enables you to create desktop applications with pure JavaScript by providing a runtime with rich native (operating system) APIs. You could see it as a variant of the Node.js runtime that is focused on desktop applications instead of web servers.

**`electron-builder`** is used as a complete solution to package and build a ready for distribution (supports Numerous target formats) Electron app with "auto update" support out of the box.

**`electron-serve`** is used for Static file serving for Electron apps.

**`ember`** is a framework for ambitious web developers. Ember.js is a productive, battle-tested JavaScript framework for building modern web applications. It includes everything you need to build rich UIs that work on any device. Ember’s out-of-the-box experience has everything you need to start building on day one and keep shipping for years. Ember is built on the Glimmer rendering engine, one of the fastest rendering technologies on the market today, thanks to the way it compiles templates down to a highly-performant virtual machine. Due to our holistic performance approach, performance upgrades are often free with version upgrades— no extra work necessary!

**`concurrently`** is used to run multiple commands concurrently.

**`wait-on`** is used as it can wait for sockets, and http(s) resources to become available.
<br />

## 🚀 Getting Started

**Note:** If you wish to use npm over yarn then modify `package.json` by replacing `yarn` with `npm` in `electron-dev` and `preelectron-pack` scripts.
But I strongly recommend using <em>yarn</em> as it is a better choice when compared to <em>npm</em>.

### 🤓 Use this boilerplate

```bash
# Clone the Project

# Use degit scaffolding tool
$ npx degit soulehshaikh99/create-ember-electron-app create-ember-electron-app
# or GitHub CLI Users
$ gh repo clone https://github.com/soulehshaikh99/create-ember-electron-app.git
# or Normal Git Users
$ git clone https://github.com/soulehshaikh99/create-ember-electron-app.git

# Switch location to the cloned directory
$ cd create-ember-electron-app

# Install dependencies
$ yarn # or npm install

# Run your app
$ yarn electron-dev # or npm run electron-dev

# Package Your App
$ yarn electron-pack # or npm run electron-pack
```

### 💫 Create this boilerplate from scratch (Manual Setup)

#### 1) Start by cloning `ember-learn/super-rentals` project as ember template project

```bash
# Use degit scaffolding tool
$ npx degit ember-learn/super-rentals create-ember-electron-app
# or GitHub CLI Users
$ gh repo clone https://github.com/ember-learn/super-rentals.git
# or Normal Git Users
$ git clone https://github.com/ember-learn/super-rentals.git
```

#### 2) Switch to project directory

```bash
$ cd create-ember-electron-app
```

#### 3) Install Dependencies

```bash
$ yarn # npm install
```

#### 4) Install Development Dependencies

```bash
$ yarn add --dev electron electron-builder wait-on concurrently
# npm i -D electron electron-builder wait-on concurrently
```

#### 5) Install Production Dependency

```bash
$ yarn add electron-serve # or npm i electron-serve
```

#### 6) Your dependencies should look something like this

```json
"dependencies": {
  "electron-serve": "^1.0.0"
},
"devDependencies": {
  "@ember/optional-features": "^2.0.0",
  "@glimmer/component": "^1.0.1",
  "@glimmer/tracking": "^1.0.1",
  "babel-eslint": "^10.1.0",
  "broccoli-asset-rev": "^3.0.0",
  "concurrently": "^5.3.0",
  "electron": "^10.1.1",
  "electron-builder": "^22.8.0",
  "ember-auto-import": "^1.6.0",
  "ember-cli": "~3.21.0",
  "ember-cli-app-version": "^3.2.0",
  "ember-cli-babel": "^7.22.1",
  "ember-cli-dependency-checker": "^3.2.0",
  "ember-cli-htmlbars": "^5.3.1",
  "ember-cli-inject-live-reload": "^2.0.2",
  "ember-cli-sri": "^2.1.1",
  "ember-cli-uglify": "^3.0.0",
  "ember-data": "~3.21.0",
  "ember-export-application-global": "^2.0.1",
  "ember-fetch": "^8.0.2",
  "ember-load-initializers": "^2.1.1",
  "ember-maybe-import-regenerator": "^0.1.6",
  "ember-qunit": "^4.6.0",
  "ember-resolver": "^8.0.2",
  "ember-source": "~3.21.1",
  "ember-template-lint": "^2.11.0",
  "ember-welcome-page": "^4.0.0",
  "eslint": "^7.8.0",
  "eslint-plugin-ember": "^8.13.0",
  "eslint-plugin-node": "^11.1.0",
  "loader.js": "^4.7.0",
  "npm-run-all": "^4.1.5",
  "qunit-dom": "^1.4.0",
  "wait-on": "^5.2.0"
}
```

#### 7) Download the app icon

[favicon.png](https://raw.githubusercontent.com/soulehshaikh99/assets/master/framework-icons/ember/favicon.png) and place it in the public/assets/images directory.

#### 8) Add `output-path` configuration in `.ember-cli`

```bash
# .ember-cli
# This will make sure that the electron-builder and ember-cli
# has seperate directories for output.
{
  ..
  "output-path": "build"
}
```

#### 9) Create main.js file (serves as entry point for Electron App's Main Process)

```bash
# Windows Users
$ fsutil file createnew main.js 0
# notepad main.js

# Linux and macOS Users
$ touch main.js
```

#### 10) Paste the below code in main.js file

```js
// Modules to control application life and create native browser window
const { app, BrowserWindow, dialog } = require('electron');
const path = require('path');
const serve = require('electron-serve');
const loadURL = serve({ directory: 'build' });

// Keep a global reference of the window object, if you don't, the window will
// be closed automatically when the JavaScript object is garbage collected.
let mainWindow;

function isDev() {
    return !app.isPackaged;
}

function createWindow() {
    // Create the browser window.
    mainWindow = new BrowserWindow({
        width: 800,
        height: 600,
        webPreferences: {
            nodeIntegration: true
        },
        // Use this in development mode.
        icon: isDev() ? path.join(process.cwd(), 'public/assets/images/favicon.png') : path.join(__dirname, 'assets/images/favicon.png'),
        // Use this in production mode.
        // icon: path.join(__dirname, 'assets/images/favicon.png'),
        show: false
    });

    // This block of code is intended for development purpose only.
    // Delete this entire block of code when you are ready to package the application.
    if (isDev()) {
        mainWindow.loadURL('http://localhost:4200/');
    } else {
        loadURL(mainWindow);
    }
    
    // Uncomment the following line of code when app is ready to be packaged.
    // loadURL(mainWindow);

    // Open the DevTools and also disable Electron Security Warning.
    // process.env['ELECTRON_DISABLE_SECURITY_WARNINGS'] = true;
    // mainWindow.webContents.openDevTools();

    // Emitted when the window is closed.
    mainWindow.on('closed', function () {
        // Dereference the window object, usually you would store windows
        // in an array if your app supports multi windows, this is the time
        // when you should delete the corresponding element.
        mainWindow = null
    });

    // Emitted when the window is ready to be shown
    // This helps in showing the window gracefully.
    mainWindow.once('ready-to-show', () => {
        mainWindow.show()
    });
}

// This method will be called when Electron has finished
// initialization and is ready to create browser windows.
// Some APIs can only be used after this event occurs.
app.on('ready', createWindow);

// Quit when all windows are closed.
app.on('window-all-closed', function () {
    // On macOS it is common for applications and their menu bar
    // to stay active until the user quits explicitly with Cmd + Q
    if (process.platform !== 'darwin') app.quit()
});

app.on('activate', function () {
    // On macOS it's common to re-create a window in the app when the
    // dock icon is clicked and there are no other windows open.
    if (mainWindow === null) createWindow()
});
// In this file you can include the rest of your app's specific main process
// code. You can also put them in separate files and require them here.
```

#### 11) Update the script section of `package.json`

```bash
# Add this scripts
"electron": "wait-on http://localhost:4200 && electron .",
"electron-dev": "concurrently \"yarn start\" \"yarn electron\"",
"preelectron-pack": "yarn build",
"electron-pack": "electron-builder"

# You should end up with something similar
"scripts": {
  "build": "ember build --environment=production",
  "lint": "npm-run-all --aggregate-output --continue-on-error --parallel lint:*",
  "lint:hbs": "ember-template-lint .",
  "lint:js": "eslint .",
  "start": "ember serve",
  "test": "npm-run-all lint:* test:*",
  "test:ember": "ember test",
  "electron": "wait-on http://localhost:4200 && electron .",
  "electron-dev": "concurrently \"yarn start\" \"yarn electron\"",
  "preelectron-pack": "yarn build",
  "electron-pack": "electron-builder"
}
```

#### 12) Delete `directory` configuration from `package.json`

**Note:** delete this entry from package.json as it collides with electron-builder configuration.

```bash
"directories": {
  "doc": "doc",
  "test": "tests"
}
```

#### 13) Add the following configuration in `package.json`

**Note:** build configuration is used by electron-builder, modify it if you wish to add more packaging and native distribution options for different OS Platforms.

```bash
"name": "create-ember-electron-app", # default is super-rentals
"main": "main.js",  # Application Entry Point, please verify entry point is set to main.js
"build": {
  "icon": "public/assets/images/favicon.png",
  "productName": "Ember and Electron App",
  "files": [
    "build/**/*",
    "main.js"
  ],
  "win": {},  # Windows Specific Configuration
  "linux": {},  # Linux Specific Configuration
  "mac": {}  # MacOs Specific Configuration
}
```

#### 13) Test drive your app

```bash
# Run your app
$ yarn electron-dev # or npm run electron-dev

# Package Your App
$ yarn electron-pack # or npm run electron-pack
```

### 💯 Result

<div align="center">
<img alt="Electron Ember Window Screeenshot" src="https://raw.githubusercontent.com/soulehshaikh99/assets/master/create-electron-framework-app/readme/png/create-ember-electron-app.png" />
</div>

<h3>😍 Made with ❤️ from Souleh</h3>
 
[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com)
<br/>

<h3>📋 License: </h3>
Licensed under the <a href="https://github.com/soulehshaikh99/create-ember-electron-app/blob/master/LICENSE">MIT License</a>.
# Bug in VS code typescript debugging

### Workspace
In VS Code Open the workspace folder containing :
* `.vscode` launch configuration
* `app` contains the application
* `lib` contains some shared utilities deployed as a node module

### Install and Build
```
cd app/
npm install
npm run build
```

### Debug
Use the 'Launch from build' debug profile.
This runs ${workspaceFolder}/app/build/src/main.js 

* If you put a breakpoint in app/src/main.ts or app/src/appUsingLib.ts AND a breakpoint in lib/src/utilities => the debugger stops and everything works fine

* If you put a breakpoint ONLY in lib/src/utilities => __**the debugger doesn't stop**__

### NPM Link
Note that we get the same behavior if we use NPM link instead of having the path in the app/package.json ("@local/lib": "../lib/dist")

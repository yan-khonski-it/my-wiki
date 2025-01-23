# How to install Node.js on Windows

## Check if node / npm weere installed before

Check NPM version
`npm -v`

Output
```
PS C:\Users\Yan> npm -v
11.0.0
```

Check Nodejs version
`node -v`

Output
```
PS C:\Users\Yan> node -v
v22.11.0
```

If you want to remove them, just to the [#uninstall-nodejs-from-windows](#uninstall-nodejs-from-windows) section.

## Installation

https://nodejs.org/en/download
In case, the link above changes, I will put the commands here.

Currently (2025-01-21), they recommend using Schniz.fnm. 
https://github.com/Schniz/fnm

It is a fast Node management.

### Download and install fnm:
```
winget install Schniz.fnm
```

> Bellow, 
> **Please, use PowerShell**

### Install environment variables
To get envrinment variables names and their values, run this command:
```
fnm env
```
The output will be:
```
PS C:\Users\Yan> fnm env
$env:PATH = "C:\Users\Yan\AppData\Local\fnm_multishells\22812_1737499396918;C:\Dev\python\python-3.12.7\Scripts\;more-path-entries;"
$env:FNM_MULTISHELL_PATH = "C:\Users\Yan\AppData\Local\fnm_multishells\22812_1737499396918"
$env:FNM_VERSION_FILE_STRATEGY = "local"
$env:FNM_DIR = "C:\Users\Yan\AppData\Roaming\fnm"
$env:FNM_LOGLEVEL = "info"
$env:FNM_NODE_DIST_MIRROR = "https://nodejs.org/dist"
$env:FNM_COREPACK_ENABLED = "false"
$env:FNM_RESOLVE_ENGINES = "true"
$env:FNM_ARCH = "x64"
```

If you eval the value of the previous output, you will have the variables set. However, on my machine, the eval command did not work, so I had to set the env variables manually.

### Setup
Run PowerShell and use this command
```
fnm env --use-on-cd | Out-String | Invoke-Expression
```

### Download and install Node.js:
```
fnm install 22
```

### Use node.js
```
fnm use v22.13.1
```
Expected output
```
Using Node v22.13.1
```

### Verify the Node.js version:
```
node -v # Should print "v22.13.1".
```
### Verify npm version:
```
npm -v # Should print "10.9.2".
```

## Update NPM
After the previous step, it can happen that npm version is not the latest. You can check the latest version

https://docs.npmjs.com/cli/v11/commands/npm-version

Run the command to update npm
```
npm install -g npm
```

The output will be:
```
PS C:\Users\Yan> npm install -g npm

removed 11 packages, and changed 39 packages in 5s
PS C:\Users\Yan> npm -v
11.0.0
```

## Uninstall nodejs
Run the command, where 22 is the version of node.js you want to remove.
```
 fnm uninstall 22
```

## Uninstall Node.js from windows
- https://www.geeksforgeeks.org/how-to-completely-remove-node-js-from-windows/
- https://stackoverflow.com/questions/20711240/how-to-completely-remove-node-js-from-windows

## How to add a new dependency to the project
Add the depondency and its version to the package.json file.
Then run insstall command, so the dependecy will be added to the node_modules.
```
npm install
```

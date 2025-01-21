# How to install Node.js on Windows

## Check
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

### Download and install Node.js:
```
fnm install 22
```
### Verify the Node.js version:
```
node -v # Should print "v22.13.1".
```
### Verify npm version:
```
npm -v # Should print "10.9.2".
```

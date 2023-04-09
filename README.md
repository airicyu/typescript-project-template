# typescript-project-template

This is a minimum but good enough setup for Typescript project template (NodeJS).

It contains:
- Setup of typescript, ts-node dependencies and tsconfig.json.
- Start/Build script is ready.
- VS code debug with main script is ready
- Bundle output types via api-extractor is ready.

------

# Commands

## Install

`npm i`

------

## Start

`npm start`

------

## Build commands

### Compile Typescript

`npm run build`

The compiled js files would be under dir `./build`.

### Compile Typescript in watch mode

`npm run watch`

### Bundle library type declaration file

`npm run bundleType`

The type declaration file would be in `./build/types/lib.d.ts`.

------

## VS Code Debug

- Run against main.ts
- Support source maps
- Skip debug of codes for 3rd-party lib or core code.

```
{
    "type": "node",
    "request": "launch",
    "name": "Launch Program",
    "program": "${workspaceFolder}\\build\\main.js",
    "preLaunchTask": "tsc: build - tsconfig.json",
    "outputCapture": "std",
    "sourceMaps": true,
    "cwd": "${workspaceFolder}",
    "skipFiles": [
        "<node_internals>/**",
        "${workspaceFolder}/node_modules/**/*.js"
    ],
    "outFiles": [
        "${workspaceFolder}/build/**/*.js"
    ]
}
```
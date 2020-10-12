# Node.js Application

## Links

[How To](https://medium.com/@jorgemcdev/node-express-app-typescript-tslint-prettier-airbnb-husky-c42588cbcbe3)

[Building and publishing an NPM Typescript package](https://itnext.io/step-by-step-building-and-publishing-an-npm-typescript-package-44fe7164964c)

## Install

```shell
mkdir <app-name>
cd <app-name>
git init
npm init
npm i -D typescript @types/node ts-node-dev
$(npm bin)/tsc -v
$(npm bin)/tsc --init
```

Edit `package.json`  
Edit `tsconfig.json`

### Express

```shell
npm i -S express
npm i -D @types/express
```

### Application

Edit `src/index.ts`

Run:

```shell
npm run dev
```

## Files Content

`package.json`

```json
  "scripts": {
    "build": "tsc",
    "start": "NODE_ENV=production node ./build/index.js",
    "dev": "ts-node-dev --respawn --transpileOnly ./src/index.ts",
  },
```

`tsconfig.json`

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "outDir": "./build",
    "strict": true,
    ...
  },
  "include": [
    "src/**/*.ts"
  ]
}
```

# NX (nrlw)

## Links

[NX - Getting Started](https://nx.dev/angular/getting-started/getting-started)

[NX - GitHub](https://github.com/nrwl/nx)

[NX - Blog](https://blog.nrwl.io/)

[Lerna - Getting Started](https://lerna.js.org/)

[Lerna - GitHub](https://github.com/lerna/lerna)

### Posts

[Release management in Angular with Lerna](https://blog.angularindepth.com/release-management-in-angular-with-lerna-21b4ab417c59)

## Initial tools install

```shell
npm i @angular/cli -g
npm i lerna -g
```

## Create workspace

```shell
npx create-nx-workspace@latest <workspace name>
cd <workspace name>
```

## Generate application

```shell
ng add @nrwl/angular
ng g @nrwl/angular:application <application name>
```

Generate library

```shell
ng g @nrwl/angular:library <library name>
```

or

```shell
ng g @nrwl/angular:library <library name> --publishable
```

## Initialize lerna workspace

One version for all workspace

```shell
lerna init
```

or independent versions for each library

```shell
lerna init --independent
```

## Configuration

Edit `lerna.json`

## Dependencies

To add `lib A` to the dependencies in the package.json of `lib B`.<br />
(`lib A` and `lib B` are `name` property in `package.json` of the libraries)

```shell
lerna add <lib A> --scope=<lib B>
```

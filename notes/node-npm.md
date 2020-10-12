# Node.js and NPM

## Update NPM

```shell
npm i -g npm
```

## Global packages

### Install global packages

```shell
npm i -g @angular/cli @nrwl/cli lerna npm-check-updates
```

### List global pacages

```shell
npm list -g --depth=0
```

### Update global pacages

```shell
ncu -g
npm outdated -g
npm update -g
```

### Linked packages

```shell
npm ls --depth=0 --link=true
npm ls -g --depth=0 --link=true
```

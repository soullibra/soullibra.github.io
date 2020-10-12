# Angular setup

## Core

### angular@stable

```shell
npm i -g @angular/cli
ng new ${APP_NAME} --style=scss
cd ${APP_NAME}
ng --vertion
```

### angular@next

```shell
npx -p @angular/cli@next ng new ${APP_NAME}
cd ${APP_NAME}
ng --vertion
```

## Material

### legacy

```shell
npm install --save @angular/material @angular/cdk @angular/animations
ng g module material --flat
```

### modern

```shell
ng add @angular/material
ng g module material --flat
```

## NGRX

```shell
npm install @ngrx/core @ngrx/store @ngrx/effects @ngrx/store-devtools @ngrx/router-store --save
cd ${APP_NAME}/src/app/
mkdir store store/actions store/effects store/reducers store/selectors store/state
```

## CLI

```shell
ng g component ${COMPONENT} --module app.module
ng g module modules/${MODULE} --routing
ng g component modules/${MODULE}/components/${COMPONENT} --module=modules/${MODULE}
ng g component components/${COMPONENT} --inlineStyle --inlineTemplate --flat
```

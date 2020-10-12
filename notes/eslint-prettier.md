# ESLint + Stylelint + Prettier

## Install (new)

Install ESLint

```shell
npm i -D eslint
$(npm bin)/eslint --init
```

Install Stylelint:

```shell
npm i -D stylelint stylelint-scss
npm view stylelint-config-airbnb peerDependencies
npm i -D stylelint-config-airbnb
```

Install Prettier:

```shell
npm i -D prettier eslint-config-prettier eslint-plugin-prettier stylelint-config-prettier stylelint-prettier
```

Edit config files:

`.eslintrc.json`

```json
{
  "extends": [..., "airbnb...", "prettier/recommended"],
  "rules": {
    "import/extensions": [
      "error",
      "ignorePackages",
      {
        "js": "never",
        "jsx": "never",
        "ts": "never",
        "tsx": "never"
      }
    ]
  },
  "settings": {
    "import/resolver": {
      "node": {
        "extensions": [".js", ".jsx", ".ts", ".tsx"]
      }
    }
  }
}
```

### Husky hooks

```shell
npm i -D husky
nano package.json
```

## Files Content

`package.json`

```json
  ...
  "scripts": {
    "lint": "eslint .",
    "prettier:base": "prettier --parser typescript --single-quote",
    "prettier:check": "npm run prettier:base -- --list-different \"src/**/*.{ts,tsx}\"",
    "prettier:write": "npm run prettier:base -- --write \"src/**/*.{ts,tsx}\"",
  },
  "husky": {
    "hooks": {
      "pre-commit": "npm run prettier:write"
    }
  },
  ...
```

`.prettierrc`

```json
{
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "es5",
  "useTabs": false
}
```

`.eslintrc.json`

```json
{
  "extends": ["airbnb-base", "plugin:prettier/recommended"]
}
```

`.stylelintrc.json`

```json
{
  "plugins": ["stylelint-scss"],
  "extends": ["stylelint-config-airbnb", "stylelint-prettier/recommended"]
}
```

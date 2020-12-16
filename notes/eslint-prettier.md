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

`.editorconfig`

```ini
root = true

[*]
charset = utf-8
end_of_line = lf
insert_final_newline = true
indent_style = space
max_line_length = 120
indent_size = 4
trim_trailing_whitespace = true

[*.md]
max_line_length = off
trim_trailing_whitespace = false
```

`.prettierrc.json`

```json
{
  "trailingComma": "es5",
  "tabWidth": 4,
  "semi": true,
  "singleQuote": true,
  "useTabs": false,
  "printWidth": 120
}
```

`.eslintrc.json`

```json
{
  "env": {
    "es2021": true,
    "node": true
  },
  "extends": [
    "airbnb-base",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking",
    "plugin:prettier/recommended",
    "plugin:cypress/recommended"
  ],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "project": "./tsconfig.json",
    "tsconfigRootDir": "./"
  },
  "plugins": ["@typescript-eslint", "import"],
  "rules": {
    "import/prefer-default-export": "off",
    "import/extensions": [
      "error",
      "ignorePackages",
      {
        "js": "never",
        "jsx": "never",
        "ts": "never",
        "tsx": "never"
      }
    ],
    "no-plusplus": ["warn", { "allowForLoopAfterthoughts": true }],
    "prefer-destructuring": "off",
    "no-shadow": "off",
    "class-methods-use-this": "off",
    "@typescript-eslint/no-shadow": ["error"],
    "@typescript-eslint/no-inferrable-types": "off"
  },
  "settings": {
    "import/resolver": {
      "typescript": {}
    }
  }
}
```

`.stylelintrc.json`

```json
{
  "plugins": ["stylelint-scss"],
  "extends": ["stylelint-config-airbnb", "stylelint-prettier/recommended"]
}
```

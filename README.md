# CONFIG

## Editor Config

```editorconfig
# .editorconfig

root = true

[*]
charset = utf-8
end_of_line = lf # Prettier
indent_size = 2 # Prettier
indent_style = space # Prettier
trim_trailing_whitespace = true

[*.md]
trim_trailing_whitespace = false
```

---

## Prettier

```pnpm
pnpm install --save-dev prettier prettier-plugin-astro
```

- **_package.json (pnpm support)_**

```json
"format": "prettier --write --plugin-search-dir=. ."
```

- **_.prettierrc.yaml_**

```yaml
# .prettierrc.yaml

plugins:
  - prettier-plugin-astro

overrides:
  - files: '*.astro'
    options:
      parser: astro

semi: false
printWidth: 100
singleQuote: true
jsxSingleQuote: true
```

- **_.prettierrc.json_**

```json
{
  "plugins": ["prettier-plugin-astro"],

  "overrides": [
    {
      "files": "*.astro",
      "options": {
        "parser": "astro"
      }
    }
  ],

  "semi": false,
  "printWidth": 100,
  "singleQuote": true,
  "jsxSingleQuote": true
}
```

---

## ESLint

```pnpm
pnpm install --save-dev ts-standard eslint-plugin-astro @typescript-eslint/parser
```

```json
"lint": "eslint --fix . --ext .js,.ts,.astro"
```

- **_.eslintrc.yaml_**

```yaml
# .eslintrc.yaml

extends:
  - standard-with-typescript
  - plugin:astro/recommended

parserOptions:
  project: tsconfig.json

overrides:
  - files: '*.astro'
    parser: astro-eslint-parser
    parserOptions:
      parser: '@typescript-eslint/parser'
      extraFileExtensions: .astro

rules:
  comma-dangle: off
  no-multiple-empty-lines: off
  no-trailing-spaces: off
  space-before-function-paren: off

  '@typescript-eslint/comma-dangle': off
  '@typescript-eslint/space-before-function-paren': off
```

- **_.eslintrc.json_**

```json
{
  "extends": ["standard-with-typescript", "plugin:astro/recommended"],

  "parserOptions": {
    "project": "tsconfig.json"
  },

  "overrides": [
    {
      "files": "*.astro",
      "parser": "astro-eslint-parser",
      "parserOptions": {
        "parser": "@typescript-eslint/parser",
        "extraFileExtensions": ".astro"
      }
    }
  ],

  "rules": {
    "comma-dangle": "off",
    "no-multiple-empty-lines": "off",
    "no-trailing-spaces": "off",
    "space-before-function-paren": "off",

    "@typescript-eslint/comma-dangle": "off",
    "@typescript-eslint/space-before-function-paren": "off"
  }
}
```

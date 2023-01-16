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

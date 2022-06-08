# Init TypeScript Project

Install TS and more

```bash
pnpm init -y
pnpm add -D typescript sucrase nodemon
mkdir src
touch src/server.ts
echo "const a: number = 5; console.log(a);" >> src/server.ts
```

add on `package.json`

```json
"scripts": {
"dev": "nodemon src/server.ts",
"build": "sucrase ./src -d .dist --transforms typescript, imports"
},
```

add on `nodemon.json`

```bash
echo "{
    \"watch\": [
        \"src\"
    ],
    \"ext\": \"ts\",
    \"execMap\": {
        \"ts\": \"sucrase-node src/server.ts\"
    }
}" >> nodemon.json
```

## Eslint

Install eslint

```bash
pnpm add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
```
init eslint

```bash
pnpm eslint --init
```

add on `.eslintrc.js`

```bash
echo "module.exports = {
  env: {
    node: true,
    es2021: true
  },
  extends: ['standard', 'plugin:@typescript-eslint/recommended'],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaVersion: 'latest',
    sourceType: 'module'
  },
  plugins: ['@typescript-eslint'],
  rules: {}
}" >> .eslintrc.js
```

### settings.json (vs code)

```json
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },

  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },

  "[typescript]": {
    "editor.formatOnSave": false
  },

  "[typescriptreact]": {
    "editor.formatOnSave": false
  },
```

Install prettier (if necessary)

```bash
pnpm add prettier eslint-config-prettier eslint-plugin-prettier -D
```

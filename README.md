# VS Code Extensions 에서 ESLint, Prettier 설치

# yarn 설치

```bash
npm i -g yarn

# 권한 오류 나면 Windows PowerShell 에서 아래 명령어 실행
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
# 재설치
npm i -g yarn
```


# react-typescript

```bash
npx create-react-app . --template typescript
```

# .prettierrc.json 파일 생성 후 eslint 와 prettier 연결

```bash
# prettier 설치 
yarn add --dev --exact prettier

# 파일 생성
echo {}> .prettierrc.json

# eslint 초기 설정
yarn run eslint --init

? How would you like to use ESLint? ...
  To check syntax only
  To check syntax and find problems
> To check syntax, find problems, and enforce code style

? What type of modules does your project use? ... 
> JavaScript modules (import/export)
  CommonJS (require/exports)
  None of these

? Which framework does your project use? ...       
> React
  Vue.js
  None of these

? Does your project use TypeScript? 
  No 
> Yes

? Where does your code run? ...  (Press <space> to select, <a> to toggle all, <i> to invert selection)
√ Browser
√ Node

? How would you like to define a style for your project? ... 
> Use a popular style guide
  Answer questions about your style

? Which style guide do you want to follow? ...
> Standard: https://github.com/standard/eslint-config-standard-with-typescript
  XO: https://github.com/xojs/eslint-config-xo-typescript
  
? What format do you want your config file to be in? ...
> JavaScript
  YAML
  JSON

? Would you like to install them now? 
  No 
> Yes

? Which package manager do you want to use? ... 
  npm
> yarn
  pnpm
```

# .eslintrc.js 파일 수정

```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  extends: [
    "plugin:react/recommended",
    "standard",
    "prettier",
    "plugin:storybook/recommended",
  ],
  parser: "@typescript-eslint/parser",
  overrides: [],
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: "latest",
    sourceType: "module",
  },
  plugins: ["react", "@typescript-eslint"],
  rules: {
    "react/prop-types": "off",
  },
};
```


# eslint 와 prettier 연결
```
yarn add eslint-config-prettier --dev
```


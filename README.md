# @vitordbento/configs

Use this package in any project to share the same configuration files.

## What's included

- Prettier
- ESLint
- TS [Coming soon...]
- Jest [Coming soon...]

## Instructions

Install as a `devDependency` in your project.

```bash
yarn add @vitordbento/configs --dev
```

##### Prettier

Use this file in any project to share the same Prettier configuration.

1. First, install Prettier locally:

```bash
yarn add --dev prettier
```

2. Then, create an empty config file to let editors and other tools know you are using Prettier:

```bash
echo {}> .prettierrc.js
```

3. Finally, copy and paste the below code in the newly created file:

```js
module.exports = {
  ...require('@vitordbento/configs/prettierrc'),
  // override what ever you  want eg:
  // tabWidth: 4
};
```

4. You can optionally add the below scripts into your package.json:

```json
"scripts": {
  "format-check": "prettier --check \"src/**/*\"",
  "format-fix": "prettier --write \"src/**/*\"",
}
```

##### ESLint

Use this file in any project to share the same ESLint configuration.

1. First, install ESLint locally:

```bash
yarn add eslint --dev
```

2. Then, create an empty config file to let editors and other tools know you are using ESLint:

```bash
echo {}> .eslintrc.js
```

3. Finally, copy and paste the below code in the newly created file:

```js
module.exports = {
  extends: [require.resolve('@vitordbento/configs/eslintrc')],
};
```

4. You can optionally add the below scripts into your package.json:

```json
"scripts": {
  "lint-check": "eslint . --ext ts --ext tsx --ext js",
  "lint-fix": "eslint . --fix",
}
```

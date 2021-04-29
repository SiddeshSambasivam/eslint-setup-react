<h1 align="center" style="font-weight:bold">Getting started with eslint for React</h1>
<p align="center">This repository contains the notes and code which I used to learn how to setup eslint for react projects</p>

<h2 style="font-weight:bold">Instructions</h2>

1. Install eslint and create a config file

    ```
    npm install eslint --save-dev
    npx esline --init
    ```

2. Personal Preference, inside the .eslintrc.json add `react/react-in-jsx-scope": "off"` under the rules. Add `"jest": true` under env.

3. Update the settings.json in the vscode

    ```json
    "editor.formatOnSave": true,
    "editor.codeActionsOnSave": {
        "source.fixAll.eslint": true
    },
    "eslint.alwaysShowStatus": true,
    "files.autoSave": "onFocusChange",
    "eslint.validate": [
        "javascript"
    ],

    ```

4. Add this to package.json

    ```json
    "lint": "eslint src/**/*.js",
    "lint:fix": "eslint src/**/*.js --fix"
    ```

    Now `npm run lint:fix` will enfore the linting style to the changes.

5. (Optional) To setup prettier, install the following packages

    ```bash
    npm uninstall eslint-config-prettier eslint-plugin-prettier prettier --save-dev
    ```

    and add `"plugin:prettier/recommended"` under `extends` in .eslintrc.json

**Peronal Notes:**

-   The difference between npm and npx is that npm is a package manager to install node packages golbally, where as npx is tool to execute packages. Packages used by npx are not installed globally so you have to carefree for the pollution for the long term.

-   When open sourcing projects or working as a group, its a good practice to setup linting.

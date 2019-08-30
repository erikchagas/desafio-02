## Step by step to create the backend of [MeetApp](https://github.com/Rocketseat/bootcamp-gostack-desafio-02/blob/master/README.md#desafio-02-iniciando-aplica%C3%A7%C3%A3o)

### Initial creation of main project file structure
1. Create the folder of your project
```shell
mkdir project
```

2. Create README.md
```shell
touch README.md
```

3. Add dependency 'express'
```shell
yarn add express
```

4. Create folder src in the root directory
```shell
mkdir src
```

5. Create folder src/app
```shell
cd src
```
```shell
mkdir app
```

6. Create folder src/app/controllers
```shell
cd app
```
```shell
mkdir controllers
```

7. Create folder src/app/middlewares
```shell
mkdir middlewares
```

8. Create folder src/app/models
```shell
mkdir models
```

9. Create folder src/config
```shell
cd ..
```
```shell
mkdir config
```

10. Create folder src/database
```shell
mkdir database
```

11. Create folder src/database/migrations
```shell
cd database
```
```shell
mkdir migrations
```

12. Create file src/database/index.js
```shell
touch index.js
```

13. Create file src/app.js
```shell
cd ..
```
```shell
touch app.js
```

14. Create file src/routes.js
```shell
touch routes.js
```

15. Create file src/server.js
```shell
touch server.js
```

### Installing dev dependencies
1. Installation of Nodemon e Sucrase
```shell
yarn add sucrase nodemon -D

```
2. Add script to watch changes with Nodemon in package.json
```javascript
"scripts": {
  "dev": "nodemon src/server.js"
}
```

3. Create file src/nodemon.json
```javascript
{
  "execMap": {
    "js": sucrase-mode
  }
}
```
4. Installation of Docker
```shell
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

```shell
sudo docker run hello-world
```

```shell
sudo groupadd docker
```

```shell
sudo usermod -aG docker $USER
```

```shell
newgrp docker
```

```shell
docker run hello-world
```

```shell
sudo systemctl enable docker
```


5. Initializing a Docker image of Postgres
```shell
docker run --name database -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres
```

```shell
docker start database
```

6. Installing ESLint
```shell
yarn add eslint -D
```

7. Initializing ESLint
```shell
yarn eslint --init
```

8. Installing ESLint extension on VS Code
Search for ESLint on the Extension VS Code tab

9. Configure 'ESLint' on VS Code
```js
"eslint.autoFixOnSave": true,
"eslint.validate": [
  {
    "language": "javascript",
    "autoFix": true
  },
  {
    "language": "javascriptreact",
    "autoFix": true
  },
  {
    "language": "typescript",
    "autoFix": true
  },
  {
    "language": "typescriptreact",
    "autoFix": true
  }
]
```

10. Override custom setting on .eslintrc.js
```js
rules: {
  "class-methods-use-this": "off",
  "no-param-reassign": "off",
  "camelCase": "off",
  "no-unused-vars": ["error", {"argsIgnorePattern": "next"}]
},
```

11. Installing Prettier
```shell
yarn add prettier eslint-config-prettier eslint-plugin-prettier
```

12. Integrating Prettier on eslintrc.js
```js
extends: [
  'airbnb-base',
  'prettier'
],
plugins: ['prettier'],
```

```js
rules: {
  "prettier/prettier": "error",
  "class-methods-use-this": "off",
  "no-param-reassign": "off",
  "camelCase": "off",
  "no-unused-vars": ["error", {"argsIgnorePattern": "next"}]
},
```
13. Create file .prettierrc
```shell
touch .prettierrc
```

14. Override default setting on .prettierrc
```js
{
  "singleQuote": true,
  "trailingComma": "es5"
}
```

15. Running ESLint fix on all of the project's files
```shell
yarn eslint --fix src --ext .js
```

16. Installing EditorConfig extension on VS Code
Search for EditorConfig on the Extension VS Code tab

17. Generating .editorconfig
Right-click on the mouse over the root tree on VS Code's Explorer tab and select
'Generate .editorconfig'

17. Configuring .editorconfig
```js
root = true

[*]
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```

### Configuring Sequelize

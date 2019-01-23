---
description: 'HTML5, CSS3, Sass, NPM , and JavaScript'
---

# A Website

## **Technologies Used**

```text
HTML5 CSS3 - Transitions
Grid/Flex Sass 
NPM - Package Manager 
JavaScript 
Git
```

## Step 1

> create folder for project and open **text editor** in projects folder

> create `dist` **folder** in **main directory**

> create `index.html` **file** in `dist` folder

> in `index.html` **file,** using **html emmet** type `!` followed by **tab** to create starter html template

> add `link` tag in the `index.html` file in the `header` section above `title`

```css
<link rel="stylesheet" href="css/main.css">
```

> create `scss` **folder** in **main directory**

> create `main.scss` **file** in **scss folder**

## **Step 2**

> in the **terminal,** `cd` into **project-folder** and run `npm init`**.**  This creates `package.json` **file** in the **main directory**.

> in the **terminal** run `npm i node-sass`. This creates `node_modules` **folder** in the **main directory**

## **Step 3**

> now inside the `package.json` **file** in the `script` section, **change** `test` into `scss`

```javascript
{
  "name": "portfolio",
  "version": "1.0.0",
  "description": "My portfolio website",
  "main": "index.js",
  "scripts": {
    "sass": "node-sass -w scss/ -o dist/css/ --recursive"
  },
  "author": "Joseph Hyatt",
  "license": "MIT",
  "dependencies": {
    "node-sass": "^4.11.0"
  }
}
```

> In **above** code, on line **7** `node-sass` is to **run node-sass program.** `-w scss/`  to **watch Scss folder.** `-o dist/css/` **-o** sets an **output** of the **compiled sass** eto **dist/css.** `--recursive` for the `_partials` loading with **auto reload** vscode.

> to run an `NPM script` **type** `npm run <script-name>` in the **terminal**. In above example we called the `NPM script` `sass`

> to run an `NPM script` **type** `npm run <script-name>` in the **terminal**. In above example we called the `NPM script` `sass`

```text
npm run sass
```

> create `.gitignore` **file** in **main directory** and **add** `node_modules` inside `gitignore` file


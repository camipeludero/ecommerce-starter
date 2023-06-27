# GM2 Ecommerce starter theme

## Table of Contents
- [Install](#install)
- [Usage](#usage)
- [Base Theme](#theme)
- [Tech Stack](#techstack)
- [Project Structure](#structure)
- [Staying up to date with Dawn changes](#staying-up-to-date-with-dawn-changes)
- [Developer tools](#developer-tools)

## Install

To install this project on your local machine, follow these steps:

1. Clone the repository:

```bash
git clone https://github.com/camipeludero/gm2-ecommerce-boilerplate.git
```

2. Navigate to the project directory:

```bash
cd gm2-ecommerce-boilerplate
```

3. If you don't have it, install Shopify CLI v3:

```bash
npm run install-shopify-cli
```

4. Complete the `config` values of your store inside `package.json`:

```bash
    "store": "STORE_ID or STORE_URL",
    "password": "THEME_ACCESS_PASSWORD",
    "theme_id": "CURRENT_THEME_ID(optional)"
```

5. Login on your Shopify store:

```bash
npm run login
```

6. Start the development server:

```bash
npm start
```

7. Navigate to `http://127.0.0.1:9292/` in your web browser to view the development version of the theme.

## Usage

To use this project as a starting point for building a Shopify theme, you can modify the code and add your own functionality.

To deploy the theme to your Shopify store, run any of the following commands:

- Deploy a new theme:

```bash
npm run deploy:new
```

- Deploy and update an existing theme

```bash
npm run deploy
```

- Deploy and update the current theme

```bash
npm run deploy:theme
```

To pull the changes from the remote Shopify, run any of the following commands:

- Pull and update an existing theme

```bash
npm run pull
```

- Pull and update the current theme files

```bash
npm run pull:theme
```

### Tech Stack

- [Liquid](https://shopify.dev/api/liquid) / HTML
- [Tailwind](https://tailwindcss.com/docs) + [SCSS](https://sass-lang.com/documentation)
- [Shopify CLI 3.0](https://shopify.dev/docs/themes/tools/cli)
- [NPM](https://www.npmjs.com/)

### Theme

> This theme uses [Dawn]({https://github.com/Shopify/dawn}) as its base theme.

## Staying up to date with Dawn changes

Say you're building a new theme off Dawn but you still want to be able to pull in the latest changes, you can add a remote `upstream` pointing to this Dawn repository.

1. Navigate to your local theme folder.
2. Verify the list of remotes and validate that you have both an `origin` and `upstream`:
```sh
git remote -v
```
3. If you don't see an `upstream`, you can add one that points to Shopify's Dawn repository:
```sh
git remote add upstream https://github.com/Shopify/dawn.git
```
4. Pull in the latest Dawn changes into your repository:
```sh
git fetch upstream
git pull upstream main
```

## Developer tools

There are a number of really useful tools that the Shopify Themes team uses during development. Dawn is already set up to work with these tools.

### Shopify CLI

[Shopify CLI](https://github.com/Shopify/shopify-cli) helps you build Shopify themes faster and is used to automate and enhance your local development workflow. It comes bundled with a suite of commands for developing Shopify themes—everything from working with themes on a Shopify store (e.g. creating, publishing, deleting themes) or launching a development server for local theme development.

You can follow this [quick start guide for theme developers](https://github.com/Shopify/shopify-cli#quick-start-guide-for-theme-developers) to get started.

### Theme Check

We recommend using [Theme Check](https://github.com/shopify/theme-check) as a way to validate and lint your Shopify themes.

We've added Theme Check to Dawn's [list of VS Code extensions](/.vscode/extensions.json) so if you're using Visual Studio Code as your code editor of choice, you'll be prompted to install the [Theme Check VS Code](https://marketplace.visualstudio.com/items?itemName=Shopify.theme-check-vscode) extension upon opening VS Code after you've forked and cloned Dawn.

To run Shopify Theme Check, use the following command:

```bash
npm run check
```

You can also run it from a terminal with the following Shopify CLI command:

```bash
shopify theme check
```



# HTML Rspack Nonce Injector

A plugin for injecting a `nonce` attribute into HTML tags generated by the `html-rspack-plugin`.

## Installation

Install the package using NPM:

```bash
npm install html-rspack-nonce-injector
```

## Usage

Add the NonceInjector plugin to your Rspack configuration:

**rspack.config.js**

```js
const HtmlRspackPlugin = require('html-rspack-plugin');
const NonceInjector = require('html-rspack-nonce-injector');

module.exports = {
  plugins: [
    new HtmlRspackPlugin({ template: './src/index.html' }),
    new NonceInjector('nonce-value'), // Add your nonce value here
  ],
};
```

This will generate a file dist/index.html containing the following

```html
<html>
  <head>
    <meta charset="utf-8" />
    <title>Rspack App Example</title>
    <script defer src="" nonce="nonce-value"></script>
  </head>
  <body></body>
</html>
```
# html-externals-webpack-plugin
A webpack plugin that inserts externals into html

## usage

```javascript
// webpack.config.js
const HtmlExternalsWebpackPlugin = require('html-externals-webpack-plugin');
module.exports = {
  plugins: [
        // 生产环境下插入external模块的CDN脚本
        isEnvProduction && new HtmlExternalsWebpackPlugin(HtmlWebpackPlugin, [
          'https://cdn.jsdelivr.net/npm/react@16.13.1/umd/react.production.min.js',
          'https://cdn.jsdelivr.net/npm/react-dom@16.13.1/umd/react-dom.production.min.js',
          'https://cdn.jsdelivr.net/npm/react-router@5.2.0/umd/react-router.min.js',
        ])
  ]
}
```

You can find them in the HTML template:
```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8"/>
    <title>YuJudge</title>
    <script src="https://cdn.jsdelivr.net/npm/react@16.13.1/umd/react.production.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/react-dom@16.13.1/umd/react-dom.production.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/react-router@5.2.0/umd/react-router.min.js"></script>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>

```

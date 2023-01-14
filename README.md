# edu-react-intro

> Starta en react applikation utan script. Detta tjänar till en bra grund om vad som är minimi att förstå av en react applikation. Man bör förstå webpack och babel.


## Instruktioner

```bash
cd ~
cd ws
mkdir edu-react-intro
cd edu-react-intro
npm init -y
mkdir src
touch ./src/{index.js,index.html,App.jsx}
touch {.babelrc,webpack.config.js}
npm pkg set scripts.start="webpack-dev-server --mode development --open --hot --port 3000"
npm pkg set scripts.build="webpack --mode production"
npm install react
npm install react-dom
npm install webpack -D
npm install webpack-cli -D
npm install html-webpack-plugin -D
npm install @babel/core  -D
npm install @babel/preset-env  -D
npm install @babel/preset-react  -D
npm install babel-loader -D
npm install webpack-dev-server -D
```

## DoD

```bash
npm start
```

## index.html

```html
<!doctype html>
<html lang=”en”>

<head>
    <meta charset=”utf-8">
    <title>edu-react-intro</title>
</head>

<body>
    <div id=”app”></div>
</body>

</html>
```


## index.js

```js
import React from 'react';
import ReactDOM from 'react-dom';

import App from './components/app';

ReactDOM.render(<App />, document.getElementById('mountNode'));
```

## App.jsx

```jsx
import React from "react";

export default () => {
    return <h1>WACOCO</h1>
};
```

## webpack.config.js

```js
const path = require("path");
const HtmlWebpackPlugin = require("html-webpack-plugin");

const htmlPlugin = new HtmlWebpackPlugin({
  template: "./src/index.html",
  filename: "./index.html",
});

module.exports = {
  entry: "./src",
  output: {
    path: path.resolve(__dirname, "public"),
    filename: "bundle.js",
  },
  module: {
    rules: [
      {
        test: /\.(js|jsx)$/,
        exclude: /node_modules/,
        use: ["babel-loader"],
      },
      {
        test: /\.css$/,
        use: ["style-loader", "css-loader"],
      },
    ],
  },
  resolve: {
    extensions: ["*", ".js", ".jsx"],
  },
  plugins: [htmlPlugin],
};
```

## .babelrc

```json
{
    "presets": [
        [
            "@babel/preset-env",
            {
                "targets": {
                    "node": "current"
                }
            }
        ],
        "@babel/react"
    ]
}
```

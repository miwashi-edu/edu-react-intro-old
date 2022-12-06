# edu-react-intro

## Instruktioner

```bash
cd ~
cd ws
mkdir edu-react-intro
cd edu-react-intro
npm init -y
npm i webpack 
npm i babel-loader 
npm i @babel/preset-react 
npm i @babel/core 
npm i babel-preset-react 
npm i html-webpack-plugin 
npm i webpack-dev-server 
npm i css-loader 
npm i style-loader 
npm i @babel/plugin-proposal-class-properties 
npm i webpack-cli -D
npm i npm i react react-dom -S
mkdir src
touch ./src/index.js
touch ./src/index.html
touch .babelrc 
touch webpack.config.js
npm pkg set scripts.start="webpack serve --config webpack.config.js"
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
import ReactDOM from 'react - dom';
import React from 'react';
const App = () => {
    return <h1>edu-react-intro</h1>;
}
ReactDOM.render(<App />, document.getElementById('app'));
```

## webpack.config.js

```js
const HtmlWebPackPlugin = require("html-webpack-plugin");
const htmlPlugin = new HtmlWebPackPlugin({
    template: "./src/index.html",
    filename: "./index.html"
});

module.exports = {
    mode: 'development',
    module: {
        rules: [{
            test: /\.js$/, 
            exclude: /node_modules/,
            use: {
                loader: "babel-loader"
            }
        },
        {
            test: /\.css$/,
            use: ["style-loader", "css-loader"]
        }
    ]},
plugins: [htmlPlugin]
};
```

## .babelrc

```json
{
    "presets": ["@babel/preset-react"],
    "plugins": ["@babel/plugin-proposal-class-properties"]
}
```

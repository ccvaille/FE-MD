# Webpack 学习笔记

标签（空格分隔）： 前端

---

## 简介
- 四大概念
    - Entry 入口文件
    - Output 出口文件 ： bundle.js 文件
    ```
    module.exports = {
      entry: './main.js',
      output: {
        filename: 'bundle.js'
      }
    };
    
    ```
    - Loader 加载器： bable-loader css-loader
    ```
    const config = {
      ...
      module: {
        rules: [
          {test: /\.(js|jsx)$/, use: 'babel-loader'}
        ]
      }
    };
    
    ```
    - Plugin 插件
    ```
    const HtmlWebpackPlugin = require('html-webpack-plugin'); //installed via npm
    
    const config = {
      ...
      plugins: [
        new webpack.optimize.UglifyJsPlugin(), // webpack 内置有一些 plugin
        new HtmlWebpackPlugin({template: './src/index.html'}) // 另外一些可以通过装包实现
      ]
    };
    
    module.exports = config;
    ```





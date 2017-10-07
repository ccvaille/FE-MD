# PostCSS
- pre-processor(预处理器)
```
h1 {
    color: red;
}

@red : red;
h1 {
    color: @red;
}
```

- post-processor(后处理器)
```
div {
    border-radius: 3px;
}

div {
    -moz-border-radius: 3px;
    -webkit-border-radius: 3px;
    border-radius: 3px;
}
```

- 关于 PostCSS
> 它提供了一种方式用 JavaScript 代码来处理 CSS。它负责把 CSS 代码解析成抽象语法树结构（Abstract Syntax Tree，AST），再交由插件来进行处理

- 使用
  -  与已有的构建工具进行集成（Webpack, Gulp, Grunt）
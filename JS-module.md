# 模块化
## A: 非 Module 模式
- 初级写法：函数被挂载在全局变量下，使用时直接调用，缺点： 污染全局变量，有可能出现变量名冲突
```js
function foo() {
    // ...
}
function bar() {
    // ...
}
```
- 对象写法：有一定的命名空间作用，可是本质是对象，不安全
```js
var Module = {
    foo: function() {},
    bar: function() {}
}
Module.foo();

```
- 立即执行函数：JS 只有函数作用域，能保护私有变量
```js
var Module = (function(){
    var _private = "safe now";
    var foo = function() {
        console.log(_private);
    }
    return {
        foo: foo
    }
})();

Module.foo();
Module._private; // undefined
```
## 引入依赖(基础的模块模式)
```js
var Module = (function($) {
    var _$body = $("body");
    var foo = function() {
        console.log($_body);
    }

    return {
        foo:foo
    }
})(jQuery)

Module.foo();
```

## B: LABjs- Script Loader(2009)
- `$LAB` 对象替代了 `<script>` 标签
- `.script()` 表示加载 JavaScript 文件
- 带 `.wait()` 表示立即运行 JavaScript 文件，但是还运行参数中的函数
```js
script(src="LAB.js" async)

$LAB.script("framework.js").wait()
    .script("init.js");
```

## C: YUI3 Loader - Module Loader (2009)
```js
// 编写模块
YUI.add('hello', function(Y) {
    Y.sayHello = function*(msg) {
        Y.DOM.set(el, 'innerHTML', 'hello!');
    }
}, '3.0.0', {
    requires: ['dom']
})

// 使用模块
YUI.use('hello', function(Y) {
    Y.sayHello('hey yui loader');
})

script(src="yui-min.js")
script(src="module1.js")
script(src="module1.js")
script(src="module2.js")

YUI().use('module1', 'module2', 'module3', function(Y) {
    // ...
})
```

## D: COMMONjs - API Standard (2009)
```js
exports.add = function(a, b) {
    return a + b;
}

var math = require('math');
console.log(math.add(1,2)); // 3
```

#### 参考链接
- [Javascript模块化编程（一）：模块的写法](http://www.ruanyifeng.com/blog/2012/10/javascript_module.html)
- [Javascript模块化编程（二）：AMD规范](http://www.ruanyifeng.com/blog/2012/10/asynchronous_module_definition.html)
- [Javascript模块化编程（三）：require.js的用法](http://www.ruanyifeng.com/blog/2012/11/require_js.html)
- [JavaScript 模块化七日谈](http://huangxuan.me/js-module-7day/)
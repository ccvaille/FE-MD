# JavaScript 高级程序设计（第三版）阅读笔记

标签（空格分隔）： 前端

---

### 第一章 JavaScript 简介
- 组成
    - ECMAScript 
    - DOM(文档对象模型)，提供访问和操作网页内容的方法和接口
    - BOM（浏览器对象模型），提供与浏览器交互的方法和接口

---

### 第二章 使用 JavaScript
- none

---
### 第三章 基本概念
- 语法
    - 区分大小写
    - 标识符：第一个字母必须是字母 _ $
        -  使用小驼峰命名（第一个字母小写，剩下首字母大写）
    - 注释： 
        - /* 多行注释 */
        - // 单行注释
    - 变量
        - var 局部变量
- 数据类型
    - 基本数据类型
        - typeof 操作符：检测变量的数据类型
        - Undefined：声明了变量没有复制，未定义
        - Null
        - Boolean
        - Number
            - **NaN: 与任何值都不相等，任何数值/0 都得 NaN**
            - isNaN(): 任何不能被转换为数值的值都会返回 true
            - Number()
            ```
            Number('hello') //NaN
            Number('0001') //1
            Number('') //0
            ```
                     
            - parseInt()
            ```
            parseInt('') //NaN
            parseInt('1234coolfe') //1234
            ```
                
            - parseFloat() 忽略第二个小数点
            ```
            parseFloat('1234.567.89') //1234.567  
            ```
                
        - String(不可变)
            - 字符字面量
                - \n: 换行
                - \r: 回车
                - \ \ : \
            - toString()
                
    - Object：对象或 null
        - new : var o = new Object();
    （17.01.23）
- 操作符
    - 一元操作符：只能操作一个值的操作
        - 递增/递减 ++/--
        ```
        var a = 2;
        var b = 20;
        var c = --a + b; // 21
        var d = a + b;  //21
            
        var a = 2;
        var b = 20;
        var e = a-- + b; //22
        var f = a + b; //21
        ```
            
    - 一元加和减操作符：+ -
    - 位操作符：按内存中表示数值的位来操作数值
        - 最后一位为符号位： 0表示正数，1表示负数
        - 负数以 **二进制补码** 存储
            - 绝对值的二进制
            - 反码
            - 加1
        - 按位非（NOT ~）：反码
        - 按位与（AND &）: 逻辑乘
        - 按位或（OR | )： 逻辑加
        - 按异位或（XOR ^）: 只有一个1才会返回 1，否则返回 0
        - 有符号左移（<<）：后面直接补 0
        - 有符号右移（>>）: 前面直接补 0
        - 无符号右移（>>>）：执行 **二进制补码**
        （17.01.24）
    - 布尔操作符
        - 逻辑非(!)
        - 逻辑与(&&): 逻辑乘
        - 逻辑或(||)： 逻辑加
    - 乘性操作符
        - 乘法(*)
        - 除法(/)
        - 求模(%)
    - 加性操作符
        - 加法(+)
        - 减法(-)
    - 关系操作符
        - 小于(<)
        - 大于(>)
        - 小于等于(<=)
        - 大于等于(>=)
    - 相等操作符
        - 相等(==)
        - 不相等(!=)
        ```
        null == undefined // true
        'NaN' == NaN // false NaN: 与任何值都不相等
        36 == NaN // false
        flase == 0 // ture
        null == 0 // false
        undefined == 0 // false
        ```
            
        - 全等(===)
        - 不全等(!==)
        ```
        null === undefined // false
        ```
        
    - 条件操作符
        ```
        var max = (num1 > num2) > num1 : num2;
        ```
        
    - 赋值操作符
        - *=
        - /=
        - %=
        - +=
        - -=
        ```
        var num = 10
        num = num + 10  =>  num += 10
        ```
            
- 语句
    - if 语句
    ```
    if( condition ) { statement1 } 
    else { statement2 }
    ```
    
    - do-while 语句 : 至少执行一次
    ```
    do {
        statement
    } while (expression)
    ```
    
    - while 语句
    ```
    while( expression )
    {
        statement
    }
    ```
    （17.01.24）
    - for 语句
    ```
    for(initialization; expression; post-loop-expression) {
        statement
    }
    ```
    
    - for-in 语句
    ```
    for(property in expression ) statement
    ```
    
    - break / continue 语句
        - break: 立即退出循环，强制继续执行循环后面的语句
        - continue: 立即退出循环，从循环顶部继续执行
        
    - switch 语句
    ```
    switch (expression) {
        case value : statement
        break;
        
        case value : statement
        break;
        
        default : statement
    }
    ```
    
- 函数
    - 参数
        - arguments[0]
        - arguments[1]
        ```
            function sum(a,b){ arguments[1] = 2; console.log(a+b)} 
            sum(1) // NaN
            sum(1,1) // 3 
            
        ```
  ---      
### 第四章：变量、作用域和内存问题
- 基本类型和引用类型的值
    - 基本类型（保存在栈内存中）
        - undefined
        - null
        - string
        - number
        - boolean
    - 引用类型（保存在堆内存中）
        - 保存在内存的对象
        （17.02.02)
            - 复制变量值 => 两个对象相同的值
            ```
            var num = 5;
            var num2 = num;
            
            ```
            
            - 重新赋值 => 变量引用用的是同一个对象
            ```
            var obj1 = new Object();
            var obj2 = obj1;
            obj1.name = 'coolfe';
            console.log(obj2.name); // coolfe
            
            ```
            
            - 传递参数
            > 访问变量有按值和按引用两种方法
            > **参数只能按值传递**
            
            ```
            function setname (obj) {
	            obj.name = 'coolfe';
            	obj = new Object();
	            obj.name = 'setname'
	            console.log(obj.name); // setname
            }
            var person = new Object();
            setname(person);
            console.log(person.name); // coolfe
            
            ```
            **当在函数内重写 obj 的时候，这个变量引用的是一个局部变量，在函数执行完毕后销毁**
            （17.02.03)                    
            
- 作用域
    - 延长作用域链(?)
        - try-catch 语句的 catch 块
        - with 语句
    - 查询标识符
    > 从当前的位置向上逐级查询匹配项，局部环境没有找到，会沿作用域往上搜索，一直追溯到全局环境的变量对象
- 垃圾收集
> 局部变量只在函数执行的过程中存在，在函数中使用变量，直到函数执行结束。

- 管理内存
> 确保占用最少的内存让页面获得更好的性能
> 优化内存占用的最佳方式就是执行中的代码只保存必要的数据，没用的数据将其设置为 null = 解除引用

（17.02.05)  

---
### 第五章：引用类型（一种数据结构）
> 引用类型的值（对象）是引用类型的一个实例

- object 类型
    - 创建
    ```
     var person = new Object();  // 可以写成  var person＝{ }
     person.name = "coolfe";
     person.age = 24;
         
     var person = {
     name : "coolfe",
     age : 24   //最后一个属性不能添加逗号，导致 IE7 以前版本错误
    }
         
    ```
    －　访问属性
    ```
    person.name  == person["name"] //访问的属性以字符串的形式放在方括号里面
    ```

- Array 类型 
    - 创建
    ```
    var colors = new array( [length] | [content]);
    ```
    - 操作 
        - 栈方法 （LIFO - Last-in-first-out）
            - push() //添加到数组末尾，增加长度
            - pop() // 移除最后一个，减少长度
        - 队列方法（FIFO - First-in-first-out）
            - shift() //移除第一个，减少长度
            - push()
            - unshift() //添加到数组前端，增加长度
        - 重排序方法
            - reverse() //反转顺序
            - sort() // 升序排列
        - concat() // 创建当前数组副本，添加新数组在副本末端，返回新构造数组
        - slice(起始位置，结束位置) // **返回起始和结束位置之间的项，但不包括结束位置的项**
   （17.02.06)
        - **splice()**
        ```
            splice(0,2) // 删除第一项的位置 和 要删除的项数
            splice(2,0,"red") // 起始位置，要删除的项数，插入的项
            splice(2,1,"red") //　起始位置，要删除的项数，插入的项
        ```
        －　位置方法
            －indexOf() // 查找的项，查找起点位置的索引
            - lastIndexOf() // 数组末端开始查找,第二个参数为当前数组索引
        （17.02.08) 
        ```
            var num = [1,2,3,4,5,6,7,8,9,1,2,3,4,5,6];
            console.log(num.indexOf(5,8)) // 13
            console.log(num.indexOf(5,1)) // 4
            console.log(num.lastIndexOf(5,3))  // -1
            console.log(num.lastIndexOf(5,4)) // 4
            console.log(num.lastIndexOf(5,14)) //13
        ```
        - other (不深入)
            - every()
            - filter()
            - forEach()
            - map()
            - some()
            - reduce()
            - reduceRight()
- Date 类型
（17.02.09)
```
var now = new Date();
console.log(now.getTime())  // 1486820460396
console.log(now.getDate()) // 11
now.setDate(12)
console.log(now.getDate()) //12
```

- RegRxp 类型 (pass)
- Function 类型
    - 函数末有分号

    ```
    function sum(a,b) {
        return a + b;
        }
    var other  = sum // 访问函数指针，而非执行函数
    ```
    - 函数声明和函数表达式
        - 解析器会优先读取函数声明到最前面
    - 函数内部属性
        - arguments: 类数组，包括传进函数的所有参数
            - callee 属性
            ```
            function factorial(num){
                if(num <= 1){
                    return 1;
                } else {
                return num * factorial(num - 1)
                }
            }    
            ```
            ```
            function factorial(num){
                if(num <= 1) {
                    return 1;
                    } else {
                    return num * arguments.callee(num - 1)
                    }
                }    
            ```
            
        - this
    - 函数的属性和方法
        - length 属性  // 接收参数个数
        - prototype 属性（下章介绍）
        - call 方法  //改变函数的调用对象
            - 传递给函数的参数必须逐个列举
        - apply 方法 //改变函数的调用对象
            - apply(改变后的调用这个函数的对象), 空代表调用全局对象： window
            
    - 基本包装类型
    **包装类型，才能让我们看起来在一个普通的字符串上调用方法。实际上是生成了包装类型的一个实例，然后调用了这个方法**
    ```
    var a = "this is a test"
    a.color = "red"
    console,log(a.color) //undefined
    ```
    不能为基本类型添加属性和方法
    （17.03.26)
    

    
                
        
            
            
        
        


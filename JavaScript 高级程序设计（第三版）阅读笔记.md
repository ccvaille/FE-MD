# JavaScript 高级程序设计（第三版）阅读笔记

标签（空格分隔）： 前端

---

### 第一章 JavaScript 简介
- 组成
    - ECMAScript 
    - DOM(文档对象模型)，提供访问和操作网页内容的方法和接口
    - BOM（浏览器对象模型），提供与浏览器交互的方法和接口

### 第二章 使用 JavaScript
- none

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
                    - \\: \
                
        - Object：对象或 null
        
        ---
        （17.01.23）
        


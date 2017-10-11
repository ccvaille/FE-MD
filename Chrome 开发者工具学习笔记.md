# Chrome 开发者工具学习笔记

### 打开
- F12
- Ctrl + Shift + I (WINDOW)
- Cmd + Opt + I (MAC)
- 页面右击 - “检查”

### 了解面板
- 设备模式
    - 测试响应和设备特定的可视窗口
- Elements(元素面板)
    - 实时编辑 DOM ，查看样式
- Console(控制台面板)
    - 使用命令行
- Sources(源代码面板)
    - 断点调试 JS
    - Continue：继续执行代码，直至遇到另一个断点
    - Step over（逐语句）：逐行执行，以了解每一行如何操作当前的变量。当你的代码调用另一个函数的时候，调试器不会跳到那个函数的代码中去，其焦点还是当前的函数，而 Step into 则相反
    - Step into（逐过程）：和逐语句类似，但是点击逐过程会在函数调用时,令调试器将执行转到所调用的函数声明中去
    - Step out：当使用逐过程进入某个函数内部后，点击该按钮会跳过该函数声明的剩余部分，调试器会将执行过程移动到其父函数中
    - Toggle breakpoints：切换断点启用、禁用状态，同时保证各自的启用状态不会受到影响
- Network(网络面板)
    - 请求和下载的资源文件
- Performance(性能面板)
    - 查看性能
- Memory(内存面板)
    - JavaScript CPU分析器
    - 内存堆区分析器
- Application(资源面板)
    - 管理数据(Cookie,img,font,css,Web SQL...)
- Security(安全面板)
    - 安全证书

### 配置 DevTools
- 打开设置
    - F1
    - 右侧三目 - Settings
- 打开命令菜单
    - Ctrl + Shift + P
    - Cmd + shift + P
- 面板标签重新排序
    - 直接拖动
- **设备模式**
    - 按住 Shift 键然后拖动鼠标可以模拟双指缩放手势
- 抽屉式选项卡(Esc 控制开启或关闭)
    - Animations 动画检查器    
    - Console 控制台
        - $0: 当前鼠标选中元素
        - console.table()
        ```
        console.table([{a:1, b:2, c:3}, {a:"foo", b:false, c:undefined}]);
        console.table([[1,2,3], [2,3,4]]);
        ```
        ```
        console.log("%cThis will be formatted with large, blue text", "color: blue; font-size: x-large");
        ```
        - ctrl + L: 清除控制台
    - Coverage 查看代码覆盖率
    - Network conditions 配置网络条件
    - **Remote devices 远程安卓设备**
        - chrome://inspect
        - 安卓设备
        - 设备有安装 Google 浏览器
    - Rendering 渲染设置
    - Search 搜索字符串和文件
    - Sensors 模拟移动传感器
    - What's New


### 參考链接
- https://developers.google.com/web/tools/chrome-devtools/
- https://www.w3cplus.com/tools/how-to-use-chrome-devtools-like-a-pro.html
- http://wiki.jikexueyuan.com/project/chrome-devtools/debugging-javascript.html
- http://wiki.jikexueyuan.com/project/chrome-devtools/using-the-timeline.html

# Chrome Dev Tools 初探

### 箭头按钮
- 选择页面上面的元素
### 手机图标
- 移动端预览
### Elements:功能标签页
- 可以实时预览修改后的标签样式
### Console:控制台
```
var obj = {name: 'coolfe',age: 12}
keys(obj) // ["name","age"]
values(obj) // ["coolfe", 12]
console.error('error')
console.warn('warn')
```
### Sources:资源页面
-  Sources: 项目的资源文件（css,js）
-  Content scripts ：一些插件和浏览器本身的资源和文件
-  Snippets ：片段代码，右击 run 运行
###Network:网络请求标签页
- 页面加载的 js，css，img，json
###Timeline 
- 显示JS执行时间、页面元素渲染时间
### Application
- 列出所有的资源，HTML5的 Database， LocalStore，可以对存储的内容进行编辑和删除
###Profiles
- 查看 CPU 的执行时间与内存占用
### Security
- 查看网站的安全性，有效证书
### Audits
- 分析页面性能








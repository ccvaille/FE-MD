## Udacity - React
- 命令式代码告诉 JavaScript 如何执行每个步骤。
- 对于声明式代码，我们告诉 JavaScript 我们希望实现什么结果，让 JavaScript 处理每个步骤。
- React 是声明式代码，因为我们编写代码来声明我们想要什么，React 负责处理声明的代码，并执行所有的 JavaScript/DOM 步骤来实现我们期望的结果
- React 中的数据流总结
在 React 中，数据仅朝一个方向流动，即从父组件流向子组件。如果数据在兄弟子组件之间共享，那么数据应该存储在父组件中，并同时传递给需要数据的两个子组件。
- Array 的 .map() 方法
- Array 的 .filter() 方法

```
const musicData = [
    { artist: 'Adele', name: '25', sales: 1731000 }, // "25 by Adele sold 1731000 copies"
    { artist: 'Drake', name: 'Views', sales: 1608000 },
    { artist: 'Beyonce', name: 'Lemonade', sales: 1554000 },
    { artist: 'Chris Stapleton', name: 'Traveller', sales: 1085000 },
    { artist: 'Pentatonix', name: 'A Pentatonix Christmas', sales: 904000 },
    { artist: 'Original Broadway Cast Recording', 
      name: 'Hamilton: An American Musical', sales: 820000 },
    { artist: 'Twenty One Pilots', name: 'Blurryface', sales: 738000 },
    { artist: 'Prince', name: 'The Very Best of Prince', sales: 668000 },
    { artist: 'Rihanna', name: 'Anti', sales: 603000 },
    { artist: 'Justin Bieber', name: 'Purpose', sales: 554000 }
];

const albumSalesStrings = musicData.map(album => `${album.name} by ${album.artist} sold ${album.sales} copies`);

console.log(albumSalesStrings);
```
```
const musicData = [
    { artist: 'Adele', name: '25', sales: 1731000 },
    { artist: 'Drake', name: 'Views', sales: 1608000 },
    { artist: 'Beyonce', name: 'Lemonade', sales: 1554000 },
    { artist: 'Chris Stapleton', name: 'Traveller', sales: 1085000 },
    { artist: 'Pentatonix', name: 'A Pentatonix Christmas', sales: 904000 },
    { artist: 'Original Broadway Cast Recording', 
      name: 'Hamilton: An American Musical', sales: 820000 },
    { artist: 'Twenty One Pilots', name: 'Blurryface', sales: 738000 },
    { artist: 'Prince', name: 'The Very Best of Prince', sales: 668000 },
    { artist: 'Rihanna', name: 'Anti', sales: 603000 },
    { artist: 'Justin Bieber', name: 'Purpose', sales: 554000 }
];


const results = musicData.filter(album => album.name.length <= 25 && album.name.length >= 10);

console.log(results);
```

```
const names = ['Michael', 'Ryan', 'Tyler'];

const shortNamesLengths = names.filter( name => name.length < 5 ).map( name => name.length );
```

- React.createElement( /* type */, /* props */, /* content */ );
    - type – 字符串或 React 组件

    - 可以是任何现有 HTML 元素字符串（例如 ‘p’、‘span’ 或 ‘header’），或者你可以传递 React 组件（稍后我们将使用 JSX 创建组件）。
props – 为 null 或一个对象

    - 这是 HTML 属性的对象以及关于该元素的自定义数据。
content – null、字符串、React 元素或 React 组件

    - 你在此处传递的任何内容都将为所渲染元素的内容。包括纯文本、JavaScript 代码、其他 React 元素等。

- 无状态函数式组件
```
class Email extends React.Component {
  render() {
    return (
      <div>
        {this.props.text}
      </div>
    );
  }
};
const Email = (props) => (
  <div>
    {props.text}
  </div>
);
```

- 生命周期
  - componentWillMount() // 插入 DOM 之前立即调用
  - componentDidMount() // 插入 DOM 之后立即调用
  - componentWillUnmount // DOM 移除之前立即调用
  - componentWillRecieveProps // 即将接收全新的 Props 时调用

- 添加到 DOM 中
  - 当组件正在被添加到 DOM 中时，这些生命周期事件被调用：

```
constructor()
componentWillMount()
render()
componentDidMount()
```

- 重新渲染-rendering
  - 当组件正在重新渲染到 DOM 时，这些生命周期事件被调用
```
componentWillReceiveProps()
shouldComponentUpdate()
componentWillUpdate()
render()
componentDidUpdate()
```

- 从 DOM 中删除
  - 当组件正在从 DOM 中被删除时，以下生命周期事件被调用
```
componentWillUnmount()
```


```
{this.state.screen === 'list' && (
  <div>List<div>
)}
```


## Udacity - React-Router
- BrowserRouter
- Link
  - <Link to="/about">About</Link>
- Route
  - <Route path="/" exact render={()>{component 有参数}}></Route>
  - <Route path="/create" component={<CreateContact>}></Route>

## 项目
  - https://github.com/udacity/reactnd-project-myreads-starter

## 参考链接
- https://reacttraining.com/react-router/
- https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Logical_Operators#Short-Circuit_Evaluation
- https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_Expressions
- https://www.meteor.com/
- http://todomvc.com/
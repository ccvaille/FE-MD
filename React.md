## React
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
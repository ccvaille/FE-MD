# ES6
- let
    - 使用 let 声明的变量可以重新赋值，但是不能在同一作用域内重新声明
- const
    - 使用 const 声明的变量必须赋初始值，但是不能在同一作用域内重新声明，也无法重新赋值
- 模板字面量
    - `${expression}`
    - `my name is ${name}`
- 解构
```
const point = [10, 25, -34];
const [x, y, z] = point; // 要将对象中的属性存储到其中的变量
console.log(x, y, z); // 10 25 -34
```
- 对象字面量简写法
    - 如果属性名称和所分配的变量名称一样，那么就可以从对象属性中删掉这些重复的变量名称
```
let gemstone = {
  type,
  color,
  carat,
  calculateWorth() { ... }
};
```

- for...of 循环（用于循环访问任何可迭代的数据类型）
```
const digits = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];

for (const digit of digits) {
  console.log(digit);
}
```

##  test
```
const things = ['red', 'basketball', 'paperclip', 'green', 'computer', 'earth', 'udacity', 'blue', 'dogs'];

// const one = things;
// const two = '';
// const three = '';
const [one,,,two,,,,three,,] = things;

const colors = `List of Colors
1. ${one}
2. ${two}
3. ${three}`;

console.log(colors);
```
```
const circle = {
  radius: 10,
  color: 'orange',
  getArea: function() {
    return Math.PI * this.radius * this.radius;
  },
  getCircumference: function() {
    return 2 * Math.PI * this.radius;
  }
};

let {radius, getArea, getCircumference} = circle;

getArea()
```
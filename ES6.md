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

-  展开运算符(...)
```
const primes = new Set([2, 3, 5, 7, 11, 13, 17, 19, 23, 29]);
console.log(...primes);
```

- 剩余参数（...）
```
function sum(...nums) {
  let total = 0;  
  for(const num of nums) {
    total += num;
  }
  return total;
}

function average(...nums) {
    if(nums.length === 0) return 0;
    let sum = 0;
    for(let num of nums){
        sum += num;
    }
    return sum / nums.length;
}  
```

- 箭头函数
  - 删掉关键字 function
  - 删掉圆括号
  - 删掉左右花括号
  - 删掉关键字 return
  - 删掉分号
  - 在参数列表和函数主体之间添加一个箭头（=>）
  - 对于普通函数，this 的值基于函数如何被调用。对于箭头函数，this 的值基于函数周围的上下文。换句话说，箭头函数内的，this 的值与函数外面的 this 的值一样。

- 默认函数参数
```
function greet(name = 'Student', greeting = 'Welcome') {
  return `${greeting} ${name}!`;
}

greet(); // Welcome Student!
greet('James'); // Welcome James!
greet('Richard', 'Howdy'); // Howdy Richard!
```

- 使用 class、super 和 extends 创建子类时, super 必须在 this 之前被调用
```
class Vehicle {
	constructor(color = 'blue', wheels = 4, horn = 'beep beep') {
		this.color = color;
		this.wheels = wheels;
		this.horn = horn;
	}

	honkHorn() {
		console.log(this.horn);
	}
}

class Bicycle extends Vehicle{
    constructor(color,wheels = 2, horn = 'honk honk'){
        super(color);
        this.wheels = wheels;
        this.horn = horn;
    }
    honkHorn(){
        super.honkHorn();
    }
}
```
- 集合: ES6 中的全新内置对象

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
# css-doodle
- 下载
```
npm install css-doodle
```
- Grid
    + range
        * 1-16
        * default: 1*1
        * 5 {x|,} 7  // row {x|,} column
- Selector
    + :doodle | :host 
    + @even
    + @odd
    + @nth(n)
    + @at(x,y)
    + @row(n)
    + @col(n)
- Functions
    + @index() // return index
    + @row() // return row number
    + @col() // return column number
    + @pick(v1,v2,…) // random pick a value
    + @rand(start[,stop][,step]) //return a random from range of numbers
    + shape(name [,v1,v2…]) // return a css shape 
 - 参考链接
    + http://yuanchuan.name/css-doodle/
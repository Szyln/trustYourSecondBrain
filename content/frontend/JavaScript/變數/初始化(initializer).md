# 初始化(initializer)
宣告後**賦值**的動作，宣告後沒有初始化的 const 是不能使用的
```js
var a;		// 未初始化
let b;		// 未初始化
const c;	// 未初始化

console.log(a);		// undefined
console.log(b);		// undefined
console.log(c);		// error
```

#js #variable #scope
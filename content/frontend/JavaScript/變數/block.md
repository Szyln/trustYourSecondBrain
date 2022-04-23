# block(javascript)
[block(javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block)
[[Scope]]
[Closure(閉包)](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Closures)

## Syntax
- 用大括號包起來
- 可以有 label（選用）
- 常在 if else, for 時使用

### Block Statement
```javascript
{
	陳述_1
	陳述_2
	...
	陳述_n
}
```
### Labelled Block Statement(optional)
```javascript
LabelIdentifier: {
	陳述_1
	陳述_2
	...
	陳述_n
}
```


## [[Scope]]判定
### 非嚴格模式
```javascript
// 不推薦這樣使用

var x = 1;

{
  var x = 2;
}

console.log(x); // 非嚴格模式的話 block 不會形成作用域，x = 2
```
### 嚴格模式
```javascript

let x = 1;

{
  let x = 2;
}

console.log(x); // 嚴格模式下，使用 let 會形成作用域，x = 1 
```

#js #variable #scope
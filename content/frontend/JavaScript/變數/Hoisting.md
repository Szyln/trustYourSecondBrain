# 提昇 Hoisting
- function 跟 var **宣告**會被提升到**該作用域**的頂部
- [[初始化(initializer)]]（賦值）之後就不會 Hoisiting
- 發生的時間點 [[Execution Context]] 的 Creation Phase
- 在 Execution Phase 發生之前，電腦記憶體會先分配給 function, var 的宣告（lexical declaration: let, const, function expression 沒有）

## var 的 hoisting
var 的 hoisting 只有在**賦值之前**有效果
```javascript
console.log(a);	// 不會輸出 not defined，而是輸出 undefined 
var a = 1; 
console.log(a); // 輸出 1
```
hoisting 的效果可以解讀成
```javascript
var a; 			// hoisting
console.log(a);	// log undefined
var a = 1; 		// 賦值
console.log(a); // 輸出 1
```
## function 宣告的 hoisting
function 的 hoisting 會將宣告提到作用域最頂端
```js
fn();					// log "hi"
function fn( {			// hoisting
	console.log("hi");
})
```

## 不會 hoisting 的部分(lexical declaration)
- let
- const
- function expression

```js
fn();						// error
let fn() = function() {		// hoisting
	console.log("hi");
}
```

#js #variable #scope
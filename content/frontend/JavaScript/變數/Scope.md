# Scope 作用域
[Scope(作用域)](https://developer.mozilla.org/en-US/docs/Glossary/Scope)
有三種作用域

## 類型
- Global Scope
- Function Scope
- [[Block]] Scope

|作用域類型|var|let|const|
|-|-|-|-|
|Global|O|O|O|
|Function|O|O|O|
|Block|X|O|O|

## Global Scope
Global Scope 的變數，在哪裡都可以讀取
```js
var age = 14;
let name = "Sam";
const height = 150;

function myName() {
	console.log(name);
}

myName();		// log "Sam"
```

## Function Scope
Function Scope 的變數，只能在函數內執行
```js
function myName() {
	var age = 14;
	let name = "Sam";
	const height = 150;
	
	console.log(name);
}

myName();			// log "Sam"
console.log(name);	// error
```

## [[Block]] Scope
Block Scope 的變數，只能在 block (loop, if)裡面讀取
使用 var 會全域污染
```js
var x = 1;
for (var i = 0; x < 10; x++) {
	console.log(x);
}
console.log(x);			// x = 10 全域污染
```

#js #variable #scope
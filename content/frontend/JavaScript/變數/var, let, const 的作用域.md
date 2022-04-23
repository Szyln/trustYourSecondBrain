---
title: "var, let, const 的作用域"
tag: 
- 
---
# let, const, var 的差異
[【直播記錄】JavaScript 那個 let, const, var 到底差在哪？](https://www.youtube.com/watch?v=FGdKdn_CnWo)
[block(javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/block)

|比較內容|var|let|const|
|-|-|-|-|
|[[block]] 內使用造成全域污染（不形成作用域）|O|X|X|
|顯示在 windows 上 |O|X|X|
|受非同步影響|O|X|X|
|hoisting|O|X|X|
|[[暫時性死區(TDZ)]]|X|O|O|
|再宣告（re-declaration）|O|X|X|
|再指派（re-assignment 賦值）|O|O|X|
|未[[初始化(initializer)]]就使用|O|O|X|




## function
function 會形成作用域，var 不會全域污染
````javascript
// var 作用域在程式碼寫完的當下就確定了
var a = 1;

function fnA() {
	console.log(a);	// fnA 叫 a 的話 a = 1
}

function fnB() {
	var a = 2;		// fnB 重新宣告 a 後，在 fnB 裡面使用都是 2
	fnA();			// fnA 叫 a = 1
	console.log(a);	// fnB 叫的話 a = 2，
}

console.log(a)		// 全域叫的話 a = 1，不受 fnB 內部宣告影響
````


## [[block]]
- 在 block 裡面使用 var 不會形成作用域，會有全域污染問題
- block 內使用 let **會**形成作用域，不會全域污染([[use-strict 嚴格模式]])
### var
````javascript
{
	var a = 3;		// var 不會形成作用域，會全域污染（非嚴格模式）
}
console.log(a);		// log 3
````
### let
````javascript
{
	let a = 3;		// var 會形成作用域，不會全域污染（嚴格模式）
}
console.log(a);		// not defined
````
### 非同步行為的狀況
#### var
setTimeout 屬非同步行為，實際執行時間點會**在所有事件結束後**
```javascript
for (var i = 0; i < 10; i++) {
	setTimeout(() => {
		console.log(i);
	}, 0);
} // log 十次 10
```
#### let
let 的作用域只有在這個迴圈內，不會受到非同步影響
```javascript
for (let i = 0; i < 10; i++) {
	setTimeout(() => {
		console.log(i);
	}, 0);
} // log 0 到 9
```

## 重複宣告的狀況
- var 可以被重複宣告，會有 [[Hoisting]] 狀況
- let 不行，會有錯誤提示
### var
var 可以重複宣告，會 hoisting，作用域內若在宣告前被呼叫，不會產生錯誤提示
```javascript
function fn(a) {
	console.log(a);	// 2.log 1
	var a = 2;		// 3.重複宣告
	console.log(a);	// 4.log 2
}
fn(1);				// 1.在外部先指定 a = 1
```

### let
let 不能重複宣告，不會 hoisting，作用域內若在宣告前被呼叫，**會**產生錯誤提示（[[暫時性死區]]）
```
// let 在被宣告前呼叫的話
Cannot access 'a' before initialization
```
會產生暫時性死區，不能執行
```javascript
function fn(a) {
	console.log(a);	// 2.暫時性死區，log 錯誤提示不能執行
	let a = 2;		// 3.不可重複宣告，不能執行
	console.log(a);	// 4.不能執行
}
fn(1);				// 1.外部指定 a = 1
```



## const 與 let 不同之處
````javascript
// 可重複賦值
let a = 1;
a = 2;        // 可
````
````javascript
// 不可重複賦值
const a = 1;
a = 2;        // 不可
````

## [[物件傳參考]]
const 如果碰上 object 的話，單純修改裡面的內容是可以的
但直接改 const 成其他物件是不行的（物件傳參考）
```javascript
const a = {
	name: "卡斯伯",
}; 

a.name = "Ray";		// 可
```
```javascript
const a = {
	name: "卡斯伯",
}; 

a = {
	name: "ray",
}; 					// 不可
```


#js #variable

  


---
title: "this"
tag: 
- 
---
# this

## 目錄
- this 的幾種狀況
	- simple call （不太會這樣用）
	- object 的 function（最常用）
	- 不同物件中的同個函數
	- 陷阱題
		- object 中還有 object
		- Object 裡面的 function 硬要呼叫全域 function
		- callback function


## 特性
- this 是[[函數的隱藏的參數]]之一
- 指向會變動
-  ** function 是從哪裡宣告的，就是指誰**（ES6 的 this 參照[[4.箭頭函式 arrow function]]）
- 主流框架都會用到

## 情況
看 function 從哪調用

||函數|物件的函數|
|-|-|-|
|this 指向|全域|物件|

### 不太會這樣用：simple call

function 在全域中，function 中的 this 指向全域
```js
var someone = '全域';
function callSomeone() {
  // 呼叫全域的變數：simple call
  console.log(this.someone);	// 指 global
}
callSomeone();
```

### 最常用的：object 裡的 function

function 在 object 中，function 中的 this 指向 object 

```js
var obj = {
  someone: '物件',
  callSomeone() {
    console.log(this.someone);	// 指該物件
  }
}
obj.callSomeone();
```

### 不同物件的擁有同名的函數 

例如由 [[Constructor]] 建立的 instance，每一個物件的參考（[[物件傳參考]] ）不一樣，事實上並不是同一個
```js
var obj = {
  someone: '物件',
  callSomeone() {
    console.log(this.someone);	// 指該物件
  }
}

var obj2 = {
  someone: '物件2',
  callSomeone()      // 語法糖省略 key
}
obj2.callSomeone();  // 指向 obj2

console.log(obj.callSomeone() === obj2.callSomeone());	// false
```

### 陷阱題

#### Object 中還有 Object

```js
var wrapObj = {
  someone: '外層物件',
  callSomeone(),          // wrapObj 的 function
  innerObj: {
    someone: '內層物件',
    callSomeone(),        // innerObj 的 function
  }
}
wrapObj.innerObj.callSomeone();
```

#### Object 裡面的 function 硬要呼叫全域 function

callSomeone 還是全域的 funciton

```js
var obj3 = {
  someone: '物件 3',
  fn() {
    callSomeone(); // 通常平常不會這樣去取用 this
  }
}
obj3.fn();
```

#### callback function：避免用

使用 callback function（像是在forEach裡），大部分就是把一個定義好的 function 簡化放到 callback funciton 裡面
所以他還是一個全域的 function

```js
var obj4 = {
  someone: '物件 4',
  fn() {
    setTimeout(function () {
      console.log(this.someone);    // simple call
    });
  }
}
obj4.fn();
```


#js #vue #advanceJs
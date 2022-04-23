---
title: "Function 簡寫語法糖"
tag: 
- 
---
# Object 內的 function 簡寫
原本的[[物件]]字面值的屬性都是以 [[Key-Value Pair]] 的形式出現，ES6 的語法糖中， function 可以如下簡寫：
## 原本寫法
```js
funName: function() {
	return this;
};
```
## ES6 語法糖
```js
funName() {
	return this;
};
```
## 注意：與 [[4.箭頭函式 arrow function]] 不同
`this` 指向不同，需注意，不該與語法糖混為一談
```js
funName: () => {
	return this
};
```

#js #function #advanceJs 
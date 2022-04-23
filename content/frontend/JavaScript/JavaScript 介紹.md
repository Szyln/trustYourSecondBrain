---
title: "JavaScript 介紹"
tag: 
- 
---
# JavaScript 介紹
- JavaScript 是由 [[ECMA]]-Script 寫成的**標準**，可以被任何程式語言寫出來，由瀏覽器來實現對應的引擎
- 最有名的標準更新為ECMA2015(ES6)

> python, c++, php 是由 C 語言寫成
>[[Strongly Weakly type Language]]

## 特性
屬於 [[Single-thread]] 語言，一次只能處理一件事
```js
// sync(Synchronous) code 同步
console.log('a');
console.log('b');

// log a
// log b
```
利用 [[Event Queue]] 可以製造時間差
#js #intro
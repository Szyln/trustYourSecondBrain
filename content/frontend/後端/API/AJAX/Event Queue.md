---
title: "Event Queue"
tag: 
- 
---
# Event Queue
JS 屬於 single-[[thread]]	的語言，一次只能處理一件事

Event Queue 利用時間差做出類似可以處理很多事的效果

## 非同步的語言
但 JS 裡面也有非同步的語言，他們屬於 WebAPI
- 計時器
- Ajax
- Promise

## 
```js
console.log("a");
function run() {
	console.log("b");
}
setTimeOut(run, 0);		// 產生一個 Queue 等 0 秒執行 run()
console.log("c");

// log 的順序為
// a -> c -> b
```

#js #event #ajax #async #callstack
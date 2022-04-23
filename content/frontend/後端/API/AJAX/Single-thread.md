---
title: "Single-thread"
tag: 
- 
---
# Single-thread
[[JavaScript/介紹/JavaScript]] 屬於 [[Single-thread]] 語言，一次只能處理一件事
```js
// sync(Synchronous) code 同步
console.log('a');
console.log('b');

// log a
// log b
```

## Event Queue
可利用 [[Event Queue]] 可以製造時間差

## Async code
用 Web API 達成，JS 本身做不到，是由網頁瀏覽器來實現
- setTimeout()
- addEventListener

## [[Promise]]
#js #event #ajax #async #promise 
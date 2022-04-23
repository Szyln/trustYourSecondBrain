---
title: "其餘參數 Rest Perameters"
tag: 
- 
---
# 其餘參數 Rest Perameters
設定 function 在導入之前可以為**不特定數量的參數**，並且將他們視為陣列來處理

```js
function f(a, b, ...theArgs) {
  // ...
}
f(1, 2, 3, 4, 5, 6 ,7);
```

## 範例
在 [[Math Object]] 的功能中，max 就有這個特性
```js
// 應用的範例
cosole.log(Math.max(2, 20, 200, 2000)); // log 2000
// 在 max 的參數中，可以填入任意數量的參數，
```
#js #function
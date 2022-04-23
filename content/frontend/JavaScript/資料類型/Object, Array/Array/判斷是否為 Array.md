---
title: "判斷是否為 Array"
tag: 
- 
---
# 判斷是否為 Array
> 之後讀到物件導向會講更多

因為 typeof 只能判斷是否為 object，使用 `Array.isArray(該陣列)`來辨識是 object 中的陣列或物件

```js
let ary = [1, 2];
console.log(typeof ary); // 無法分辨，顯示 object
console.log(Array.isArray(ary)); // true  

```
#js #dataType #object
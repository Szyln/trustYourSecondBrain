---
title: "陣列的循環 for, forEach, map"
tag: 
- 
---
#  陣列的循環
- for
- forEach({callback function})
- map()
- [[判定]]

## 比較
|特性|for|forEach()|map()|
|-|-|-|-|
|更動原陣列|O|X|X|
|分別 log 出更改後的元素|X|O|-|
|return 更動後新陣列（存到變數）|X|X|O|
|中斷循環|O|X|-|


## for
```js
let ary = [1, 2, 3];
for (let element of ary) {
	console.log(element + 1);
}
// 分別輸出 2
// 分別輸出 3
// 分別輸出 4
```

## forEach
```js
Array.forEach(function(){})
```
-  function 的執行次數取決於該 array 的元素數量
- 若想要得到修改後的 array 可用 .push 到新的 array 中 → 或使用 .map()
- 不可中斷

### function 預設的參數
`.forEach()` 的參數會是一個 function ，該 function 的設參數有三個
```js
Array.forEach(function(item, index, array) {
	// .....

})
```
-   item：輪到的元素
-   index：輪到的 [索引]，可省略
-   array：執行的 array，不會因為 function 內修改元素內容而變化，可省略、少用


## map()
不改原陣列，新陣列存進變數
```js
let newArray = oldArray.map(function(item{
	return item;
})
```


#js #dataType #object
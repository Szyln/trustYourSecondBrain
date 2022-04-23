---
title: "find()"
tag: 
- 
---
### find
回傳陣列的第一個符合條件的元素
```js
// 三個 element 都是物件
// 都有個一個屬性 isPerson 判斷是否為人
let ary = [dog, cat, 王小明];
let firstPerson = ary.find(element => {
	return element.isPerson == true;
})
console.log(firstPerson); // 王小明
```

>[[條件判定陣列的元素]]

#js #dataType #array #object 
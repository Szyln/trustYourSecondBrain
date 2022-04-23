---
title: "Object"
tag: 
- 
---
# 物件 Object
- [[物件字面值]]內可以包含多個屬性 (properties)
每個屬性通常都是以 [[Key-Value Pair]] 的形式出現，value 可以為其他的[[原始資料類型 Primitive Data Types]]，或是 [[Function]]、[[Array]]、甚至是 [[Object]]，另外在 ES6 有規範了 [[Function 簡寫語法糖]]
```js
let home = {
	name : 'Mary',
	{key或屬性} : {值value},
	properties,
	method,
}
```

## [[物件傳參考#傳參考 Call By Reference]]
物件與陣列皆為傳參考特性(reference data types)，宣告變數時皆為讀取他的記憶體，而非值本身
```js
let people = [A, B];
let students = people;

people.push(C);

console.log(people, students); 
// 傳參考特性 log 兩個都是 [A, B, C]
```
## 讀取物件
-   點記法 Dot notation
-   中括號 Bracket notation
```js
person.name;
person[’name’];
```

## 新增物件
-   person.name = ‘Mary’;
-   這個 key 尚未存在也沒關係，也不用在前面加 let

## 修改
-   同修改變數，可以直接更新，或是 += 去計算也可
-   person.name = ‘Jane’;
-   dogsNum += 1;

## 刪除
```js
delete person.age;

person.age;			// undefined
```
#js #objecy 
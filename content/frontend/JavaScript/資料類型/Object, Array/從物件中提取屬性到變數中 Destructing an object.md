# 從物件中提取屬性到變數中 Destructing an object
>[[Destructing Assignment]]


- 長相像有大括號的變數
- 可以把物件的屬性提出來使用，不用重複用點記法點屬性
```js
let {} =						 // 防失智搜尋用
let {提出來用的物件屬性1, 提出來用的物件屬性2 ...} = 物件;

```
```js
let Sam = {
	name: 'Sam',
	age: 25,
	friends: {
		friendName: 'Mike',
	}
}

// 舊作法
// let name = Sam.name;
// let age = Sam.age;
// let firendName = Sam.friends.name;

// 新作法
let {name, age} = Sam;			// {} 批次處理
let {firendName} = Sam.friends;
```

#mango #js #object 
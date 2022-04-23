---
title: "Constructor"
tag: 
- 
---
 # Constructor Function
可以重複生成相似物件的功能

## 使用規則
```js
function Person(name, age, height) {	// 大寫開頭
	console.log(this);					// 指向 object
	this.name = name,
	this.age = age,
	this.height = height
	this.sayHi = function() {
		console.log(this.name + " hi.")
	}
}

let Sam = new Person("Sam", 10, 100);	// new 建立空物件


```
- 使用大寫開頭（[[命名習慣 Naming Convention]]）
- 使用 [[new]] 字(reserved words)


### 如果不使用 new 的話
```js
function Person(name, age, height) {
	console.log(this);					// 指向 window
	this.name = name,
	this.age = age,
	this.height = height
}

let Sam = Person("Sam", 10, 100);		
console.log(Sam);						// undefined


```

## 記憶體
用 Constructor 製作出來的物件，每一個都是不同的記憶體空間，但有些物件的屬性不希望一直複製，會使用 [[Prototype]]

#js #advanceJs #object #oop
# Class

- 改善 [[Prototype Inheritance]] 的繁複寫法的語法糖，本質不變
- 可以理解為：類、模版
- 可以簡化 [[Constructor]] 跟 [[Prototype]] 的建立

## 會用到的功能
### 原 Class
```js
class 原本的 {
	constructor(參數們) {
		// 物件實例的屬性們
	}
	
	// prototype
	函數() {
		// 共用的功能
	}
}
```
### 繼承的 Class
```js
class 繼承的 extends 原本的 {
	constructor(參數們, 新的參數們) {
		super(原本的參數們);			// 離散數學的名詞，super 代表母集合
		// 新物件實例的屬性們
	}
	
	// prototype
	新函數() {
		// 新的 class 共用的功能
	}
}
```
## [[Prototype Inheritance#原有的]] 改寫
[[Constructor]] 與 [[Prototype]] 直接寫在 [[Class]] 裡面
```js
class Person {
	constructor(name, age, height) {
		this.name = name,
		this.age = age,
		this.height = height
	
	}
	
	// Prototype
	sayHi() {
		console.log(this.name + " says hi.");
	}
}

let Mike = new Person('Mike', 20, 150);
let Sam = new Person('Sam', 21, 190);
console.log(Mike.sayHi() === Sam.sayHi())	// true
```

## [[Prototype Inheritance#繼承的]] 改寫
繼承的 [[Class]] 使用 extends 來連結到原本的
```js
class Student extends Person {						// 從 Person 繼承
	constructor(name, age, height, major, grade) {	// 新增兩個新的參數
		super(name, age, height);					// 繼承的部份用 super
		this.major = major,							// 新的屬性
		this.grade = grade
	
	}
	
	// 新的 Prototype（舊的自動繼承）
	study() {
		console.log(this.name + " is studying.");
	}
}
```

#js #advanceJs #object #oop
# Prototype
一個物件，包含共用的 properties 和 methods，可以供所有繼承的[[物件實例]](instances) 讀取（都放在同一個記憶體）

```js
// Constructor
function Person(name, age, height) {	// 大寫開頭
	console.log(this);					// 指向 object
	this.name = name,
	this.age = age,
	this.height = height
	
	// 從 constructor 拿出，放到 prototype 來共用
	// this.sayHi = function() {
	//	console.log(this.name + " hi.")
	//}
}

Person.prototype.sayHi = funciton() {	// 新增 prototype 屬性
	console.log(this.name + " says hi.")
}

let Sam = new Person("Sam", 10, 100);	// new 建立空物件
let Mike = new Person("Mike", 12, 200);	// new 建立空物件

console.log(Sam.sayHi === Mike.sayHi)	// true，都是從 prototype 讀取


```

## [[Prototype Inheritance]]
用語法糖代替來寫
## [[Class]]
#js #advanceJs #object #oop
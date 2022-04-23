---
title: "static：僅給 class 內部用的變數"
tag: 
- 
---
# Static 的 properties, methods
Static 的屬性與方法僅供 class 內部做呼叫，不會拿來給物件實例做呼叫
```js
class Circle {
	static pi = 3.1415926535;							// static properties
	static getAreaFormula() {							// static methods
		console.log("r * r * 3.14");
	};
	
	constructor(radius) {
		this.radius = radius
	}
	
	getArea() {
		return this.radius * this.radius * Circle.pi;	// 呼叫 static
	}
}

let cl = new Circle(10);
console.log(cl.getArea());
```

#js #advanceJs #object #oop #class
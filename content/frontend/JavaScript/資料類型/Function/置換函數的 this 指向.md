# 置換函數的 this 指向
這些是函數都可以使用的 methods

## 常見 methods
- bind
- call
- apply

## bind
綁定 [[this]] 指向，需要把 bind 過的內容丟到一個新的變數內使用

```js
let Sam = {
	name: 'Sam',
	age: 25
}

function getAge() {

	// 此 this 是 simple call，指全域
	console.log(this.age);	
}

// bind getSamAge() 的 this 指到 Sam
let getSamAge = getAge.bind(Sam);
getSamAge();
```

## call
比 bind 更實用，可以直接置換 this 為指定的物件

```js
let Sam = {
	name: 'Sam',
	age: 25
}

function getAge() {

	// 此 this 是 simple call，指全域
	console.log(this.age);	
}

// call this 置換為 call 的參數
getAge.call(Sam);

```
### 函數的其他參數
如果指定的(`getAge`)函數有多個參數，也可以在 `call` 的參數後方加入
```js
let Sam = {
	name: 'Sam',
	age: 25
}

function getAge(height) {	// 有自定參數

	// 此 this 是 simple call，指全域
	console.log(this.age);
	console.log(height);
}

// call this 置換為 call 的參數
getAge.call(Sam, 100);		// 指定完 this 後呼叫即可

```

## apply
[[置換函數的 this 指向#call#函數的其他參數]] 的狀況中，把其他參數放到陣列即可
```js
let Sam = {
	name: 'Sam',
	age: 25
}

function getAge(height, weight) {	// 有自定參數

	// 此 this 是 simple call，指全域
	console.log(this.age);
	console.log(height);
	consol.log(weight);
}

// apply this 置換為 apply 的參數，自定參數要放到陣列中
getAge.apply(Sam, [100, 40]);		// 指定完 this 後呼叫即可

```

#js #function #advanceJs 
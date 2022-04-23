---
title: "Callback Hell"
tag: 
- 
---
# Callback Hell
![](https://miro.medium.com/max/721/0*iiecmuTLPBqbxd5V.jpeg)
早期沒有 [[Promise]] 功能的時候，要用很多個 callback 功能來達成，但功能一複雜就會形成 [[Callback Hell]]
```js
function getData(name) {
	setTimeout(() => {
		return {
			name,
			age: Math.floor() * 20,
			major: "CS"
		};
	}, 2000);
}
console.log('start');

// 執行的時候 let 還得不到結果，log undefined
let data = getData('Wilson');
console.log(data);

console.log('end');
```
## 要得到結果的話……
```js

function getData(name, callback) {
	setTimeout(() => {
	// 改成 callback
		callback( {
			name,
			age: Math.floor()) * 20,
			major: "CS"
		});
	}, 2000);
}

function getMovies(age, callback) {
	if(age < 12) {
		setTimeOut(() => {
			callback('cartoon');
		}, 1500);
	} else {
		setTimeout(() => {
			callback('teen movies');
		}, 1500);
	}
}

console.log('start');

// 串越多個資料就要不停的 nest 下去
// callback hell
let data = getData('Wilson', (obj) => {
	getMovies(obj.age, (str) => {
		console.log(str);
	})
});
console.log(data);

console.log('end');
```

#js #api #promise #async 
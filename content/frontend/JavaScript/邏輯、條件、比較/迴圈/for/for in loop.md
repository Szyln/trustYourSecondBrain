---
title: "for in loop"
tag: 
- 
---
# for in

- array
- object 也可（[[for of loop]]不行）

```js
let Sam = {
	age: 1,
	height:100,
}

for (let i in Sam) {
	console.log(i);		// log age , log height
	console.log(Sam[i]);		// log 1 , log 100
	
}
```

#js #loop
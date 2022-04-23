---
title: "透過 Mongoose 存入 MongoDB(Save)"
tag: 
- 
---
### save Jon to DB
```js
Jon.save()
	.then(() => {
		console.log('Jon has been saved into DB');
	})
	.catch(() => {
		console.log('error has happend.');
		console.log(e)
	});
```

>加入 Error Handling：[[Error Handling 非同步的寫法]]
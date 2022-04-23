---
title: "Error Handling 非同步的寫法"
tag: 
- 
---
##  Error Handling 非同步的寫法
>- [[Mongoose]]：[[Find(Read)]]
>- [[Async（目錄）]]
```js
// routing 有用到 promise 的話：
app.get('/', async(req, res, next) => {
	try {
		let foundData = await Monkey.findOne({ name: 'Ban'});
		res.send(foundData);
	} catch(e) {
		next(e);			// 這個 error 就會傳到下一個 middleware(error handler)
	}
})

// error handler
app.use((err, req, res, next) => {
	console.log(err);
	res.status(500).send('有什麼東西出錯了，我們會儘快修復');
	// 可以在這邊提供一個表單問遇到什麼問題
})

```


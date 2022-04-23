## Error Handling 同步的寫法
```js
// routing 沒有使用 promise 的話
// error handler
app.use((err, req, res, next) => {
	console.log(err);
	res.status(500).send('有什麼東西出錯了，我們會儘快修復');
	// 可以在這邊提供一個表單問遇到什麼問題
})

// port listen
```
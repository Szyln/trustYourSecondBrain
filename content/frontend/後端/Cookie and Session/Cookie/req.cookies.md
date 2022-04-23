# req.cookie
使用 cookie，需要安裝 middlewarea 模組 [[cookie-parser]]
可以拿來取得 [[res.cookie]] 傳過來的 [[Cookie]]	
```js
app.get('/', (req, res) => {
	console.log(req.cookies);
	let { name } = req.cookies;
	res.send(`${name}, Welcome to the homepage.`)
})
```

#js #backEnd #server #storage #expressJs
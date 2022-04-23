---
title: "Request Handling(Express)"
tag: 
- 
---
# Request Handling (Express)
- 跟 node.js（ [[Server 建立]]）比起來簡化很多
- 處理 [[HTTP request]]([[狀態碼]])

---
- [[Routing]]
- [[send 和 sendFile 回應(express)]]


處理各種網路請求的內容
```js
// Express 的寫法
app.get('/', function (req, res) {	// 參數：網址，建立 server
	res.send('Hello World')			// 顯示文字
})
```
可以設定不同的網址不同反應
```js
// Express 的寫法
app.get('/', function (req, res) {			// 
	res.send('home page')					// 
})

app.get('/product', function (req, res) {	// 不同網址
	res.send('product page')				// 
})
```
#js #advanceJs #library #framework #nodeJs #backEnd #module #expressJs #npm #server #routing 
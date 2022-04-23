# 建立 Server
用[[內建模組(Node.js)]] 來建立 Web server，不太容易，通常會用 [[Express.js]] 來建立
```javascript
const http = require('http');						// 內建模組

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {	// 建立 server，提供兩端交換的內容
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World');
});

server.listen(port, hostname, () => {				// 監聽 port
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

## 步驟
- 匯入內建模組 `http`
- middleware（到 express再談，[[Express 的 CSS 樣式環境建置 (Serving a Static File)]]）
- 建立 Server
- 監聽 [[Port]]

### http 模組
```js
const http = require('http');
```

### createServer
>通常會用 Express.js 來建立：[[Request Handling(Express)]]

建立 [[Server]]
處理對方的請求跟回應 ([[request]]), [[response]]) 之間交換的內容

```js
const server = http.createServer((req, res) => {
});
```
#### response
可以使用 `res` 參數，寫入要送出去的內容
```js
const server = http.createServer((req, res) => {

	res.write('Hello user');		// write：回應一行字
	res.write('<h1>title</h1>')		// 也可以寫 html，也可以寫很多行
	res.end();						// 要記得
});
```
>[[send 和 sendFile 回應(express)]]

#### request
也可以使用 `req` 參數，處理傳過來的資料

>- parse：[[物件不要傳參考的時候：深層、淺層拷貝#深層拷貝]]
>- [[url(module)]]

```js
const server = http.createServer((req, res) => {
	if(req.url == '/') {

		fs.readFile(path.join(__dirname, 'index.html'), (err, data) => {
			res.writeHead(200, { 'Content-Type': text/html });
			res.write(data);
			res.end();
		})
		res.writeHead(200, { 'Content-Type': text/html });
		res.write('<h1>This is Homepage.</h1>');
		res.end();
	} else {
		let parsedURL = url.parse(req.rul);	// string 轉 array
		res.write('Hello,' parsedURL.pathname);
		res.end();
	}
	console.log(res.url);				// 這個會 log 到終端機
	let parsedURL = url.parse(req.url)	// string 轉 array
})

```

>[[fs (File System)]]>[[writeFile]]
>[[Port]]

#### 一些規則
```js
res.statusCode = 200;
res.setHeader('Content-Type', 'text/plain');
```

```js
res.writeHead(200, {'Content-Type': 'text/plain'});
```
### 監聽請求
建立完 [[Server]] 之後，要設定一個負責接收請求的 [[Port]]，並且監聽他有沒有任何請求傳過來
```js
// 參數 port：設定一個接收請求的 port
// 箭頭函數：開始監聽後會出現的提示
server.listen(port, hostname, () => {
});
```
#js #advanceJs #library #framework #nodeJs #backEnd #module #npm #server
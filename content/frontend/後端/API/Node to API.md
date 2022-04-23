# Node to API
[[Fetch#需要有 Authorization Key 才能使用的 API]]
>Node 是不支援 [[Fetch]] 功能的；[[Node to API - node fetch]]
## 終端
```
npm init
npm install express ejs nodemon 
(不用安裝 mongoose)
```
## app.js
### 匯入
```js
// app.js
const express = require('express');
const app = express();
const ejs - require('ejs');
```
>[[Express.js]]
>[[EJS]]
### api 資料
```js
// api key 
const key = 'api 提供的金鑰' ;
```

### [[Middleware(express)]]
[[後端/Node.js/模組/內建模組/app.set()]]
```js
// middleware
app.use(express.static('public'));
// 這是啥
app.set('view engine', 'ejs');
```
>[Use EJS with Express](https://github.com/mde/ejs/wiki/Using-EJS-with-Express)

### [[Routing]]
```js
// request handdling
app.get('/', (req, res) => {
	res.render('index.ejs')
})

app.get('/:city', (req, res) => {
	let { city } = req.params;
	let url = `API 給的 endpoint`
	
	// get request made by node.js
	https.get('url', (response) => {
		console.log('statusCode:', response.statusCode);
		console.log('headers:', response.headers); 
		
		response.on('data', (d) => {
			// string to array
			let dJson = JSON.parse(d);
			console.log(dJson);
			// 氣溫的單位不太一樣，調整一下
			let { temp } = dJson.main;
			// 需要額外寫個 kToC() function
			let newTemp = kToC(temp);
			res.render('weather.ejs', { dJson, newTemp });
		});

		}).on('error', (e) => {
			console.error(e);
		});
})
```
>- [[從物件中提取屬性到變數中 Destructing an object]]
>- [[類型轉換#JSON]] JSON.parse(string)：轉成 array
>- [[EJS#在 HTML 內使用變數：Routing for pattern]]
> - [[Node to API - node fetch]]
### 使用 API
[[Fetch]] 是不支援的，有兩種作法
- [https.get](https://nodejs.org/docs/latest-v15.x/api/https.html#https_https_get_options_callback)
- [[Node to API - node fetch]]
### listen
```js
app.listen(3000, () => {
	console.log('server is running on 3000')
})
```


## ejs
[[EJS#在 EJS 檔案內撰寫 HTML]]
```html
<!-- head 裡面 -->
<!-- 點記法要點誰可以用 postman 查看 -->
<title><%= djs.name %> - ( <%= djs.sys.country%> )</title>

<!-- body 裡面 -->
<h1><%= djs.name %> Weather Now</h1>
```
# Signing a Cookie
對 Cookie 進行簽署，辨識客戶端是否更改了 [[Cookie]] 之後傳回來

>- 需要使用 [[cookie-parser]]
>- 配合 [[secret 的變數設定]]

```js
const cookieParser = require('cookie-parser');
// cookie-parser 的 middleware
// （不建議）填入任意字串，伺服器傳送的時候會將 cookie 內容用這個字串做簽名
// （建議）使用 process 配合 dotenv 做隱藏
app.use(cookieParser(process.env.SECRET));


app.get('/getSignedCookie', (req, res) => {
	res.cookie('name', 'Sam');
	res.send('Cookie has been send.');
})
```

## 讀取有簽署的 cookie
如果客戶端更改了有簽署的內容，`req.singedCookies` 就無法辨識內容了
>[[req.cookies]]
```js
app.get('/', (req, res) => {
	console.log(req.cookies);				// 這樣寫不會出現有簽署的內容
	console.log(req.signedCookies)	// 這樣才會顯示
})

app.get('/', (req, res) => {
	let {name} = req.signedCookies;
	res.send(name);
}
```

#js #backEnd #server #storage #expressJs
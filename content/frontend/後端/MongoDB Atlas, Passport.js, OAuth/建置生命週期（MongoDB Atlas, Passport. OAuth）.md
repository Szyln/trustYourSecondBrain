# 建置生命週期（MongoDB Atlas, Passport. OAuth）
>- [ ] 為什麼是叫 index.js 而不是 app.js？
>- [ ] `app.use(express.json());` 是做什麼的？
>[What Does `app.use(express.json())` Do in Express?](https://masteringjs.io/tutorials/express/express-json)

## 匯入
>- [[匯入模組]]
>- [[dotenv（使用 env 變數）]]
>- [[Express 匯入]]
>- [[Mongoose 建置]]


```js
// index.js
// import express, app, mongoose, dotenv
// dotenv.config();
// 匯入 passport.js ([[Configure Strategy]])
// 匯入 auth-route
// 匯入 profileRoute
```

## 數據庫連接
>- [[利用 Mongoose 連上 MongoDB]]
>	- [[MongoDB Atlas]]
```js
// 連結的 URI 要存到 env 
mongoose.connect(process.env.DB_CONNECT).then(() => {
		console.log('成功連上 mongodb atlas');
	}).catch((err) => {
		console.log(err);
})
```

## [[Middleware(express)]]
>需設定的有
>- [[EJS with Express 的基本設定]]
>- [[body-parser]]：表單（登入表單）
>- [[cookie-session]]：關掉頁面可以不用重新登入（應該不用）
>- [[Sessions in Passport]]：同上
>- [[auth-route]]：設定 local 或是 OAuth 登入
>- [[profile-route]]：登入後畫面的設定
```js
// ejs
app.set('view engine, 'ejs);
// body-parser
app.use(express.json());
app.use(express.urlencoded({extend: true}));
```


## Nav 
>需要先完成 [[OAuth]] 的部份
>[[req.user]]
```js
app.get('/', (req, res) => {
	res.render('index', { user: req.user });
})
```


## Listen
![[Express Life Cycle 生命週期#^cafd08]]
# secret 的變數設定
為了加密內容，secret 不該直接寫入字串，需要將其隱藏，需透過下列三項來達成
- [[Node]] 內建全域物件：[[process(node)]]
- [[dotenv（使用 env 變數）]] 模組：使用與設定 env 變數 
- [[node 的 gitignore 設定]]：隱藏 env 檔案

---

## 在 .env 設定 secret 
```
// .env 裡面
SECRET=THISISMYTOPSECRET
```
> 可以在 [[express-session]], [[Signing a Cookie]] 中使用

## 使用 env 的變數
```js
app.use(session({
	// 透過 dotenv 模組存入一個 env 變數做使用
	secret: process.env.SECRET,
	resave: false,
	saveUninitialized: false
}))
```



#js #node #expressJs #session #npm #module 
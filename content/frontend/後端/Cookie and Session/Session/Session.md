---
title: "Session"
tag: 
- 
---
# Session
> 需使用 [[express-session]] 模組
- [[Cookies and Sessions]] 在 [[Cookie]] 無法加密且容量較小
- 會傳送到客戶端的只有一個 ID（connect.sid）
- 用途例子：辨識是否登入
- 通常會搭配 [[Database 數據庫]]，不會只有在記憶體記錄
- 儲存系統提示用 Session：[[Flash]]

---

## req.session
```js
app.get('/', (req, res) => {
	console.log(req.session);			// 目前只有存在伺服器記憶體，伺服器關掉就會清空
})

// 認證頁面
app.get('/verifyUser', (req, res) => {
	req.session.isVerified = true;
	res.send('You are verified.');
})

// 認證完（seesion 裡面必須有 isVerified 屬性為 true）才能看到
app.get('/secret', (req, res) => {
	if (req.session.isVerified == true) {
		res.send('My secret is - I love panda.');
	} else {
		res.status(403).send('You are not authorized to see my secret.')
	}
})

```
## 進階
connect.sid


#js #backEnd #server #storage #expressJs #session
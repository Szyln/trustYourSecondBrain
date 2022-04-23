## middleware(Authenticate Requests)
- Middleware：請求包含 `/auth`？
	- 否：繼續執行 Life Cycle
	- 是：進到 [[auth-route]] 模組

```js
// 在 index.js 匯入
const authRoute = require('./routes/auth-route');

// middleware
// 檢查每次進來的 request 有沒有 /auth ，有的話就執行 authRoute
// authRoute 若被執行，就會辨識應該要回應 /login 還是 /google
app.use('/auth', authRoute);
```
>[[指定特定 Route 之前的 Middleware（Route 前面）]]
# Cookie
- 也是一個儲存資料的地方（類似[[Storage]]）
- 但跟 [[Storage]] 不同的是，他是為了讓伺服器端讀取的，前者反之
- 客戶端發送請求 [[HTTP request]] 時候，[[Cookie]] 就會跟著發出去，[[Storage]] 不會
- [[Key-Value Pair]]
- 可以透過 [[Postman]] 或是 Devtool -> 儲存空間查看
- 可以從 Devtool 修改 cookie -> [[Signing a Cookie]]

---

- [[res.cookie]]：傳送 cookie 給瀏覽器儲存
- [[req.cookies]]：讓瀏覽器讀取 [[res.cookie]]
- [[Signing a Cookie]]


#backEnd #node/express #server #storage 
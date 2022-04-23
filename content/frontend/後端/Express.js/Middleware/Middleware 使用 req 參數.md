---
title: "Middleware 使用 req 參數"
tag: 
- 
---
## Middleware 使用 req 參數
詳細之後會談
```js
app.use(function (req, res, next) {
	req.method = "POST";	// 把對方的請求強制改成 post
  next();
})
```
---
title: "404 Not Found"
tag: 
- 
---
# 404 Not Found
使用 [[Routing#Routing for all]] 的方法，將任意輸入的網址都導到[[狀態碼]] 404 頁面

```js
// * 或 /* 都可
app.get("*", (req, res) => {
	res.status(404);					// 狀態碼 404
	res.sendFile(path.join(__dirname, "error.html"));						// 設定的 404 頁面
})
```
#backEnd #node/express #node/npm
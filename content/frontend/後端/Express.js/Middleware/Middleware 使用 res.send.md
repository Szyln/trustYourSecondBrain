---
title: "Middleware 使用 res.send"
tag: 
- 
---
## Middleware 使用 res.send
大型專案很實用的功能，可以在還沒有 [[Routing]] 的情況下 send
```js
app.use(function (req, res, next) {
	res.send('Middleware');
  next();
})

app.get('/', (req, res) => {
	res.send('homepage');
})

// 網頁顯示會出錯
// 終端：Cannat set headers after they are sent to the client（res.send 不能送兩次）
```
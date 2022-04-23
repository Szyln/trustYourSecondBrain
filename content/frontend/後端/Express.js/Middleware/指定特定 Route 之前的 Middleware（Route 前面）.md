## 指定特定 Route 之前的 Middleware（Route 前面）
跟 [[Routing]] 的功能類似，也可以限定使用
```js
app.use('/student', (req, res, next) => {
	res.send('Middleware');
  next();
})

app.get('/', (req, res) => {
	res.send('homepage');
})

// 網頁顯示會出錯
// 終端：Cannat set headers after they are sent to the client（res.send 不能送兩次）
```

>跟[[Error Handling（Routing 後面）]]： [[Error Handling 非同步的寫法]]長得有點像
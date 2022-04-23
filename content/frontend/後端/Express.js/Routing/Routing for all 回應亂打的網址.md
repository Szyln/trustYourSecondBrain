## Routing for all 回應亂打的網址
這個要放在 [[Routing#Request Handling]] 的最後面，才不會什麼網址都跑這個
```js
app.get('*', (req, res) => {
	res.send('頁面不存在');
})
```
- [[404 Not Found]]

#js #npm #node #expressJs #server #routing 
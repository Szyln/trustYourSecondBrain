# 透過 Postman 刪除數據庫資料(API)
>[[HTTP request]]：DELETE

除了用 Postman 發出 delete 請求之外，也可以用[[表單更新數據庫既有資料]]的方法刪除

```js
app.delete('/students/delete/:id', (req, res) => {
	let { id } = req.params;
	Student.deleteOne({ id })
		.then(meg => {
			console.log(meg);
			res.send('刪除成功');
		}).catch(e => {
			console.log(e);
			res.send('刪除失敗');
		})
})
```


#js #npm #node #expressJs #mongoose #database #form #ejs #backEnd #crud
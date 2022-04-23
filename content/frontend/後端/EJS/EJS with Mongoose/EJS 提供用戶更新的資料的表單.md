## EJS 提供用戶更新的資料的表單
```js
// 提供更新用的表單給客戶
app.get('/students/edit/:id', async (req, res) =>
	let { id } = req.params;
	try {
		let data = await Student.findOne({ id });
		if ( data !== null ) {
			res.render('studentEdit.ejs', { data });
		} else {
			res.send('該 ID 尚未被登錄');
		}
	}
);
```

```html
// POST
<!-- 使用變數＋method-override -->
<form action="/students/edit/<%= data.id %>?method=DELETE" method="POST">
	<label for="id">ID:</label>
	<!-- value 抓出數據庫資料顯示 -->
	<input type="number" id="id" name="id" value="<%= data.id %>">
	<!-- 其餘 input 省略 -->
	<input type="submit">
</form>
```

#database/mongoose #form #crud

 #backEnd #node/npm #gulp #html #node/ejs #node/express 
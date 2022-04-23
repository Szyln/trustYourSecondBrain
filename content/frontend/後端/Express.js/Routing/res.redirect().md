---
title: "res.redirect()"
tag: 
- 
---
# res.redirect ()
重導到其他頁面
```js
// 收到 put 更新後，更新數據庫
app.put('/students/edit/:id', async (req, res) => {
	// 因為網頁上的 merit, other 沒有多包一層一個物件，需要先提出來
	let { id, name, age, merit, other } = req.body;
	try {
		res.send('感謝您，資料已更新');
		let data = await Student.findOneAndUpdate(
			{ id },
			{ id, name, age, scholarship:{ merit, other } },
			{
				new: true,
				runValidators: true,
			}
		);
		// 導到其他畫面
		res.redirect('/students/${ id }');
		
	} catch {
		res.render(reject.ejs);
	}
})
```

>顯示指定頁面可能會想用：[[編譯 EJS 樣板 res.render()]]
---
title: "API 提供特定資料"
tag: 
- 
---
# API 提供特定資料
>[[使用 Routing for pattern 顯示特定數據庫物件]]
```js
app.get('student/:id', async (req, res) => {
	let { id } = req.params;
	try {
		let data = await Student.findOne({ id });
		if( data !== null) {
			res.send(data);
		} else {
			res.status(404);  // 
			res.send({ message: '該 ID 尚未被登錄' };
		}
	} catch(e) {
		res.send('資料取得失敗');
	}
})
```
>[[狀態碼]]

#api #js #restfulapi #api #crud #database #json 
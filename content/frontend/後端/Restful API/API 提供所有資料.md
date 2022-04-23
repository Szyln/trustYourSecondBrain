---
title: "API 提供所有資料"
tag: 
- 
---
# API 提供所有資料
[[將數據庫資料顯示於網頁]]
>[[send 和 sendFile 回應(express)#回應物件的話]]
```js
// /students/（已登入學生表）
app.get('/students', async (req, res) => {
	try {
		let data = await Student.find();
		res.send(data);
	} catch {
		res.send({ message: '找不到學生資料' });
	}
})
```

之後就可以用 [[Postman]] 發出 GET 請求了
#api #js #restfulapi #api #crud #database #json 
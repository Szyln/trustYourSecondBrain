# API 提供新增資料的管道
>[[表單資料存入數據庫]]

不用提供表單了，用戶會直接透過 [[Postman]] 輸入資訊

```js
// routing for query
app.post('/students', (req, res) => {
	// req.body 是表單資訊
	let { id, name, age, merit, other } = req.body;
	// create an object
	let newStudent = new Student({
		id, name, age, scholarship: { merit, other },
	});
	
	// 存入數據庫
	newStudent.save()
		.then(() => {
			res.send({ message: '提交成功' })
		}).catch(e => {
			res.status(404);  // 有更好的狀態碼
			res.send(e);
		})
}) 
```

[[使用 Postman 發出表單請求]]

#api #js #restfulapi #api #crud #database #json 
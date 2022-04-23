# API 提供刪除資料的管道
這個功能通常不會提供給用戶使用（這什麼恐怖的功能）

- [[API 提供刪除資料的管道#刪除一項]]
- [[API 提供刪除資料的管道#刪除全部]]

## 刪除一項
> 同 [[透過 Postman 刪除數據庫資料]]
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

## 刪除全部
>[[Delete]]
```js
app.delete('/students/delete/:id', (req, res) => {
	let { id } = req.params;
	Student.deleteMany({})
		.then(meg => {
			console.log(meg);
			res.send('全部資料刪除成功');
		}).catch(e => {
			console.log(e);
			res.send('刪除失敗');
		})
})
```
#api #js #restfulapi #api #crud #database #json 
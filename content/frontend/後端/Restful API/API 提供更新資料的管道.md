---
title: "API 提供更新資料的管道"
tag: 
- 
---
# API 提供更新資料的管道
>[[獲得請求後更新數據庫資料]]

- [[API 提供更新資料的管道#PUT]]
- [[API 提供更新資料的管道#PATCH（還沒搞懂）]]


## PUT 
一樣不用提供表單（[[EJS 提供用戶更新的資料的表單]]），也不用提供 edit 頁面（透過 HTTP Verb 即可）
```js
// 收到 put 更新後，更新數據庫
app.put('/students/:id', async (req, res) => {
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
				overwrite: true			// 只有 put 需要設定
			}
		);
		res.send('感謝您，資料已更新')
		
	} catch {
		res.status(404);
		res.send('更新失敗')
	}
})
```

>[[使用 Postman 發出表單請求]]，使用 PUT 請求即可

## PATCH（還沒搞懂）
只有部分更新
>[[Class]]

使用 findOneAndUpdate 的時候，因為有設定 [[Update with Validators]]，所以會沒辦法直接運行
只動 age, merit 
```js
class newData {
	constructor() {};
	// 只用 prototype 的功能
	// 不是 scholarship：newData
	setProperty(key, value) {
		if(key !== 'merit' && key !== 'other') {
			this[key] = value;			// 使用時會指向物件實例
		} else {
			this[`scholarship.${key}`] = value
		}
	}
}

// 收到 put 更新後，更新數據庫
app.patch('/students/:id', async (req, res) => {
	let { id } = req.parmas;
	let newObject = new newData();
	for (let property in req.body) {
		newObject.setProperty(property, req.body[property] );
	}
	console.log(newObject);
	try {
		res.send('感謝您，資料已更新');
		let data = await Student.findOneAndUpdate(
			{ id },
			newObject,
			{
				new: true,
				runValidators: true,
			}
		);
		console.log(data);
		res.send('感謝您，資料已更新')
		
	} catch {
		res.status(404);
		res.send('更新失敗')
	}
})
```
#api #js #restfulapi #api #crud #database #json 
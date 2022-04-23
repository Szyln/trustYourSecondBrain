---
title: "Update"
tag: 
- 
---
---
title: "Update"
tag: 
- 
---
## Update (Mongoose)
[[MongoDB CRUD#Update]]
```js
// 操作都一樣
model.update();
model.updateOne();
model.updateMany();
```
```js
// 直接設定更改前後的內容
Student.updateOne(
	{
		name: "Jon"
	},
	{
		name: "Sam"
	}
)
	.then((meg) => {		// log 錯誤訊息
		console.log(meg);
	})
```
> [[Find(Read)#Find and Update]] 可以更快速的查看

#database #nosql #mongoose #mongodb #json 
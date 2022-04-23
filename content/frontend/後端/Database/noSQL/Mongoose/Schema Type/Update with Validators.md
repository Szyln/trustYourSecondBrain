---
title: "Update with Validators"
tag: 
- 
---
# Update with Validators
[[Validators]] 只有在一開始 set 的時候會做驗證，後續跑像是 [[Update]] 的功能就不會再驗證了，要加入一個內容 `runValidators`

> [[Find(Read)#Find and Update]]
```js
Student.findOneAndUpdate(
	{ name: '原本的'},
	{ name: '更新的' },
	// 以下可以放入 option
	{ 
		new: true,				// log 更新的項目
		runValidators: true		// 重跑一次 validators
	},
)
```


#database #nosql #mongoose #mongodb #validators #crud
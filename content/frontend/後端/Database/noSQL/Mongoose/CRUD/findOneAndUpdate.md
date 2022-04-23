---
title: "findOneAndUpdate"
tag: 
- 
---
## findOneAndUpdate
>[[Update]] 會回傳整個列表，不會回傳更改過後的特定內容
```js
model.findOneAndUpdate(condition, update, options)
```
> [[Validators]] 預設不會重跑，options 可以加入 [[Update with Validators]] 來重跑
```js
Student.findOneAndUpdate(
	{ 尋找的屬性(找出相符的特定物件) },
	{ 更改後的內容（要更改的部份） },
	{
		new: true,				// log 更新的項目
		runValidators: true		// 重跑一次 validators
	}
).then((meg) => {
	console.log(meg)
})
```
>`useFindAndModify` 在第六版已經不建議加入，可以不用放了

## 使用 [[Instance Method]] 做出同樣效果
```js
// instance method
studentSchema.methods.addage = function() {
	this.age++;
}

Student.findOne({ name: 'Eric'})
	.then((data) => {
		data.addAge();
		console.log(data);
	}).catch(e => {
		console.log(e);
	})
```

#database #nosql #mongoose #mongodb #json #crud 
# Delete(Mongoose)
```js
model.deleteOne();
model.deleteMany();

// 組合技
model.findOneAndDelete();
```

```js
Student.deleteOne({ "scholarship.merit": { $gte: 1500 } })
	.then((meg) => {
		console.log(meg)		// log 刪完的 model，刪掉誰看不到
	})
```
```js
Student.findOneAndDelete({ "scholarship.merit": { $gte: 1500 } })
	.then((meg) => {
		console.log(meg)		// log 刪掉的內容
	})

```



#database #nosql #json #npm #node
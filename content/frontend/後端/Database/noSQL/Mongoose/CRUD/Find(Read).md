---
title: "Find(Read)"
tag: 
- 
---
# Mongoose Find (Read)
```js
Model.find()				// 回傳 array with object
Model.findOne()				// 回傳單一 object
Model.findOneAndUpdate()	// 回傳更新過後的特定內容
```
## find
```js
Student.find({}).then(data => {
	console.log(data);
})
// 執行後會在終端看到搜尋結果
// 不論幾個 object 符合條件，都會包在 array 裡面
```
## findOne
```js
Student.findOne({ name: 'John' })
	.then(data => {
		console.log(data);
})
// 執行後會在終端看到搜尋結果
// 回傳一個 object
```
> `find` 還有很多[連合技](https://mongoosejs.com/docs/api/model.html)
> - [[findOneAndUpdate]]}}


> 也可以配合 [[MongoDB CRUD#比較 comparison operator]] 來做更複雜的篩選
> ```js
> Student.find({ "scholarship.merit" : {$gte: 1500} }).then((data) => {
> 	console.log(data);
> })
> ```

>[[EJS 使用 Mongoose 取得數據庫資料作為變數]]

> 不一定一定要串 then，如果沒有打算運用該物件做什麼事的話：[[製作登入、註冊介面]]

#database #nosql #mongoose #mongodb #json #crud 
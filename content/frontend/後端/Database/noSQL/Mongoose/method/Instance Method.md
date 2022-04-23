# Instance Method
[[Mongoose Method]]

[[Create#Define a Schema]] 之後，可以設定 [[Instance Method]] 供 model 使用

>有個很像的 [[Static Method]] 之後再提

>用instance method改變資料數據後，需加入this.save()
## 建立 Instance Method
```js
// create an instance method
studentSchema.methods.totalScholarship = function() {
	// this 指的是物件
	return this.scholarship.merit + this.scholarship.other;
}

// create a model
const Student = mongoose.model('Student', studentSchema);
```
## 搭配 [[Find(Read)]] 使用
### 對單一物件使用
```js
// find 會回傳 array，要用 findOne (回傳object)
Student.findOne({ name: 'Eric' })	
	// data 是符合條件的該物件
	.then(data => {	
	// 搭配 instance method 使用 
		let result = data.totalScholarship();
		console.log(result);
	}).catch(e => {
		console.log('error!');
		console.log(e);
	})
```
> 第一段要注意，有用 [[this]]，不可以隨意改成[[4.箭頭函式 arrow function]]
### 批次物件使用
```js
// data 是包在 array 的物件們
Student.find({}).then(data => {
	data.forEach(oneStudent => {
		console.log(`${onestudent} has total Scholarship ${oneStudent.totalScholarship}).`
	})
})
```
### 做出 [[findOneAndUpdate]] 的效果
[[findOneAndUpdate#使用 Instance Method 做出同樣效果]]


#database #mongoose #crud 
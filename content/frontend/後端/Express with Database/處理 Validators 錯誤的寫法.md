---
title: "處理 Validators 錯誤的寫法"
tag: 
- 
---
# [[Validators]] Error Handling
Validators 的 error 要透過 crud 的 [[Promise]] (`.catch`) 來完成，Handling 成功的話回傳給網頁一個 error object

## save 的狀況
```js
// define a Schema
const monkeySchema = new mongoose.Schema({
	name: {
		type: String,
		minlength: 3,
	}
})
// create a model
const Monkey = mongoose.model('Monkey', monkeySchema);

// routing
app.get('/', async(req, res, next) => {
	try {
		// create an object：這邊假設一個不符合 validators 的物件
		let newMonkey = new Monkey({ name: 'S' });
		// save to database
		newMonkey.save()
			.then(() => {
				res.send('成功儲存資料');
			}).catch((errMessage) => {
				res.send(errMessage);
			});
	} catch(e) {
		next(e);
	}
})
```

## findOneAndUpdate 的狀況
要按照[文件](https://mongoosejs.com/docs/api.html#query_Query-findOneAndUpdate)的寫法
```js
app.get('/find', async(req, res, next) => {
	try {
		await Monkey.findOneAndUpdate(
			{ name: 'Sam' },
			{ name: 'S'},
			{
				new: true,
				runValidator: true
			},
			// 第四個參數要填入
			(error, doc) => {
				if(error) {
					res.send(error);
				} else {
					res.send(doc);
				}
			}
		)
	}
})
```
>- [[Validators]]
>- [[透過 Mongoose 存入 MongoDB(Save)]]

#mongoose #json #js #database #validators #crud #node #expressJs 
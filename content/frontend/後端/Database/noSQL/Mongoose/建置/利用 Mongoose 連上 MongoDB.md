# 利用 Mongoose 連上 MongoDB
```js
// connect to mongoDB
// 要設定連接成功或失敗的效果
// 連到一個 database（exampleDB 為例，可自訂）
mongoose.connect('mongodb://localhost:27017/exampleDB')

	.then(() => {
		console.log('Connected to MongoDB.');
	})

	.catch((err) => {
		console.log('Failed.');
		console.log(err);
	})
```

^86a132

>`mongoose.connect()`連結到名為 `exampleDB` 的 database

>原本 mongoose 5 在 mongoose.connect 有第二個參數，[已經建議刪除](https://mongoosejs.com/docs/migrating_to_6.html#version-requirements)
>```js
>{
>	useNewUrlParser: true,
>	useUnifiedTopology: true,
>}
>```

#database #json #nosql #node #mongoose
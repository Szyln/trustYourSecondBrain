# Schema Type(Mongoose)
>- [ ] 怎麼設定 primary key
- [[Create]] 的時候，需要定義資料類型
- 搭配 [[Validators]] 可以做更複雜的定義規範
## 寫法
> 記得類型要寫大寫
### 簡易寫法
```js
// app.js
const studentSchema = new mongoose.Schema({
	name: String,
	age: Number,
	major: String,
	scholarship: {
		merit: Number,
		other: Number
	}
});
```
### 可以配合 [[Validators]] 的寫法
如果要搭配更詳細的規範，就必須用這個寫法，才能寫入 [[Validators]]
```js
// 另一種寫法
cost studentSchema = new mongoose.Schema({
	name: {
		type: String
	},
	age: {
		type: Number
	}
	scholarship {
		merit: {
			type: Number
		}
		other: {
			type: Number
		}
	}
})
```


#json #dataType #nosql #mongoose 
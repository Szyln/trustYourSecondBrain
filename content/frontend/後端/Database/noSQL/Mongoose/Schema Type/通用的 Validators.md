## 通用的 Validators
所有 [[Schema Type]] 都可以用：
- [[required]]：必填
- Default：預設值

```js
// 另一種寫法
cost studentSchema = new mongoose.Schema({
	name: {
		type: String,
		required: [true, "This is Required"]
	},
	age: {
		type: Number,
		required: true,
		default: 18,
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

#database #nosql #mongoose #mongodb #validators
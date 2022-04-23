---
title: "required"
tag: 
- 
---
## required (Mongoose Validators)
值可以是：
- boolean
- array: `[true, "沒有填的時候跳出的錯誤提示"]`
- function: `function() { return this.其他欄位 > 3; }`
```js
cost studentSchema = new mongoose.Schema({
	name: { 
		type: String,
		required: [true, "This is Required"]
	},
})
```

```js
cost breakfastSchema = new mongoose.Schema({
	bacon: {
		type: Number,
		required: true
	},
	drink: {
		type: String,
		required: function() {
			return this.bancon > 3;		// 如果 bacon 點了三片以上就必須點飲料
		}
	},
})
```

#mongoose #mongodb #database #schema #validators
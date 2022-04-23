# Number 用 [[Validators]]
- Min
- Max
- Enum( 可參照[[Enum(指定 string, number)]])

```js
// define a schema
const studentSchema = new mongoose.schema({
	age: {
		type: number,
		max: 150,
		min:0,
	}
})
```

跟 [[Form]] 的 [[input#number]] 的規範很像
#database #nosql #mongoose #mongodb #validators
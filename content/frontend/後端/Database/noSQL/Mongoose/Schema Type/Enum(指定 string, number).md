# Enum（指定 string, number）
[[String 用 Validators]]
> enumerate: 枚舉

可以規範輸入的資料只能是特定字串

很像 [[Form]] 的 [[select & datalist 選單]]
```js
// define a schema
const studentSchema = new mongoose.Schema({
	major: {
		type: string,
		// 只能輸入 enum 有出現的內容
		enum: ["Chem", "Electric", "Computer Science"],
		default: "尚未選擇"
	} 
})
// create a model
const Student = mongoose.model("Student", studentSchema);
```
> 忘記過程可以看詳細：[[Create]], [[Schema Type]], [[Validators]]

## 如果輸入一個沒被規範的內容
```js
// create an object
const newStudent = new Student({
	name: ,
	age: ,
	major: 'Math'
})
// error
```


#database #nosql #mongoose #mongodb #validators
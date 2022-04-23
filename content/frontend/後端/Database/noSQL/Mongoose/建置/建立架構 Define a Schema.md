## 建立架構
### Define a Schema
如同 [[SQL create 製作表格]] create table 的動作，Mongoose 也會定義物件的 [[Schema Type]]，之後就可以 [[Create a Model]] 做使用了
```js
// app.js
const studentSchema = new mongoose.Schema({
	name: string,
	age: Number,
	major: string,
	scholarship: {
		merit: Number,
		other: Number
	}
});
```
> 如果要更複雜的定義 [[Validators]]
> 想要做些功能 [[Instance Method]]


#database #nosql #json #npm #node #odm
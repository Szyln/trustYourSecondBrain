### create a model
model 就可以當成一個 [[MongoDB]] 的 collection 用了（[[MongoDB CRUD]]）
```js
// const 變數要大寫
// model 的 string 也要大寫、單數
const Student = mongoose.model('Student', studentSchema);
// mongoose 會自動把 model 轉成複數形式
```
> 因為 [[Mongoose 建置]]時已經指定 database 為 exampleDB 了，在操作指令時就不用寫 `db.` 了
> ```js
> db.collection.{ CRUD }		// 這是 [[MongoDB CRUD]] 寫法
> model.{ CRUD }				  // 這是 [[Mongoose]] 寫法
> ```
#database #nosql #json #npm #node #odm
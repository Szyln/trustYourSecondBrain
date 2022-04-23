# 使用數據庫資料作為變數
>看完這兩段再理解就好
>- [[Mongoose]]
>	- [[Find(Read)]]
>- [[AJAX]]

在使用 [[Mongoose]] 要注意是非同步指令，需要用 [[Promise]] 寫法
```js
// 從 DB 取得資訊顯示到網頁上
app.get('/students', async (req, res) => {
	let data = await Student.find();
	res.render('students.ejs', { data });
})
```
#database/mongoose #js/promise #ajax 
#node/npm #gulp #html #node/ejs #node/express 
# POST([[Form]])
- HTML：form 標籤要設定 `method="POST"`
- [[body-parser]] 可以讓後端使用客戶填入的內容
- req.body：[[POST 表單(express)#使用用戶填入的資訊]]

## 單純收資料
```html
// index.html

// action: 資料傳送目的地
// POST: 不會顯示在網址
<form action="/formHandling" method="POST">

	// 有 name 屬性的 input 才會送到 form action 的所在地
	<label for="name">Your Name</label>
	<input type="text" id="name" name="name">

	<label for="age">Your Age</label>
	<input type="text" id="age" name="age">
	
	<input type="submit">Submit</input>

</form>
```

```js

// 回應上面的這個 index.html 檔
app.get('/', (req, res) => {
	res.sendFile(path.join(__dirname, "index.html"))
})

// 對方送出表單後的回應
app.post('/formHandling', (req, res)) {
	console.log(req.body);
	res.send("表單已送出");
}
```

>[[使用路徑的兩種寫法]]：有兩種作法
>- 單純使用[[string#string 的串接]]
>- 使用 path 模組 + [[join()]]

## 使用用戶填入的資訊
想要細部使用表單內容需要先新增一個 [[body-parser]] 模組（[[Middleware(express)]]）

```js
// 這裡就可以使用 body 的內容了
app.post('/formHandling', (req, res)) {
	// 這裡的表單資訊對應的是 html input 標籤的 name 屬性
	let { name, age } = req.body	// body 為表單資訊
	res.send(已經送出，您的名字是 ${name} 年齡 ${age} 歲`);
	
}
```
> - 很像物件的變數：[[從物件中提取屬性到變數中 Destructing an object]]
> - 學到 [[Database 數據庫]]之後會有更複雜的應用：[[Express and Mongoose]]（資料先傳到資料庫再傳回來）
> 


#js #expressJs #node #npm #form #server #routing
---
title: "GET 表單(express)"
tag: 
- 
---
## GET ([[Form]])
跟一般的請求回應一樣都是使用 `.get()` 來回應對方的表單
```html
// index.html

// action: 資料傳送目的地
// GET: 會顯示在網址
<form action="/formHandling" method="GET">

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

// 不需要 middileware, bodyParser

app.get('/', (req, res) => {
	res.sendFile(path.join(__dirname, "index.html"))
})

// GET 的表單會更改網址
// 對方送出表單後的回應
app.get('/formHandling', (req, res)) {
	let { name, age } = req.query	// query 可以 get 的讀取表單資訊
	res.send(已經送出，您的名字是 ${name} 年齡 ${age} 歲`);
}
```

#js #expressJs #node #npm #form #server #routing
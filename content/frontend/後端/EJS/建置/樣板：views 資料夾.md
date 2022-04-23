### 樣板：views 資料夾
取代一般的 html 的 ejs 檔案必須都放在 `views` 資料夾下
```js
// index.ejs 一定要在 views 資料夾下才會運作，不然會出現 error
app.get("/", (req, res) => {
	res.render("index.ejs");			// 處理該 ejs 檔
})
```

#npm #gulp #html #js #ejs #expressJs 
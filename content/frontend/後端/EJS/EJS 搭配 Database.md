## 搭配[[Database 數據庫]]
[[Mongoose]]
```js
app.get("/", (req, res) => {
	// 有個 array ，通常數據庫都會給這樣格式的資料
	const languages = [
		{ name: "python", rating: 9.5 popularity: 9.7}, 
		{ name: "java" ......}
]

	
	res.render("index.ejs", { languages });
});
```

```ejs
<% languges.forEach(lang => { %>
<tr>
	<td><%= lang.name %></td>
	<td><%= lang.popularity %></td>
</tr>
<% }) %>
```
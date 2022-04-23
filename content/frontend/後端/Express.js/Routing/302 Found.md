---
title: "302 Found"
tag: 
- 
---
# 302 Found
指原本存在，但目前已經移除
```js
app.get("/舊網頁", (req, res) => {
	res.status(302);
	res.sendFile(path.join(__dirname, "moved.html"));
})
```
```js
// 定義在 'save' 之前要做什麼事
// writeFile: 建立一個檔案，指定寫入什麼內容
studentSchema.pre('save', async function(){
	fs.writeFile('history.txt', "One data is trying to be saved.", (e) => {
		if (e) throw e;
	})
})
```

[[fs (File System)]]
#backEnd #node/express #node/npm



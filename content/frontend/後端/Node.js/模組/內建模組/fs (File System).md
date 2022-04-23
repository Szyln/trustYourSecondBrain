---
title: "fs (File System)"
tag: 
- 
---
# fs (File System)
在 JS 檔案記錄一些伺服器遭遇的事件
```js
const fs = require('fs');

// 參數是：寫入的檔案、寫入訊息、function
fs.writeFile('try.txt', 'Today is a good day.' e => {
	if (e) throw e;							// 失敗的話終端機顯示
	
	console.log('file has been written.')	// 終端機顯示
})
```
```js
fs.readFile('./try.txt', 'utf8', (e, data) => {
	if (e) throw e;
	console.log(data);
})
```

- [[writeFile]]
- [[readFile]]


[[Middleware(Mongoose)]]
[[內建模組(Node.js)]]

#js #library #framework #nodeJs #backEnd #module
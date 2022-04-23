---
title: "writeFile"
tag: 
- 
---
# writeFile

```js
const fs = require('fs');

// 參數是：寫入的檔案、寫入訊息、function
fs.writeFile('try.txt', 'Today is a good day.' e => {
	if (e) throw e;							// 失敗的話終端機顯示
	
	console.log('file has been written.')	// 終端機顯示
})
```
預設是可以在該檔案寫內容，每次使用這個功能，都會覆寫掉原本的內容


#js #library #framework #nodeJs #backEnd #module
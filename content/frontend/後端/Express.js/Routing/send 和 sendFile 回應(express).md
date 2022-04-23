---
title: "send 和 sendFile 回應(express)"
tag: 
- 
---
# 回應 html 內容 
[[Routing]] 內有更多綜合運用
## res.send()
[[Express.js#建立 server]] 中 send 可以送出純字串或是 html 都可，跟 [[node]] [[Server 建立]] 的 `write` 類似

但是只能送一行
```js
app.get('/', (req, res) => {
	res.send('<h1>homepage</h1>');
	res.send('<h2>substitle</h2>');		// 終端顯示錯誤
})
```
### 回應物件的話
>製作 [[Restful API]] 時就會使用到，傳給用戶資料讓他們做使用
```js
app.get('/', (req, res) => {
	const Sam = {
		name: Sam,
		age: 2
	}
	res.send(Sam);				// 瀏覽器顯示 JSON 格式
})
```
## sendFile()：回應 HTML 檔案
這個可以送整個 html 檔案
```js
app.get('/', (req, res) => {
	res.sendFile(__dirname + "/index.html");
})
```

>[[Module Wrapper#__dirname#使用方式]]：有兩種作法，單純使用[[string#string 的串接]]或是使用 path 模組 + [[join()]]


#js #expressJs #node #npm #form #routing 
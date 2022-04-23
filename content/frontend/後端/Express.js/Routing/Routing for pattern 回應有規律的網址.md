---
title: "Routing for pattern 回應有規律的網址"
tag: 
- 
---
## Routing for pattern 回應有規律的網址
網址尾端內容，如果是想要顯示有規律的內容（例如搜尋結果）
可以在網址尾端加入 `/:不特定內容的群組`
```js
app.get('/某個分支頁面/:分支底下的特定內容', (req, res) => {
	res.send('你要找的是' + res.params.分支底下的特定內容 + '嗎？');
})
```
#### 舉例
搜尋就可以搜不同的內容，網頁上都會顯示同樣的格式
```js
app.get('/search/:result', (req, res) => {
	res.send('你要找的是' + res.params.result + '嗎？');
})
```

>[[從物件中提取屬性到變數中 Destructing an object]] 提到可以把物件內容提取出來，增加易讀性
>```js
>app.get('/search/:result', (req, res) => {
>	let { result } = res.params;
>	res.send('你要找的是' + result + '嗎？');
>})
>```
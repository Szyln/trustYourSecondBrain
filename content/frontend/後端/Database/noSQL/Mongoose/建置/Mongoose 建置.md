---
title: "Mongoose 建置"
tag: 
- 
---
# [[Mongoose]] 建置
- npm install: express, ejs, mongoose([[npm 建置與指令]])
- import：[[取得 Node.js 裡的模組]]
- [[利用 Mongoose 連上 MongoDB]]
- [[Middleware(express)]]
- [[使用與操作 Mongoose]]
- [[Request Handling(Express)]]
- port listening

寫在 middleware 前
```js
const express = require('express');
const app = express();
const ejs = require('ejs');
const mongoose = require('mongoose');
```
```js
// middleware
app.use(express.static('public'));


app.get('/', (req, res) => {
	res.render('index.ejs');
})

app.listen(3000, () => {
	console.log("running on port 3000");
})
```



#database #json #nosql #node #mongoose
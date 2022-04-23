---
title: "body-parser"
tag: 
- 
---
# body-parser
[npm](https://www.npmjs.com/package/body-parser)
> 其實 [[Express.js]] 自帶這個模組，可以直接使用
>```js
>app.use(express.urlencoded({ extended: true }));
>```

```js
const bodyParser = require("body-parser");

// middleware 收到請求一定會被執行
app.use(express.json());
app.use(bodyParser.urlencoded(
	{ extended: true }
));
```
#form #server #routing
#backEnd #node/express #node/npm #node/ejs 
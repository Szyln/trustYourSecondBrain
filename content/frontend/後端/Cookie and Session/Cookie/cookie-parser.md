---
title: "cookie-parser"
tag: 
- 
---
# cookie-parser
[npm](https://www.npmjs.com/package/cookie-parser)
可以使用 [[req.cookies]] 的 [[Middleware(express)]] 模組

---

## npm install
```shell
$ npm install cookie-parser
```
## import
```js
const cookieParser = require('cookie-parser')
```
## 用法
```js
const express = require('express')
const cookieParser = require('cookie-parser')
const app = express()

app.use(cookieParser())

app.get('/', function (req, res) {
  // Cookies that have not been signed
  console.log('Cookies: ', req.cookies)

  // Cookies that have been signed
  console.log('Signed Cookies: ', req.signedCookies)
})

app.listen(8080)

// curl command that sends an HTTP request with two cookies
// curl http://127.0.0.1:8080 --cookie "Cho=Kim;Greet=Hello"
```


#backEnd #node/express #node/npm #server #storage #js/module #storage 
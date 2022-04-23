---
title: "Stateless Authentication(JWT)"
tag: 
- 
---
# Stateless Authentication
>[[Stateful Authentication]]

```
客戶端 --- post 登入資訊到 /api/auth/login --> 伺服器端
客戶端 <-- 認證密碼＆生成 JWT 存到客戶端（LocalStorage）-- 伺服器端
```

客戶端成功登入後，server 會將客戶資料加密，回傳給客戶端（token），存在 [[Local Storage]]（客戶端不能更動）
之後客戶端傳送請求時，會將這個 token 一併送出，server 將 token 解密認證（[[Passport.js]]），如果認證成功才會發出回應

>相關文章[以 JSON Web Token 替代傳統 Token](https://yami.io/jwt/)

---
## npm 
```shell
npm install jsonwebtoken passport-jwt passport-local
```

```js
// 匯入
var jwt = require('jsonwebtoken');
// 使用
var token = jwt.sign({ foo: 'bar' }, 'shhhhh');
```
## 優點
- 不佔用伺服器資源：token 儲存在客戶端
- 後端無權限刪除資料：token 儲存在客戶端，後端無法修改
- 擴充容易：需要時從客戶端抓過來就好，不用準備儲存空間
- 簡易：他是一串字串，有利於傳輸
- 包含使用者資料：解密就好不用去數據庫花時間抓資料
- Digitally Signed：有數位簽證功能，安全性
- 支援多種程式語言

## 缺點
- 後端不能修改內容


#session #authentication #oauth 

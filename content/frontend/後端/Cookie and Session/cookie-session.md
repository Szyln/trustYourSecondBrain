---
title: "cookie-session"
tag: 
- 
---
# cookie-session
[npm](https://www.npmjs.com/package/cookie-session)
```shell
npm i cookie-session
```

## 建置

```js
const cookieSession = require('cookie-session');
```

### middleware
>[[指定特定 Route 之前的 Middleware（Route 前面）]]
```js
// 在特定 route 使用的 middleware 之前
app.use(cookieSession({
  name: 'session',
  keys: [process.env.SECRET],

  // Cookie Options
  maxAge: 24 * 60 * 60 * 1000 // 24 hours
}))
```
>[[passport-google-oauth20 的 .env 變數]]
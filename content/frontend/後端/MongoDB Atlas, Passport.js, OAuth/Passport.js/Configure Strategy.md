# Configure Strategy
新增 config 資料夾，新增 passport.js 檔案 

## 模組設定
>- [[Passport.js]]
>- [[用資料夾管理 Mongoose models 模組]]
>- [[bcrypt#檢查密碼]]：登入時加密
```js
// config/passport.js
const passport = require('passport');
const GoogleStrategy = require('passport-google-oauth20');
const User = require('../models/user-model');
const LocalStrategy = require('passport-local');
const bcrypt = require('bcrypt');
```

### 在 index.js 匯入
```js
// index.js
// 不用 const 一個變數來存
require('./config/passport');
```
>[[建置生命週期（MongoDB Atlas, Passport. OAuth）]]

## Stretegy
- [[Configure Strategy(passport-google)]]
- [[Configure Strategy(passport-local)]]
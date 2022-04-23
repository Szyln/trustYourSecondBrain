# dotenv
[npm](https://www.npmjs.com/package/dotenv)
使用[[Cookies and Sessions]] 的時候，應該將 [[cookie-parser]] 跟 [[express-session]] 的內容加密並且隱藏

在使用 [[process(node)]] 的時候可以使用自訂的 env 變數

```shell
npm install dotenv
```

## 設定
```js
// app.js 最頂端
require('dotenv').config()
```

## 專案新增 .env 檔案
```shell
// 可以照著這個格式新增 env 變數
// 變數名=變數內容
// string 不用加 '' or ""
DB_HOST=localhost
DB_USER=root
DB_PASS=s1mpl3
```
> 這個檔案要透過 [[node 的 gitignore 設定]]隱藏
## 使用
```js
process.env.資料夾內設定的變數名
```

```js
// 對應用法
const db = require('db')
db.connect({
  host: process.env.DB_HOST,
  username: process.env.DB_USER,
  password: process.env.DB_PASS
})
```




#node #node/express  #session #node/npm #git
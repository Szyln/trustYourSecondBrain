### [[匯入模組]]
頭兩行可以發現 `app` 這個變數直接將匯入的檔案當做函數處理
```js
// app.js
const express = require('express')
const app = express()
```
#### Express.js 的匯出方式（不用自己做）
以往我們是將檔案整個[[匯出模組]]，這邊是只匯出檔案內的函數
```js
// 模組.js
exports = 函數名稱();
```
這樣匯入
```js
// app.js
const 模組 = require('./模組');
模組();
```

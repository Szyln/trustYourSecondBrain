# Babel
- JavaScript [[Compiler]]，可以將 [[JSX]] 編譯成原始的 React 寫法
- 不用特別裝，VScode



```js
let i = 1;
```


```js
const express = require('express');
const app = express();
const mongoose = require('mongoose');
const dotenv = require('dotenv');

dotenv.config();

const authRoute = require('./routes/auth-route');


mongoose.connect(process.env.DB_CONNECT).then(() => {
	console.log('成功連上 mongoDB Atlas');
}).catch((err) => {
	console.log(err);
})


```

#js/react/jsx 
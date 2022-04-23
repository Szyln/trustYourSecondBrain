---
title: "EJS with Express 的基本設定"
tag: 
- 
---
# EJS with Express
>取自[官網提供的方法](https://github.com/mde/ejs/wiki/Using-EJS-with-Express)

會用到 [[app.set()]]
```js
// import
let express = require('express');
let app = express();

// EJS 設定
app.set('view engine', 'ejs');

// routing
app.get('/', (req, res) => {
  res.render('index', {foo: 'FOO'});
});

// port listening
app.listen(4000, () => console.log('Example app listening on port 4000!'));
```
>[[app.set()]]

#node/npm #gulp #html #node/ejs #node/express 
# connect-flash
[npm](https://www.npmjs.com/package/connect-flash)
使用[[Flash]] 需要安裝的 npm 模組
```shell
$ npm install connect-flash
```

## 使用
```js
const flash = require('connect-flash');
const app = express();

// middleware: 會生成一個 req.flash 可做使用
app.use(flash());	
```

```js
// 第一種用法
app.get('/', (req, res) => {
	// 跟 session 一樣 flash 也是 key-value pair
	req.flash('success_msg', 'Successfully get to the homepage.');
	res.send('Hi, ' + req.flash('success_msg'));
})
```
#server #storage #session
#backEnd #node/express #node/npm
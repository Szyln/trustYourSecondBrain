# Flash
> 必須使用 npm 模組：[[connect-flash]]、[[express-session]]

- [[Session]] 的其中一部分
- 可以儲存一些給使用端的訊息（例如：成功、失敗提示）

---

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

#js #backEnd #server #storage #expressJs #session #npm #module 
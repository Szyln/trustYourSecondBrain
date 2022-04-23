# method-override
>[method-override](https://www.npmjs.com/package/method-override)
---
因為 html [[Form]] 不支援 [[HTTP request]] GET, POST 之外的請求，需要額外裝模組輔助

```js
const methodOverride = require('method-override');

// middleware
app.use(methodOverride('_method'));

app.put('/students/edit/:id', (req, res) => {
	console.log(req.body);
	res.send('感謝您，資料已更新');
})
```
action 的 query 可寫入`?_method=要執行的請求`
```html
<!-- method 會被蓋過 -->
<form action="/students/edit/<%= data.id %>?_method=PUT" method="POST">
</form>
```
#js #node #npm #form #database  #ejs #mongoose #backEnd 
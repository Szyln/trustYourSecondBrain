# Node to API - 使用 fetch 的狀況
>[[Node to API#Routing]]

Node 不支援 [[Fetch]] 功能，在 node 裡想要串 [[API]] 要注意，需要用 [[npm]] 再裝個 [node-fetch](https://www.npmjs.com/package/node-fetch)

```js
// 匯入 fetch
const fetch = require('fetch');

// 第一種寫法
app.get('/:city', async (req, res) => {
	let { city } = req.params;
	let url =`API 給的 endpoint`;
	
	fetch(url).then(d => d.json()).then(djs => {
		let { temp } = djs.main;
		let newTemp = kToC(temp)
		res.render('weather.ejs', { djs });
	});
});

// 第二種寫法
app.get('/:city', async (req, res) => {
	let { city } = req.params;
	let url =`API 給的 endpoint`;
	let data = await fetch(url);
	let dataJson = await data.json();
	let { temp } = dataJson.main;
	res.render('weather.ejs', { dataJson, newTemp });
});
```
## 沒有裝的話
```shell
UnhandledPromiseRejectionWarning: ReferenceError: fetch is not defined
```




#js #node #api #promise #expressJs #ejs 
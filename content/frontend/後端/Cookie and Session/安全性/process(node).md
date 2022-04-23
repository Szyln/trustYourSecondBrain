# process(node)
[javaTpoint](https://www.javatpoint.com/nodejs-process)

一個 [[Node]] 的全域物件，可以檢視目前的 platform, version 等

```js
app.get('/', (req, res) => {
	console.log(process.platform);
	console.log(process.version);
	console.log(process.env);				// 另外需要 dotenv 做使用
})
```

> [[dotenv（使用 env 變數）]]






#js #nodeJs #backEnd #session #expressJs
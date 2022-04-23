# 自製 Node.js [[模組]]
會利用到 [[Module Wrapper]] 的預設參數 [[Module Wrapper#exports require module]]

建立模組檔案（舉例 hi, bye）
```
js/
|– app.js		
|– hi.js
|– bye.js
```

```js
// hi.js
function sayHi() {
	console.log('Hi.');
}
```

```js
// bye.js
function sayBye() {
	console.log('Bye.');
}
```

如果用 Node.js 去執行 `.js` 檔的話，會把 `.js` 用 [[Module Wrapper]] 執行，可以讀取預設參數

## [[匯出模組]]
## [[匯入模組]]
## [[整合模組匯出匯入]]

#js #advanceJs #library #framework #nodeJs #backEnd #module #npm
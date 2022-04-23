# Module Wrapper
[21/11/12 現下的 Document 說明](https://nodejs.org/dist/latest-v17.x/docs/api/modules.html#the-module-wrapper)

JS 可以在瀏覽器內直接執行，但透過 Node 在終端運行時，會用 Module Wrapper 將 js 程式碼包起來再運行

```js
(function(exports, require, module, __filename, __dirname) {
	// Module code actually lives in here
});
```

所以會使全域變數都會限制在這個函式的作用域([[Scope#Function Scope]])內

>  如何使用這些參數：[[Node.js 的預設參數]]

#js #advanceJs #library #framework #nodeJs #backEnd #module 
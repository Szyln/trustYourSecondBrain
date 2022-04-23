# 初始化(package.json)
當專案要做 npm 的使用時，都必須先初始化環境，製作一個 `package.json` 的檔案，有這個檔案才能上 npm 去使用別人的模組
```shell
// 專案資料夾
npm init
```

```json
// package.json

{

	"name": "node",
	"version": "1.0.0",
	"description": "Learning npm and node.js",
	"main": "app.js",
	"scripts": {
		"test": "echo \"Error: no test specified\" && exit 1"
	},
	"author": "SZ",
	"license": "ISC"
}
```

## dependencies
當[[指令(npm)#安裝]] 模組之後，這個 `.json`檔會出現該 npm 模組
```json
"dependencies": {
	"cowsay": "^1.4.0"		// 模組名稱與版本
},
```

## scripts
這個屬性可以自定指令
```json
"scripts": {
	"test": "echo \"Error: no test specified\" && exit 1",
	
	"mynodemon": "nodemon app.js", // 可以自己新增指令與動作
	
},
```

#js #advanceJs #library #framework #nodeJs #backEnd #module #npm #json
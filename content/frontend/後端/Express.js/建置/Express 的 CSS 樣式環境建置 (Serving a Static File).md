# 回應有樣式的 HTML 檔案
```js
// app.js

// middleware
app.use(express.static("public"));	// 製作一個 public 資料夾
```

>[[Middleware(express)]]

[[send 和 sendFile 回應(express)#sendFile ：回應 HTML 檔案]] 提到 `sendFile()` 可以回應整個檔案，但如果只是單純在該檔案寫入 `<link>` 是不會有作用的，必須在後端做處理
```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<!-- 用 node 傳 css 不會作用 -->
		<link rel="stylesheet" href="style.css">
		<title>homepage</title>

	</head>

	<body>
		<h1>ejiowjeiqoe</h1>
	</body>
</html>
```

## 樣式的環境設定
```js
// app.js

// middleware
app.use(express.static("public"));	// 製作一個 public 資料夾
```
設定完之後，在這個 public 資料夾裡面放樣式的檔案，就可以讀取到了
```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<!-- public/ 可省略，直接打 style.css 就可以了 -->
		<link rel="stylesheet" href="public/style.css">		
		<title>homepage</title>

	</head>

	<body>
		<h1>ejiowjeiqoe</h1>
	</body>
</html>

```
#js #expressJs #node #server #css #html 
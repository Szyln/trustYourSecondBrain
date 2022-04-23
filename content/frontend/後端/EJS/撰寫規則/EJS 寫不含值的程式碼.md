---
title: "EJS 寫不含值的程式碼"
tag: 
- 
---
# EJS 寫不含值的程式碼
```js
// 單純寫
<% 撰寫純 JS code 的話 %>
```
## for 迴圈
`i` 會顯示在 HTML，要加 `=`
```ejs
<body>
	<%for (let = 0; i < 10; i++) {%>
		<p><%= i %><p>
	<% } %>
</body>
```
---
title: "navbar"
tag: 
- 
---
# navbar
```html
<nav class="navbar navbar-light bg-secondary-light navbar-expand-lg">
	<!-- navabr: 主要 class
	<!-- navbar-light：淺字（配合深底）
	<!-- bg-<theme-color（自訂變數的話，要設定API）> -->
	<!-- navbar-expand-<breakpoint>：設定什麼時候要將細項收起來 -->
</nav>
```
>可以搭配[定位](https://bootstrap5.hexschool.com/docs/5.0/utilities/position/)的通用類別
## container
避免內容貼邊
```html
<nav>
	<div class="container">
			<!-- 內容不貼邊 -->
	</div>
</nav>
```

## 子元素
- [[navbar-brand]]：品牌
- [[navbar-toggler]]：收合按鈕
- [[navbar-nav]]：細項群組

- [[navbar 內放入 form 元素（button, input...）]]

#bs/component/navbar 
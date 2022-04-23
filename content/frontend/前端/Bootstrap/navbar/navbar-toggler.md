---
title: "navbar-toggler"
tag: 
- 
---
# navbar-toggler
收合的按鈕
```html
<button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
	<span class="navbar-toggler-icon"></span>
</button>
```

#bs/component/navbar 


## collapse 跟 navbar-collapse class
`div.collapse.navbar-collapse` 內的標籤會收合
```html
<div class="collapse navbar-collapse" id="navbarSupportedContent">
	<!-- toggle 的範圍要包在這裡面 -->
	<ul class="navbar-nav">
	</ul>
</div>
```


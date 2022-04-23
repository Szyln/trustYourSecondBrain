---
title: "use-strict 嚴格模式"
tag: 
- 
---
# 嚴格模式 use strict
[JavaScript 的嚴格模式 "use strict"](https://ithelp.ithome.com.tw/articles/10191736)
使撰寫語法的時候，如果用了不嚴謹的寫法，會跳出錯誤提示
## 使用方法
### 在全域下
```js
// 在全域直接寫
'use-strict';

// 開始寫程式碼
```

### 在 [[function]] 下
```js
function fn() {
	'use-strict';
	
	// 開始寫 function 內容
}
```

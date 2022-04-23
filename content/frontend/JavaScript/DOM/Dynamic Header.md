---
title: "Dynamic Header"
tag: 
- 
---
# Dynamic Header
設定黏在頭頂的 navbar，可以隨著滾輪變化（透明度、高度等）
 
 - `window.pageYOffset` property
 - `scroll` event
 - style object

sticky 的 nav 
  
```js
const header = document.querySelector('header')

// 加入 scroll 這個事件，每次只要滾輪被滾動，就會觸發第二個參數（一個功能） 
window.addEventListener("scroll", () => {
 	// pageYOffset 代表 window 目前顯示頁面 Y 軸的位置，（例如：最頂端為 0）
	console.log(window.pageYOffset);
	
	if(window.pageYOffset != 0 ) {
		header.style.backgroundColor = 'black'
	} else {
		header.style = ''			
	}
})
```

---
## React 寫法
- https://kyleamathews.github.io/react-headroom/
- https://www.cluemediator.com/animated-sticky-header-on-scroll-in-react

#js #dom
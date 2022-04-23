# Event
[事件](https://developer.mozilla.org/zh-TW/docs/Web/Events)

## 監聽事件
```js
{某節點}.addEventListener(’{event}’, {callback Function})
```

```js
btn.addEventListener(”click”, e => {
		console.log(”clicked!”)
	}
)
```
-   可在 chrome 的開發者工具觀察物件是否有註冊監聽事件
## 事件快照｜監聽事件裡的 function(e)，e 為何物
-   捕捉執行 {event} 時，所發生的所有事件，為 event 的簡寫，可替換為其他字不影響功能
-   也可以針對 e 裡的特定屬性去寫程式，或當成條件等
-   e.target 了解目前事件的作用標籤範圍
-   e.preventDefault｜阻止預設動作
	-   對 a 設定的話，就可以阻止連到其他網站

## 適用範圍
- window object
- element object
## event type
## Event Object Inheritance 繼承
![](https://i.imgur.com/YmH97EB.png)


## Event 常用的 Properties 跟 method
- target
- preventDefault()
- [[stopPropagation]]
### target
event 執行的目標
```js
title.addEventListener(”click”, e => {
		console.log(e.target);
	}
)
```
### preventDefault()
```js
title.addEventListener(”click”, e => {
		e.target.preventDefault();
		
	}
)
```

#js #dom #event
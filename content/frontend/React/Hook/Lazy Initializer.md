---
title: "Lazy Initializer"
tag: 
- 
---
## Lazy Initializer
>[[useState Hook]]
>[[useEffect Hook]]

只要每次 `name` 更新就會 re-render 這個 app（ `Greeting()` ），但每次執行時就檢查一次初始值吃效能不實際
這個功能提供初始狀態只會在需要檢查的時候執行

```jsx
function Greeting() {
  const [name, setName] = React.useState(
		// 放到一個函式內即可
		// 只有重整網站後第一次需要看 localStorage
		// 平常都是看 input 輸入不用執行
		() => { window.localStorage.getItem('name') || '' },
  )
}
```


>[[Logic OR]]

#js/react/hook
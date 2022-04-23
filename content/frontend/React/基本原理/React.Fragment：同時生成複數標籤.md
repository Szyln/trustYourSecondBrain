---
title: "React.Fragment：同時生成複數標籤"
tag: 
- 
---
# React.Fragment
因為 [[ReactDOM：渲染]] 不能[[同時生成多個標籤]]，如果不想要[[上層多包一個標籤]]可以用這個功能

>[[生成標籤：React.createElement()]]：可以多個內文（[[children]]）

```jsx
const element = (
  {/* 沒有內容的空標籤原本的內容是：React.Fragment，太常用了所以簡寫 */}
	<>
		<span>Hello</span>
		<span>World</span>
	</>
)
```
> 沒有簡寫的 JSX 長這樣
>```jsx
>const element = (
>  <React.Fragment>
>    <span>Hello</span>
>    <span>World</span>
>  <React.Fragment/>
>)
>```

## 原始的樣子
- 原本放入 [[children]] 的地方改放多個 `createElement`
- 也可以直接放入 [[children]]
```jsx
const helloElement = React.createElement('span', null, 'Hello')
const worldElement = React.createElement('span', null, 'World')

// 使用 React.Fragment 來產出帶有複數標籤的元素
const element = React.createElement(
	// 實際上不會形成標籤
  React.Fragment,
  null,
		helloElement,
		' ', 
		worldElement
)
```

#js/react/jsx #js/dom #html
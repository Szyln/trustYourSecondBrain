---
title: "JSX"
tag: 
- 
---
# JSX (JavaScript eXtension)
- React 的原始的寫法[[生成標籤：React.createElement()]] 很複雜，通常都是透過 JSX 的功能來寫，再透過 [[Babel]] 編譯回原始寫法
- 可以讓 JS 寫得像 HTML 一樣 
- React 的擴充功能，[[安裝 React]]會一併安裝
- 副檔名是 `.jsx`

```jsx
function App() {
	return (
		// 長相就像 HTML 
		<div>
			<h1>lorem</h1>
			<p>lorem</p>
		</div>			
	)
}
```

#js/react/jsx
# children
- React 標籤的其中一個屬性
- 等同於內文 (DOM 的 textContent)

```jsx
// JSX 的 React 標籤屬性都可以這樣寫
cosnt element = <p children="內文內文" />
```
```jsx
// JSX 的 React children 屬性還可以這樣寫，等同於 HTML 的寫法
cosnt element = <p>內文內文</p>
}
```

## 原始寫法
- 寫在第二個屬性參數內
- 或獨立出來寫在第三個參數內
- 可以用 array 包住多個 children

> 多個 children 可，但是多個標籤不行，參照：[[同時生成多個標籤]]

```js
// 標籤, {屬性}, children
const element = React.createElement('p', {
	className: 'paragraph',
	children: ['Hello World', 'Goodbye World'],
})
```
```js
const element = React.createElement(
	'div', 
	{	className: 'container' },
	'Hello World', 'Goodbye World', 	// 可以多個
)
```

#js/react/jsx #js/dom #html
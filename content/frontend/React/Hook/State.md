---
title: "State"
tag: 
- 
---
# State
>[[useState Hook]]
- 一個狀態，可以拿來設定說這個狀態改變的話哪裡要一起更動
- 元件的狀態
- React 當中每個元件都可以獨立處理（不影響其他頁面上的元素）
- 可以利用這個狀態可以重複使用
- 每當 State, props 更新，都會自動 re-render
- 原本要用 DOM 來處理（querySelector, addEventListener 等等）
>[[Rerender a React Application：有效率的重新渲染]]


## 實例
```jsx
// 這樣不會執行
const App = () => {
	let name = 'Wang'
	const changeNameHandler = () => {
		name = 'Chen'
	}
	return (
		<div>
			<h1>{name}</h1>
			<button onClick={changeHandler}>Change Name</button>
		</div>
	)
}
```
要使用 [[useState Hook]] 來寫
```jsx
const App = () => {
	let [name, setName] = useState('Wang')
	const changeNameHandler = () => {
		setName('Chen')
	}
	return (
		<div>
			<h1>{name}</h1>
			<button onClick={changeHandler}>Change Name</button>
		</div>
	)
}
```

#js/react/hook
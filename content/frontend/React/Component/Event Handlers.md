---
title: "Event Handlers"
tag: 
- 
---
# Event Handlers
>[可以上文件查有支援什麼 Event](https://reactjs.org/docs/events.html#supported-events) 

> 注意事件的函式有沒有被寫成 invoked 的狀態，可以透過再包到一個函式裡來規避
>```js
>onClick{() => {會直接 invoked 的函式}}
>```


## 原始寫法
可以看到原本的寫法會需要 render 很多次，搭配 [[Hook]] 可以改善這問題
>可以再用 [[useState Hook]] 改良：[[Event Handlers#使用 Hook 改寫]]

```jsx
function App() {
	// state 變數儲存要顯示到網頁上的值（event 觸發會更動）
	const state = { eventCount: 0, username: "" };
	// 設定功能要執行的動作
	// 給 onClick event 的功能，event 觸發後便更新 state.eventCount
	// 如果 button 是放在 form 裡面會有預設送出的效果，要放 e.preventDefault() 
	function handleClick() {
		state. eventCount += 1;
		renderApp();
	}
	// 給 onChange 的功能，event 觸發後便將 state
	function handleChange(event) {
		state.username = event.target.value;
		renderApp();
	}

	return (
		<div>
			<p>There have been {state.eventCount} events.</p>
			<p>
				{/* 事件觸發的函式 handleClick 拉上去寫 */}
				<button onClick={handleClick}>Click Me</button>
			</p>
			<p>You typed: {state.username}</p>
			<p>
				<input onChange={handleChange} />
			</p>
		</div>
	);
}

// 正規應該不會這樣寫，參照 [[useState Hook]]
function renderApp() {
	ReactDOM.render(<App />, document.querySelector("#root"));
}

// 要先 render 一次頁面
renderApp();
```

>React 支援的 Event Handlers 也可以讀取到原生的 Event Handlers
>```jsx
>function someKindOfFunction(event) {
>  console.log(event.nativeEvent)
>}
>```

## 使用 [[Hook]] 改寫
>[[Hook]]：[[useState Hook]]
>[[Destructing Assignment]]
```jsx	
function App() { 
	const [ count, setCount ] = React.useState(0);
	const [ username, setUsername ] = React.useState('');

	const handleClick = () => setCount(count + 1);
	const handleChange = (e) => setUsername (e.target.value);

	return (
		<div>
			<p>There have been {count} events.</p>
			<p>
				<button onClick={handleClick}>Click Me</button>
			</p>
			<p>You typed: {username}</p>
			<p>
				<input onChange={handleChange} />
			</p>
		</div>
	);
}

ReactDOM.render(<App />, document.querySelector('#root'));
```

## 補充
課程原本是這樣寫（模擬 `useState` 的寫法），上述有改成自己比較直覺的理解方式
```jsx
// 課程原本寫的事件是這樣寫
function handleClick() {
  setState({eventCount: state.eventCount + 1})
}
// 給 onChange 的功能，event 觸發後便將 state 
function handleChange(event) {
  setState({username: event.target.value})
}

function setState(newState) {
	Object.assign(state, newState)
	renderApp()
}
```
>[[物件不要傳參考的時候：深層、淺層拷貝#淺層拷貝 Shallow Copy]]

 #js/react/component #js/function #js/event
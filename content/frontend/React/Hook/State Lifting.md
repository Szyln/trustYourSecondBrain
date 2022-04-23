# State Lifting
當元件一多的時候，會遇到需要跨元件共享同一個資料的狀況
- [[State Lifting]]	做的就是將子層元件的 state 提升到母層
- 再下放到子層的 props 做使用
- 反過來叫做 [[Colocating]]

>[[State]]：每個元件都有自己獨立的 state, props，彼此不影響

>未來學到 [[Redux]] 就可以解決這問題了，如果專案大了會需要用到
```shell
// 每個元件都有自己的 state, props
<App />
|	|- props: X
|	|- state: X
|- <Create />
|			|- props:
|			|- state: input, message	# 無法共用
|- <Info />
|			|- props: X
|			|- state: X
```
```shell
// 每個元件都有自己的 state, props
<App />
|	|- props: X
|	|- state: message			# state lifting
|- <Create />
|			|- props: message	# 下放
|			|- state: input 	# 無法共用
|- <Info />
|			|- props: message	# 下放
|			|- state: X
```
```jsx
// 母層 
import React from 'react'
// 匯入子層
import Create from './Create';
import Info from './Info';

const App = () => {
	let [message, setMessage] = useState([])
  let [input, setInput] = useState("")

	return (
		<div>
			{/* 將 lift 上來的 state 轉成 props 傳給子層 */}
			<Create message={message} setMessage={setMessages} />
			<Info message={message} setMessage={setMessages} />
		</div>
	)
}
```

```jsx
// 子層
// 傳下來的 props 記得寫進去
const Create = ({message, setMessage}) => {
	// 這兩行 state lifting 到母層
  // let [message, setMessage] = useState([])
  // let [input, setInput] = useState("")

  const submitHandler = (e) => {
    e.preventDefault()
    setMessage([...message, input])
    setInput("")
  }
  const inputHandler = (e) => {
    setInput(e.target.value)
  }
  return (
    <form>
      <input type="text" onChange={inputHandler} value={input} />
      <input type="button" onClick={submitHandler} value="Submit" />
    </form>
  )
}
export default Create
```
>[[Delete in React]]
```jsx
const Info = ({message, setMessage}) => {
  return (
    <ul>
			{message.map(msg => <li>{msg}</li>)}
		</ul>
  )
}

export default Info
```

#js/react/hook
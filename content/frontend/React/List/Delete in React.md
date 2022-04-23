# Delete in React
>用 [[State Lifting]] 的範例

目前內容
- `<App />` ：母層，[[State Lifting]] 有 input, message 的 state
	- `<Create />`：子層，輸入 input 用（存到 message）
	- `<Info />`：子層，顯示 message
		- `<Message />` ：孫層，每個 message 條目，需要參照 [[Key prop]]

>本篇接續 [[Key prop]]

```jsx
const Info = ({message, setMessage}) => {
	return (
		<ul>
			{/* 在 Create 當中被儲存的每個 message 都有 input, id 屬性（一起被 lift 了） */}
			{
        message.map(msg =>
          <Message key={msg} msg={msg.input} message={message} setMessage={setMessage} key={msg.id} />
        )
      }
		</ul>	
	)
}
```

```jsx
// 孫層
const Message = ({msg, message, setMessage}) => {
	const deleteHandler = () => {
		// 因為是刪除功能，所以點擊到要刪除的 message 之外都要保留，所以 id 不相等的都要顯示
		setMessage(message.filter(m => m.id !== msg.id))
	}
	return (
		<li>
			<p>{msg.input}</p>
			<button onClick={deleteHandler}>刪除</button>
		</li>
	)
}
```
>[[filter()]]  




#js/react 
---
title: "Dynamic Form in React"
tag: 
- 
---

# Dynamic Form in React
>[[Form in React]]

運用 React，讓表單做更即時性的互動

以大小寫限制為例
- 用戶輸入大寫時，跳出警示「必須使用小寫英文」＋禁用送出表單按鈕
- 用戶輸入大寫時，自動轉成小寫（推薦）

---

## 自動轉小寫
```jsx
function UsernameForm() {
  const [username, setUsername] = React.useState('')

  function handleSubmit(event) {
    event.preventDefault()
    alert(`You entered: ${username}`)
  }

  function handleChange(event) {
    // 輸入後直接更改 state，但要記得連 input 顯示的 value 一起改
    setUsername(event.target.value.toLowerCase())
  }

  return (
    <form onSubmit={handleSubmit}>
      <div>
        <label htmlFor="usernameInput">Username:</label>
        {/* value 一起更動 */}
        <input id="usernameInput" type="text" onChange={handleChange} value={username} />
      </div>
      <button disabled={Boolean(error)} type="submit">
        Submit
      </button>
    </form>
  )
}
``` 
## 跳出警示＋禁用按鈕
```jsx
function UsernameForm() {
  const [username, setUsername] = React.useState('')
  // 輸入大寫時跳出警示
  const isLowerCase = username === username.toLowerCase()
  const error = isLowerCase ? null : '必須使用小寫英文'

  function handleSubmit(event) {
    event.preventDefault()
    alert(`You entered: ${username}`)
  }

  function handleChange(event) {
    setUsername(event.target.value)
  }

  return (
    <form onSubmit={handleSubmit}>
      <div>
        <label htmlFor="usernameInput">Username:</label>
        <input id="usernameInput" type="text" onChange={handleChange} />
      </div>
      {/* 輸入大寫時跳出警示 */}
      <div style={{color: 'red'}}>{error}</div>
      {/* 輸入大寫禁用按鈕 */}
      <button disabled={Boolean(error)} type="submit">
        Submit
      </button>
    </form>
  )
}
``` 

#js/react #form
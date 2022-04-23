# Form in React
>[[Form]]

- `for` 為保留字，React 中要用 `htmlFor`
- `htmlFor` 可以對應 `input` 的 `id` （或是 `name` ）屬性
```jsx
function UsernameForm() {
  function handleSubmit(event) {
    event.preventDefault()
    // 有幾種寫法
    const username = event.target.elements.usernameInput.value
    alert(`You entered: ${username}`)
  }

  return (
    // event 可以寫在 button 上沒錯
    // 但實際使用上在 input 輸入完按 enter 也可以送出整個表單
    // 所以放在 form 標籤上可以更好得到控制
    <form onSubmit={handleSubmit}>
      <div>
        {/* label 使用 htmlFor, input 用 id, name 都可以對到*/}
        <label htmlFor="usernameInput">Username:</label>
        <input id="usernameInput" type="text" />
      </div>
      <button type="submit">Submit</button>
    </form>
  )
}
```
>## 使用 for 佳
>```jsx
>// 有很多寫法，使用 htmlFor(for) 佳，有唯一性
>const username = event.target.elements.usernameInput.value
>```
>
>### 依照非唯一性的指標不優
>```jsx
>// input 不優，通常會有很多個，建議多 for
>const username = document.querySelector('input').value
>// 用 [指定 index] 不優，程式碼元素順序改變的時候會跑掉
>const username = event.target[0].value
>const username = event.target.elements[0].value 
>```
>### useRef 視狀況用
>```jsx
>// 如果沒必要不用用 useRef
>const usernameInputRef = React.useRef()
>// useRef
>const username = usernameInputRef.current.value
>```
>```jsx
><input ref={usernameInputRef} />
>```

#js/react #form #html 
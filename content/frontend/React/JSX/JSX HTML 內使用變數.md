## JSX HTML 內使用變數
JSX 可以讓 html 像 js 一樣重複利用，更可以在 JSX 標籤內帶入 JS 程式碼

>如果是要元件重複利用（可以導入參數）：[[Component：可重複利用、自定參數的元件]]

```jsx
// 可以單純存值
const children = 'Hello'
const className = 'container'
```
```jsx
// 也可以存 JSX 標籤
// 在 JSX 標籤內想寫 JS 程式碼要用 {} 包起來
const element = <div className={className}>{children}</div>
```
>[[定義屬性(props)]]


```jsx
const App = () => {
  let people = ['Mike', 'Ken', 'Sam']
  return (
    <div>
      {/* 加入{} 就可以寫 JS 了*/}
      <h1>{ 3 * 2 }</h1>
      <p>My name is { name[1] }</p>
    </div>
  )
};
```

#js/react/jsx #js/variable 
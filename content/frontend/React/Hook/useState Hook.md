# useState Hook
```jsx
import React, { useState } from 'react'
// 有匯入 useState 的話下面的 React.useState 可簡寫為 useState
```
```jsx
// name: 自訂名稱，setName：name 的更改 state 用函數
// 初始狀態任意資料類型皆可
// 更詳細的初始狀態設定：[[Lazy Initializer]]
const [name, setName] = React.useState('name 初始狀態')
// setName 參數放入要更新成的內容
// setName 會自動 re-render 該元件，且不影響其他頁面上元素
const handleChange = event => setName('想要 name 怎麼變')
```
>關於 `[name, setName]` 寫法參照：
>- [[Destructing Assignment]]
>- [[Event Handlers]]

使用 useState [[Hook]]，來控制元件的 [[State]]，並且用 [[Event Handlers]] 來規劃如何觸發

>再用 [[useEffect Hook]] 看如何搭配 [[side-effect]] 來寫更複雜的 [[Hook]]，並且改良 `useState` 的初始值設定 （[[Lazy Initializer]]）

>[[State Lifting]]：寫多層次的 react 專案時會遇到的問題
---

```jsx
function Greeting() {
	// destructing assignment
	// 更進階的初始值設定：[[Lazy Initializer]]
  const [name, setName] = React.useState('')
  const handleChange = event => setName(event.target.value)
  return (
    <div>
      <form>
				{/* for 要寫 htmlFor 避免與 js 的 for 衝突 */}
        <label htmlFor="name">Name: </label>
        <input onChange={handleChange} id="name" />
      </form>
      {name ? <strong>Hello {name}</strong> : 'Please type your name'}
    </div>
  )
}

ReactDOM.render(<Greeting />, document.querySelector('#root'))
```
>```jsx
>for 要寫 htmlFor 避免與 js 的 for 衝突
><label htmlFor="name">Name: </label>
> ```

#js/react/hook
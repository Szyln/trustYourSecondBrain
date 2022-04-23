# useEffect Hook
處理 [[side-effect]] 的 [[Hook]]

## 使用情境
`useEffect` 會在每次 render 時執行，可以使用 [[Dependency array]] 來限定執行時機

## 以儲存資料到 [[Local Storage]] 為例

>[[自訂 Hooks]]：若有要一起使用的 [[Hook]] （這裡以 [[useEffect Hook]], [[useState Hook]] 為例）可以把他們加到一個函式內，方便使用

```jsx
const App = () => {
	// useState: name, setName	
	// setName 功能
	// useEffect
	
	return <渲染的內容 />
}
```
### 先完成 useState 設定
>參照： [[useState Hook]]，設定了 `[name, setName]`

### name 存入 LocalStorage
1. 當 `name` 透過 `useState` 更新（自動 re-render 這個 app）
2. 觸發 `useEffect` 更新 [[Local Storage]]（單向更新）

>#### 選用（效能考量）
>3. [[Dependency array]]：可以讓 [[side-effect]] 的另一端資料與 React 維持雙向同步

```jsx
// name 更新 -> 更新 localStorage（注意：這是單向更新）
React.useEffect(() => {
  console.log('useEffect 被執行囉');
  window.localStorage.setItem('name', name)
// [[Dependency array]]：使資料雙向同步
}, [name])
```

### 檢查 LocalStorage 內有沒有既有資料
用來剛開啟網頁（或是重整網頁）時用

>參照 [[Lazy Initializer]]（[[useState Hook]]）

#js/react/hook
---
title: "自訂 Hooks"
tag: 
- 
---
# 自訂 Hooks
>[[Hook]]

- 若有要一起使用的 [[Hook]] 可以把他們加到一個函式內，方便使用
- 慣例上會以 use 作為開頭命名（[[eslint-plugin-react-hooks]] 會加以辨識）

```jsx
// 將 useState, useEffect 從 Greeting () 元件抽出，組合成一個自訂 Hook
function useLocalStorageState(key, defaultValue = '') {
	// [[Destructing Assignment]]
	// 命名保有通用性，不管什麼值都符合
  const [state, setState] = React.useState(
    // key 保有通用性，defaultValue 保有可自訂性（呼叫函式時可以參數設定）
    () => window.localStorage.getItem(key) || defaultValue,
  )

  React.useEffect(() => {
    // 通用性
    window.localStorage.setItem(key, state)
    // 兩個值都可能透過 localStorage 更動，兩個都要雙向同步
    // [[Dependency array]]
  }, [key, state])

  return [state, setState]
}

function Greeting() {
  // 取得 [state, setState] 將他存到 [name, setName] 裡
  const [name, setName] = useLocalStorageState('name')
	// setName 函式
	
  return (<渲染內容 />)
}
```

#js/react/hook


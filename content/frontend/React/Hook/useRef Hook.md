---
title: "useRef Hook"
tag: 
- 
---
# useRef Hook

> `useRef` 的 ref 與[[物件傳參考]]中提到的 reference 是同一件事
> 指的是「變數指向記憶體位置上對應到的值」

- 在 React 中用原始的 DOM 方式（ `querySelector` 之類）操作元素並不直覺，使用 `useRef` [[Hook]]，可以直接在元件裡，直接操作元件
- 允許 render 期間可以維持相同的值
- 可以儲存可變動值，但不會觸發 re-render
- `useRef` 只會回傳一個  `current` 屬性
- `useRef()` 的 argument 可放入初始值

>[[useState Hook]] 更動值的的時候就會觸發 re-render

>[[Form in React]]：不一定所有狀況都適合用 `useRef`

---

>本篇使用 Library：[vanill-tilt](https://micku7zu.github.io/vanilla-tilt.js/index.html)
>可使用 querySelector 來讓 DOM node 有酷炫的漸層動態效果
```jsx
function Tilt() {
  // 這變數存有一個 object，其中有 current 屬性可以使用，可以顯示當前 DOM node
  const tilteRef = React.useRef()
	
  // 這樣用 current 不會成功，因為還沒有渲染 return 裡面的內容
  console.log(tiltRef.current)
	
  // useEffect 使這個在 render 完後執行
  React.useEffect(() => {
		// tilt.current 代表該 ref 的 dom node
    const tiltNode = tiltRef.current
    //  vanilla-tilt 的 設定
    const vanillaTiltOptions = {
      max: 25,
      speed: 400,
    }
    // vanilla-tilt 的設定: 將 vanillaTiltOptions 賦予到 tiltNode 這個 DOM node 上
    VanillaTilt.init(tiltNode, vanillaTiltOptions)
		// 在不渲染這個 dom node 的時候可以將這個 ref 刪掉，不佔用記憶體空間
		return () => {
			tiltNode.vanillaTilt.destroy()
		}
	// [[Dependency array]]: 只需要第一次執行 
  }, [])
  return (
    // useRef
    <div ref={tiltRef} className="tilt-root">
    </div>
  )
}
```
>[[useEffect Hook]]
```jsx
function Tilt({children}) {
  const tiltRef = React.useRef()

  React.useEffect(() => {
    const tiltNode = tiltRef.current
    const vanillaTiltOptions = {
      max: 25,
      speed: 400,
      glare: true,
      'max-glare': 0.5,
    }
    VanillaTilt.init(tiltNode, vanillaTiltOptions)
    return () => {
      tiltNode.vanillaTilt.destroy()
    }
  }, [])

  // 注意：React 的 JSX 寫的終究是一個 React element 而已
  // （Render 出來的結果才是 DOM 元素）
  // 不是 DOM 元素 
  return (
    // 放入 ref prop 可以讓他有
    <div ref={tiltRef} className="tilt-root">
      <div className="tilt-child">{children}</div>
    </div>
  )
}

function App() {
  const [showTilt, setShowTilt] = React.useState(true)
  return (
    <div>
      <label>
        <input
          type="checkbox"
          checked={showTilt}
          onChange={e => setShowTilt(e.target.checked)}
        />{' '}
        show tilt
      </label>
      {showTilt ? (
        <Tilt>
          <div className="totally-centered">vanilla-tilt.js</div>
        </Tilt>
      ) : null}
    </div>
  )
}
```


>- [非控制組件與 useRef](https://ithelp.ithome.com.tw/articles/10246939)
>- [React useRef Hook](https://www.w3schools.com/react/react_useref.asp)

#js/react/hook
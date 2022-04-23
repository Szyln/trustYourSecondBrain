# Rerender a React Application
React 中，重新渲染的時候不會造成整個區塊都被更新的問題
重整範圍：有更新的（ `{time}` ）屬性的範圍

```jsx
function tick() {
  const time = new Date().toLocaleTimeString()
  const element = (
  <div>
    <input value={time} />
    <input value={time} />
  </div>
  )
  ReactDOM.render(element, rootElement)
}

setInterval(tick, 1000)
```

>## DOM 的作法
>重整範圍：`<div>`
>```jsx
>function tick() {
>  const time = new Date().toLocaleTimeString()
>  const element = `
>  <div>
>    <input value='${time}' />
>    <input value='${time}' />
>  </div>
>
>  rootElement.innerHTML = element
>}
>
>setInterval(tick, 1000)
>```

#js/react/component
---
title: "Class Component"
tag: 
- 
---
## Class Component
>現今版本已經不建議使用，參考：[[Component：可重複利用、自定參數的元件]]
```jsx
// 一定要繼承 React.Component 來寫，結果跟 function component 一樣
// 這裡面的 render 不等於 ReactDOM.render()
class Car extends React.Component {
  render() {
    return <h2>Hi, I am a Car!</h2>;
  }
}

// function component 寫法

function Car() {
  return <h2>Hi, I am a Car!</h2>;
}
```
#js/react
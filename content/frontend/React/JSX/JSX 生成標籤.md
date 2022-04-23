---
title: "JSX 生成標籤"
tag: 
- 
---
# JSX 生成標籤
>雖然他長相像 HTML，但更可以做 JS 內才能做的事： [[JSX 內的 HTML 加入 JS 程式碼]]

- JSX 的寫法跟一般 HTML 差不了多少，編譯完可以看到原始 [[生成標籤：React.createElement()]] 的寫法

```jsx
// JSX 寫法
const HellowElement = <h1 className="title">Hello World</h1>
```
```jsx
// JSX 編譯後
const HelloElement = React.createElement(
  'h1',
  { className: 'title' },
  'Hello World'
)
```
>標籤內文寫法參照：[[children]]
>等同於 textContent

#js/react/jsx
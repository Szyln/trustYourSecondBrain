---
title: "ReactDOM：渲染"
tag: 
- 
---
# ReactDOM
![[React 使用的模組#^19ab2a]]

React 遵循 [[5.關注點分離]]的規則，JS 的內容寫完後渲染到畫面指定位置上

```js
// 可以直接簡寫成：
ReactDom. render('要渲染的內容', document. querySelector('#渲染位置'));
// <要渲染的內容> 只能有一個：[[同時生成多個標籤]]
```
---

```html
<body>
	<div id="root">
		<!-- 使用 React.DOM 將內容渲染於頁面 -->
	</div>
</body>
```
```js
// 生成標籤：[[React.createElement()：生成標籤]]再講
const element = '等到後面再講'

// 取得渲染位置
const rootElement = document.querySelector('#root')
// 將標籤 append 到 rootElement 上
ReactDOM.render(element, rootElement)

```
```js
// 可以直接簡寫成：
ReactDom.render(element, document.quertSelector('#root'));
```
>## 原生 JS 作法
>```js
>// 生成標籤
>const element = document.createElement('div')
>
>// 取得欲渲染到的 HTML 標籤(#root)
>const rootElement = document.querySeletor('#root')
>// 將標籤 append 到 rootElement 上
>rootElement.appendChild(element)
>```


## 補充：元件的渲染
```jsx
function App() {
	return <一些東西 />
}
```
```jsx
// 原本是這樣寫
ReactDOM.render(React.createElement(App), document.querySelector('#root'));
```
```jsx
// 因為是函數，這樣寫也可
ReactDOM.render(App(), document.querySelector('#root'));
```
```jsx
// 搭配 JSX 這樣寫即可：[[JSX]] 再講
ReactDOM.render(<App />, document.querySelector('#root'));
```
#js/react/jsx #js/dom #html
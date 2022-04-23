# Component
- 用 `function` 來 `return` HTML 元素，其中可以自訂參數來調整元素，方便重複使用
- 透過 [[定義屬性(props)#物件定義屬性（ Key-Value Pair ）]]（參數）可以調整每個生成出來的元件
- 要大寫開頭
- 一個元件可以在另一個元件裡（詳細要進一步了解渲染的機制： [[Hook]]）
- 寫多了元件就：[[元件匯出]]

>先今（16.8 版）多是用 Function Component + [[Hook]] 來寫（參照本篇）
>早期主要是用 [[Class Component]]，現在已經很少用到

>- 單純使用 `{}`  可以重複利用存到變數內的 html：[[JSX HTML 內使用變數]]
>- 但要可以調整參數就要學會元件的概念

>[[用元件處理 CSS Styling]]
---

元件導入了參數的概念，[[定義屬性(props)]] 可以做出更靈活的調整

## 生成元件
>如果想限制參數的格式：[[PropTypes：元件參數的 Vaildator]]
```jsx
// 也可以這樣寫：[[Destructing Assignment]]
cosnt MessageEdit = {children} => <div>{children}</div>
```
```jsx
// 元件的參數可以指定很多屬性，例如 children, style, 或是自訂等
// 用 props.屬性 來讀取
const MessageEdit = props => <div>{props.children}</div>
```


## 使用元件
```jsx
const element = (
  <div>
		{/* 通用寫法，children 還有更好的寫法 */}
		<MessageEdit children="Hello America." />
	</div>
)
```
> 還可以這樣寫
> ```jsx
>// 因為是函式，這樣寫也可
>{MessageEdit({ children: "Hello Taiwan." })}
>// 所有的屬性都可以這樣寫
><MessageEdit children="Hello America." />
>// children 這樣寫可讀性最好
><MessageEdit>Hello Japan.</MessageEdit>
>```
>>[[children]]


>元件與 [[JSX 內的 HTML 加入 JS 程式碼]]不同有使用參數，變數儲存的內容若是函數（Component），要大寫開頭
>```js
>// ！：如果沒有寫大寫，第一參數（HTML 標籤）編譯會無法正常辨識
>const element = React.createElement('messageEdit', null, 'Hello World')
> `` `
>```jsx
>// 有大寫的話，就會辨識為一個函數
>const element = React.createElement(MessageEdit, null, 'Hello World')
>
>// type: MessageEdit(props)
>// 為一個 function 而非標籤
>console.log(<MessageEdit children="Hello America." />);
>```
[[生成標籤：React.createElement()]]


#js/react/component #js/function #js/object #html #html
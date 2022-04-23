# 定義屬性
- HTML 標籤上有很多屬性（例：class, style, action......）都可以透過 React 去設定
- 也可以自訂屬性寫更客製化的內容：[[Component：可重複利用、自定參數的元件]]
>範例：[[用元件處理 CSS Styling]]

---

- 屬性的定義有兩種方法，效果一樣 ^1bd0ac
	- 用 JS 寫值本身（單一資料） ^8d0c66
	- 用 JS 寫整個屬性（物件、[[Key-Value Pair]]）

## 只用 JS 定義屬性的值 Value

>[[JSX 內的 HTML 加入 JS 程式碼]]

```jsx
const children = 'Hello'
const className = 'container'

const element = <div className={className}>{children}</div>
```
>[[children]] 還有其他寫法

## 物件定義屬性（ [[Key-Value Pair]] ）
>寫 [[Component：可重複利用、自定參數的元件]]的時候會把參數拉出來寫
>>[[Destructing Assignment]]
>```jsx
>// 將物件內容轉換成網頁顯示
>const friend = ({name, age, desc}) => {
>  return <div>
>    <h1>Name: {name}</h1>
>    <h2>Age: {age}</h2>
>    <p>{desc}</p>
>  </div>
>};
>```
>

HTML 屬性中，重複的屬性，後者會蓋過前者
```jsx
// 使用物件儲存屬性們
const props = { children: 'Hello', className: 'container' }
const element = <div {...props} />
```
>[[物件不要傳參考的時候：深層、淺層拷貝]]

### 增加屬性（物件以外）
```jsx
// 寫在 props 前
const element = <div id="app-root" {...props} />
```
### 覆蓋屬性
```jsx
// 寫在 props 後
const element = <div {...props} className="not-container" />
```


#js/react/component #js/function #js/object #html
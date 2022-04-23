# Key prop when Rendering List
> 使用 [[UUID]] 來生生成 key prop

>與 [[Delete in React]] 同一個範例，做完 key prop 就可以做 delete 功能了

## 取得 list 資料 -> 存到 array（state）

^3083f9

React 會因為在 render `array` （例如用 [[陣列的循環 for, forEach, map]] 功能）的時候，沒有加上 `key` 這個唯一性的屬性而跳出警示
可以自己寫也可以使用 [[UUID]] 來自動生成
```jsx
// 匯入 UUID 來生成 key prop
import { v4 as uuidv4 } from 'uuid';

// 有 state lifting 到母層
const Create = ({message, setMessage}) => {
  const submitHandler = (e) => {
    e.preventDefault()
		// 剛生成 message 的時候就可以給她 key prop 了
    setMessage([...message, {input, id: uuidv4()}])
    setInput("")
  }
  const inputHandler = (e) => {
    setInput(e.target.value)
  }
  return (
    <form>
      <input type="text" onChange={inputHandler} value={input} />
      <input type="button" onClick={submitHandler} value="Submit" />
    </form>
  )
}
```
>### 為什麼需要 key
>因為用其他非唯一性的屬性作為 event handler 的參考的話，很容易出現問題
> >[[Delete in React]]
>
> ```jsx
> // 例如做刪除 list 功能時
>const deleteHandler = () => {
>// 使用文字做基準的話，有兩個 li 都是相同內文的話就會一起刪掉
>setMessage (message. filter (m => m !== msg))
>}
> ```

#js/react 
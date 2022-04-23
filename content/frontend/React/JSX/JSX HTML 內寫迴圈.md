## JSX HTML 內寫迴圈
```jsx
const App = () => {
  let people = ['Mike', 'Ken', 'Sam']
  return (
    <div>
      <p>List of team member:</p>
      {/* 箭頭函式可以簡化 */}
      {/*
        people.map(person => {
          reutrn <p>{name}</p>
        })
      */}
      {/* 迴圈要記得，return 的 HTML 再包一次 {} */}
      {
        people.map(person => (<p>{name}</p>)
      }
    </div>
  )
};
```
>[[陣列的循環 for, forEach, map]]
>[[4.箭頭函式 arrow function]]

#js/react/jsx #js/loop 
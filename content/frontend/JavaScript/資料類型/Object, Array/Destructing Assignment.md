---
title: "Destructing Assignment"
tag: 
- 
---
# Destructing Assignment
```js
// array
[a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(a); // 10
console.log(b); // 20
console.log(rest); // [30, 40, 50]

// object
({a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40});
console.log(a); // 10
console.log(b); // 20
console.log(rest); // {c: 30, d: 40}

// 忽略前面的只取其中一個（以第三個為例）
[,,c] = [10, 20, 30, 40, 50];
console.log(c); // 30
```

```js
// 只取得物件中的特定屬性
// 
const person = {
  name: 'Jesse',
  age: 30, 
  address: {
    city: 'Houston',
    state: 'Texas',
    country: 'USA'
  }
}

displayMessage(person)

// 只取 person.address.state
function displayMessage({ address: { state } }) {
  const message = 'I live in ' + state + '.';
}
```
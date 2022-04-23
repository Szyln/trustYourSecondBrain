# Logic OR (||)
> [mdn](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR)
```js
expr1 || expr2
```
如果 expr1 是真值，傳 expr1，其餘傳 expr2
```js
o1 = true  || true       // t || t returns true
o2 = false || true       // f || t returns true
o3 = true  || false      // t || f returns true
o4 = false || (3 == 4)   // f || f returns false
o5 = 'Cat' || 'Dog'      // t || t returns "Cat"
o6 = false || 'Cat'      // f || t returns "Cat"
o7 = 'Cat' || false      // t || f returns "Cat"
o8 = ''    || false      // f || f returns false
o9 = false || ''         // f || f returns ""
o10 = false || varObject // f || object returns varObject
```

#js #logic 
---
title: "console.log"
tag: 
- 
---
# console.log
- [Handy Tips on Using console.log()](https://dmitripavlutin.com/console-log-tips/)

可以用以下的 specifier 來帶入特定值

| Specifier |                             Purpose                            |
|:---------:|:--------------------------------------------------------------:|
| %s        | string                               |
| %d or %i  | 整數 (integer)                             |
| %f        | 非整數 (float)                                |
| %o        | Element is displayed with optimally useful formatting          |
| %O        | Element is displayed with generic JavaScript object formatting |
| %c        | 賦予 CSS 樣式                                        |


```js
const user = 'john_smith';
const attempts = 5;

// 帶入 string, 整數
console.log('%s failed to login %i times', user, attempts);
// logs "john_smith failed to login 5 times"

// 賦予樣式
console.log('%c Big message', 'font-size: 36px; font-weight: bold');
```
#js 

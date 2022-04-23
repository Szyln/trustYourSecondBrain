---
title: "React-bootstrap 建置"
tag: 
- 
---
## 安裝
>[官網](https://react-bootstrap.github.io/getting-started/introduction/#installation)

```shell
npm install react-bootstrap bootstrap@5.1.3
```
BS 客製化的話要再多安裝原生 BS
```shell
npm install bootstrap
```


## 使用元件
使用元件要個別匯入
```jsx
import Button from 'react-bootstrap/Button';
```
>```jsx
>// 或是這樣寫也還可（建議前者）
>import { Button } from 'react-bootstrap';
>```

## 使用 JS
-  `react-bootstrap.js` 
-  `react-bootstrap.min.js`
```jsx
import "../node_modules/react-bootstrap/dist/react-boostrap.js";
```


#js/react #bs 
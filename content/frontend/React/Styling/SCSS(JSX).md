---
title: "SCSS(JSX)"
tag: 
- 
---
# SCSS (JSX)
編譯完後的 CSS 檔可以直接匯到 `app.jsx` 內
不用匯到 `main.jsx` （ `main` 只負責 render）

```jsx
import React from 'react';
// 匯入 css 
import './styles/style.css';

const App = () =>  (
  <div>
    {/* 測試 bs */}
    <button type="button" class="btn btn-primary mr-3" data-toggle="modal" data-target="#exampleModal">Toggle example modal</button>
  </div>
);

export default App; 
```

#js/react #css/scss 
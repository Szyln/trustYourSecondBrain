---
title: "react-router-dom"
tag: 
- 
---
# react-router-dom
```shell
npm install react-router-dom
```

- Routing
- Link (`a` 標籤)

>[[react-router-dom 版本差異]]

---

## Routing
可以在 React 操作 Routing
### BrowserRouter：URL 將 React 專案連接上瀏覽器的網址
```jsx
// main.jsx(負責 render)
// 匯入 React, ReactDOM, App
import { BrowserRouter } from 'react-router-dom'

ReactDOM.render(
  <React.StrictMode>
    {/* 用 BrowserRouter 包住 */}
    <BrowserRouter>
      {/* App 元件內為整個頁面，包含共同區塊 Nav, Footer */}
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
```

`<Route />` 內寫入 `path`（路徑）, `element`（頁面.jsx）
```jsx
// 匯入 React, Nav, HomePage, About, Footer
import { Routes, Route } from 'react-router-dom'

function App() {
  return (
    <>
      <Nav />
      {/* 使用 Routes 包住 Route */}
      <Routes>
				{/* Route 決定點連結之後會產生的內容 */}
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<About />} />
      </Routes>
      <Footer />
    </>
  );
}
export default App;
```
>[[Nested Routes(react-router-dom （未完成）]]
## Link
取代 `<a>` ，`App()` 中的 `Routes` 元件就是透過這裡做回應
```jsx
// 匯入 React
import { Link } from "react-router-dom";

const Nav = () => {
  return (
    <nav >
      <ul>
        <li>
          {/* 因為有設定 Route，所以這個點下去後 Routes 區塊的內容就會隨著 Link 影響*/}
          <Link to="/">首頁</Link>
        </li>
        <li>
          <Link to="/about">關於我們</Link>
        </li>
      </ul>
    </nav>
  );
};
```



#js/react #npm #module #routing 
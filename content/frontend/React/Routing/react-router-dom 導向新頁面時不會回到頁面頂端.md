---
title: "react-router-dom 導向新頁面時不會回到頁面頂端"
tag: 
- 
---
# react-router-dom 導向新頁面時不會回到頁面頂端
>[Scroll Restoration](https://v5.reactrouter.com/web/guides/scroll-restoration)

新增 [scroll 到頂端的元件]((https://v5.reactrouter.com/web/guides/scroll-restoration))
```jsx
import { useEffect } from "react";
import { useLocation } from "react-router-dom";

export default function ScrollToTop() {
  const { pathname } = useLocation();

  useEffect(() => {
    window.scrollTo(0, 0);
  }, [pathname]);

  return null;
}
```
在 `BrowserRouter` 下方加入這個元件
```jsx
// 雜七雜八匯入

ReactDOM.render(
  <React.StrictMode>
    {/* 用 BrowserRouter 包住 */}
    <BrowserRouter>
    <ScrollToTop />
      {/* App 元件內為整個頁面，包含共同區塊 Nav, Footer */}
      <App />
    </BrowserRouter>
  </React.StrictMode>,
  document.getElementById("root")
);
```

#js/react #routing
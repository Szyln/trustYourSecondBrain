# react-router-dom 版本差異
Wilson 課程影片是 5，該版本有 Switch 的寫法
> [[react-router-dom]]
```jsx
import { Switch, Route } from "react-router-dom";
 
function App() {
  return (
    <div className="App">
      <Nav />
      {/* 主要更改部分 */}
      {/* Switch 包兩個 Route，Route 包一個頁面（網頁共同部分 Nav, Footer 不含在內） */}
      <Switch>
        // exact 代表要完全符合 path 的值, 才會顯示
        <Route path="/" exact>
          <Homepage />
        </Route>
        <Route path="/about" exact>
          <About />
        </Route>
      </Switch>
      <Footer />
    </div>
  );
}
```

```jsx
import { Routes, Route } from "react-router-dom";

function App() {
  return (
    <div className="App">
      <Nav />
      {/* Switch 拿掉，改成 Routes 包兩個 Route，Route 內頁面寫在 element 即可*/}
      <Routes>
        <Route path="/" element={<Homepage />} />
        <Route path="/about" element={<About />} />
      </Routes>
      <Footer />
    </div>
  );
}
```

#js/react #routing #node/npm
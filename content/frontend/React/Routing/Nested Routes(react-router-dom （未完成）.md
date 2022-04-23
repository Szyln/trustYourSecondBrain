## Nested Routes
>[[react-router-dom]]

You may have noticed when clicking the links that the layout in `App` disappears. Repeating shared layouts is a pain in the neck. We've learned that most UI is a series of nested layouts that almost always map to segments of the URL so this idea is baked right in to React Router.

Let's get some automatic, persistent layout handling by doing just two things:

1.  Nest the routes inside of the App route
2.  Render an Outlet

First let's nest the routes. Right now the expenses and invoices routes are siblings to the app, we want to make them _children_ of the app route:
```jsx
import { render } from "react-dom";
import {
  BrowserRouter,
  Routes,
  Route,
} from "react-router-dom";
import App from "./App";
import Expenses from "./routes/expenses";
import Invoices from "./routes/invoices";

const rootElement = document.getElementById("root");
render(
  <BrowserRouter>
    <Routes>
      <Route path="/" element={<App />}>
        <Route path="expenses" element={<Expenses />} />
        <Route path="invoices" element={<Invoices />} />
      </Route>
    </Routes>
  </BrowserRouter>,
  rootElement
);
```
When routes have children it does two things:

1.  It nests the URLs (`"/" + "expenses"` and `"/" + "invoices"`)
2.  It will nest the UI components for shared layout when the child route matches:

However, before (2) will work we need to render an `Outlet` in the `App.jsx` "parent" route.

```jsx
import { Outlet, Link } from "react-router-dom";
export default function App() {
  return (
    <div>
      <h1>Bookkeeper</h1>
      <nav
        style={{
          borderBottom: "solid 1px",
          paddingBottom: "1rem",
        }}
      >
        <Link to="/invoices">Invoices</Link> |{" "}
        <Link to="/expenses">Expenses</Link>
      </nav>
      <Outlet />
    </div>
  );
}
```
Now click around again. The parent route (`App.js`) persists while the `<Outlet>` swaps between the two child routes (`<Invoices>` and `<Expenses>`)!

As we'll see later, this works at _any level_ of the route hierarchy and is incredibly powerful.


#js/react #routing #未完成 
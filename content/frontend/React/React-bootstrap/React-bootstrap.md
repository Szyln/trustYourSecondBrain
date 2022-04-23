---
title: "React-bootstrap"
tag: 
- 
---
# React-bootstrap
- 不包含 styling 部分（SCSS），要客製化要再匯入原生 BS
- 符合 React 的特性，不會直接操作實體 DOM 元素。
- 配合 React，將各式各樣的元件已經 Component 化，減少整個程式碼的複雜度。


- [[React-bootstrap 建置]]

# 'as' prop
```jsx
<Row className="mx-0">
  <Button as={Col} variant="primary">Button #1</Button>
  <Button as={Col} variant="secondary" className="mx-2">Button #2</Button>
  <Button as={Col} variant="success">Button #3</Button>
</Row>
```
```jsx
// as 的部分渲染後長這樣
<div role="button" tabindex="0" class="btn btn-primary col">Button #1</div>
```
#js/react/bs 
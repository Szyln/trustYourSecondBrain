---
title: "現行的 ES 模組使用技巧"
tag: 
- 
---
# 現行的 ES 模組使用技巧
## 作用域
每個 `type="module"` 的作用域都是獨立的
### 非模組的狀況
```html
<script>
var a = 1;		// 設置全域 a 變數
window.b = 2;	// windows b 屬性
</script>

<script>
console.log(a); // 讀取不到
console.log(b);	// 讀取不到
</script>

```

### 模組的狀況
```html
<script type="module">
var a = 1;		// 設置全域 a 變數
window.b = 2;	// windows b 屬性
</script>

<script type="module">
console.log(a); // 讀取不到
console.log(b);	// 讀到了！（不建議
</script>

```
## 可以運用的 ESM 套件
網路上有很多版本的 ESM 套件
> [ESM module](https://cdnjs.com/libraries/vue)
> [Vue 的 Getting Started 的語法](https://v3.vuejs.org/guide/introduction.html#declarative-rendering)

```html
<script type="module">
  import { createApp } from 'https://cdnjs.cloudflare.com/ajax/libs/vue/3.1.4/vue.esm-browser.min.js'    // esm-browser 是給瀏覽器運行用的 ESM 版本
const Counter = {
  data() {
    return {
      counter: 0
    }
  }
}

// 決定畫面要在哪裡呈現
createApp(Counter).mount('#app')  
</script>
```
```html
<div id="app">  // .mount('#app')指定渲染於此
  Counter: {{ counter }}
</div>
```

#js #vue #module 
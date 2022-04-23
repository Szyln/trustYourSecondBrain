# 在瀏覽器運行 ES 模組
## 為何模組化
[[JS 模組化的由來與目的]]

## 方法
[[在瀏覽器（原生）下運行模組]]

## 匯出
匯入前要先匯出，原則上都是在 JS 上進行
### 預設匯出：defaultExport.js
常見的匯出方式，通常用於匯出物件，在 Vue 開發中可用來匯出元件
- 只能匯出一個
``` javascript=
export default
```
### 具名匯出：namedExport.js
可用於匯出已定義的變數、物件、函式，專案開發中通常用於 “方法匯出”
第三方的框架、函式、套件很常使用具名定義 “方法”
- 可以匯出多個
``` js
export const XXX = ... // 多個，具名
```
## 匯入
在 HTML, JS 匯入都有
### 預設匯入
因為本身沒有名稱，可自訂
``` js
import 自訂名稱 from ..
```
### 具名匯入
```js
import {具名名稱} from ..
```

## 實例
### 預設匯出匯入
預設匯出，建立一個 export.js 檔
```js
export default {某個元件內容}  // 不包含該元件的名稱
```
預設匯入
```html
<script type="module">
  import newComponent from 'export.js';
  newComponent.init();
</script>
```

### 具名匯出匯入
建立一個 export2.js 檔
```js
export const a = 1;
export function b() {
  ..
}..
```
#### 單一匯入（建議）
```html
<script type="module">
  import { a, b } from 'export2.js';
  console.log(a);
  b();
</script>
```

#### 全部匯入（不建議，較難除錯）
```html
<script type="module">
  import * as all from 'export2.js';  // 避免名稱的衝突，會賦予在一個物件(all)上面
  console.log(all.a);
  all.b();
</script>
```

#js #vue #module 
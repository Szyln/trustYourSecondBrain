# data attribute：自訂 HTML 屬性
>[使用數據屬性(data attribute)](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Howto/Use_data_attributes)

在 HTML 上可以任意自訂 `data-*` 的屬性，使 JS 可以輕易訪問
```html
<article
  id="文章"
  data-bunch-of-numbers="12314"
>
...
</article>
```


## 如何用 JS 訪問
- `getAttribute()`
- `DOMStringMap` 的 `dataset`

```js
var article = document.querySelector('#文章');

// 記得原本用 - 連接的字要用 camelCase 拼
article.dataset.bunchOfNumbers // "12314"
```


## 用 CSS 訪問
### 讀取
```css
article::before {
  content: attr(data-bunch-of-numbers);
}
```
### 當作屬性選擇器
```css
article[data-bunch-of-numbers='12314'] {
  width: 400px;
}

```
#html #js #js/dom 
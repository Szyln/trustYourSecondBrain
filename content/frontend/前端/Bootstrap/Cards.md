---
title: "Cards"
tag: 
- 
---
# Cards

## 基本結構
`card` 不包含 `margin`，預設寬度適應父層
```html
<!-- card，寬度可自訂 -->
<div class="card">
  <!-- card-img-top -->
  <img src="..." class="card-img-top" alt="...">
  <!-- card-body -->
  <div class="card-body">
    <!-- card-title -->
    <h5 class="card-title">Card title</h5>
	<!-- card-text -->
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

## 父層
- `card`

## 子層
### 卡片結構
有頁頭、頁尾、內文，除了文字的頁頭頁尾，也有圖像的頁頭頁尾
- `&-header`
- `&-footer`
- `&-body`
- 圖像版看下段

### 圖像相關
- `&-img-top`
- `&-img-bottom`
- `&-img`：佔滿
- `&-img-overlay`：取代 `card-body`

### 其他搭配
- `list-group-flush`


## 孫層
可以在子層任意位置使用
- `&-title h*`
- `&-subtitle h*`
- `&-text`
- `&-link`：link 在卡片裡可以並排
- 還可以搭配其他小元件

### 列表群組
- 搭配 `list-group-flush`可以在卡片內建立群組  

```html
<!-- 可放入 .card 子層，加上 list-group-flush -->
<ul class="list-group list-group-flush">
  <li class="list-group-item">An item</li>
  <li class="list-group-item">A second item</li>
  <li class="list-group-item">A third item</li>
</ul>
```


## 網格換行
`.row-cols-數字`
可控制該從第幾張卡片開始換行


## 等高
### 卡片群組化
如果外層加上 `card-group`，卡片們會群組化，並且等高
### 對卡片加上等高設定
如果不想群組化要等高的話，要在 card 層加上 h-100

#css/scss  #bs/component/card

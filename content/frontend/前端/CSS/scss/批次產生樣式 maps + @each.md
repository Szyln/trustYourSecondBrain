---
title: "批次產生樣式 maps + @each"
tag: 
- 
---
# 批次產生樣式 @each

[@each+Sass Maps批次產生各元素樣式](https://github.com/gonsakon/Learn-Sass-in-90-days/blob/master/docs/Sass/%40each%2BSass%20Maps%E6%89%B9%E6%AC%A1%E7%94%A2%E7%94%9F%E5%90%84%E5%85%83%E7%B4%A0%E6%A8%A3%E5%BC%8F.markdown)

## BS 的寫法
原始碼長這樣
```scss
// 先有個 maps
$types: (
  primary   :  #428bca,
  success   :  #5cb85c,
  info :  #5bc0de,
  warning    :  #f0ad4e,
  danger    :  #d9534f
) !default;
//按鈕

// 再用 each 產出樣式
@each $name, $color in $types {
  .btn-#{$name} {
    background:$color;
    color:#fff;
    border: 1px solid darken($color,5%);
  }
}
```


## Sass Maps 是什麼功能？
先解釋第一段 maps 的部份
```scss
$types: (
  primary   :  #428bca,
  success   :  #5cb85c,
  info :  #5bc0de,
  warning    :  #f0ad4e,
  danger    :  #d9534f
)
```
這是 Sass 3.3的新的變數設定方式
```scss
$variables-group: ( // 看起來很熟悉的變數，但內容是更多的變數
key1: value,  // key 是變數名
key2: value,
....
)
```
maps 功能可以將多個相關的變數群組起來

## @each
那再來看第二段
```scss
@each $name, $color in $types {
  .btn-#{$name} {
    background:$color;
    color:#fff;
    border: 1px solid darken($color,5%);
  }
}
```
結構是這樣
```scss
// $key, $value 可自訂名稱，分別代表 代入的 $variables-group 的 key, value
@each $key, $value in $variables-group {
	.btn-#{$key} {  // 有多少個 key 就執行多少遍
		background: $value;
	}
}
```

## 產出的 CSS
這就是 bs 這樣寫會產出的東西囉
```css
.btn-primary {
  background: #428bca;
  color: #fff;
  border: 1px solid #357ebd;
}
.btn-success {
  background: #5cb85c;
  color: #fff;
  border: 1px solid #4cae4c;
}
```


```css
.btn-key1 {
	background: value;
}
.btn-key2
...
```

## ${} 插補
變數沒辦法直接接在字串上，所以會用
所以會看到`.btn-#{$key}`的字樣
（目前還看不懂）
#css #scss
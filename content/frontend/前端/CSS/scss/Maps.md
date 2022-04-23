---
title: "Maps"
tag: 
- 
---
# Maps
[## Sass教學 (40) - 使用Sass Maps提升程式可讀、變數群組性](https://ithelp.ithome.com.tw/articles/10161389)

## 從原始碼推敲
原始碼長這樣
```sass
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
```sass
$types: (
  primary   :  #428bca,
  success   :  #5cb85c,
  info :  #5bc0de,
  warning    :  #f0ad4e,
  danger    :  #d9534f
)
```
這是 Sass 3.3的新的變數設定方式
```sass
$variables-group: ( // 看起來很熟悉的變數，但內容是更多的變數
key1: value,  // key 是變數名
key2: value,
....
)
```
maps 功能可以將多個相關的變數群組起來
## maps 的進階功能
### map-get($map , $key)
取出`$map`裡指定的`$key`，將value取出來。  
### map-merge($map1, $map2)
將兩個$map合併起來。  
### map-remove( $map , $key)
從Map裡面刪除一個$key。  
### map-keys($map)
取出所有的$key。  
### map-values($map)
取出所有的value。  
### map-has-key($map, $key)
瀏覽裡面是否有$key值，有則回傳true，沒有便回傳false。  
### keywords($args)
Returns the map of named arguments passed to a function or mixin that takes a variable argument list. The argument names are strings, and they do not contain the leading $.
```scss
$color: (
    default: #fff,
    primary: #22ae39
);
.box{
    color: map-get($color,default);
    background: map-get($color,primary)
}
```
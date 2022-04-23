# 客製化 Sass
## import 順序
-   BS variables
-   BS function
-   BS mixins
-   自訂 variables（命名_customVariables.scss，簡稱 custom）
-   BS 完整版（如果還不知道怎麼挑出需要的，就先放完整版扣掉前面的）

## 客製化步驟
用 custom 去覆蓋
### 修改預設變數
直接在 _custom 複製該變數，去掉 !default 進行修改即可

### 修改 Maps
```scss
// 想要修改的顏色
$primary: $blue !default;
$secondary: $gray-600 !default;
  
// 他們所在的 map
$theme-colors: (
"primary": $primary,
"secondary": $secondary, ...
) !default;


// 在 _custom 中修改 map 中特定項目，同修改變數後，重寫一次 map
$primary: #0074d9;
$danger: #ff4136;

$theme-colors: (
"primary": $primary,
"secondary": $secondary, ...
) ;
```
#### 添加至 map
```scss
// 在 _custom
// 新增一個 map
$custom-colors: (
 "custom-color": #900
);

// 合併到原本的 map
**$theme-colors: map-merge($theme-colors, $custom-colors);**
```
#bs/customize #css/scss/customize
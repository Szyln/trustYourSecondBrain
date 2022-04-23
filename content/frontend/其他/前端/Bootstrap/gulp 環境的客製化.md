# gulp 環境下的 bootstrap 客製化
## 檔案結構
目前還不太清楚為什麼要放在 node_modules 裡  
```text
your-project/
├── scss
│   └── custom.scss
└── node_modules/
    └── bootstrap
        ├── js
        └── scss
```

## 匯入至專案
有兩種方法  
- 全部匯入 `bootstrap.scss`（入門）
- 部分匯入（進階）

### 全部匯入
```sass
// 選項 A: 放入完整 bs 檔

// 匯入欲覆蓋既有變數的自訂變數（但 function 不會運作）

@import "../node_modules/bootstrap/scss/bootstrap";

// 匯入新增的自訂變數
```
### 部分匯入
熟悉之後會建議採取這個方法  
一開始會不知道怎麼去取用要哪些檔案  
我目前的作法是直接把 `bootstrap.scss` 裡面有匯入的都先匯入，等到專案做完之後我再把拿掉不影響的檔案拿掉。  

```sass
//選項 B: 放入部分 bs 檔（只放專案有用到的部份）

// 1. 匯入 functions (按照這個順序，後面可以啟動 manipulate colors, SVGs, calc 等功能)
@import "../node_modules/bootstrap/scss/functions";

// 2. 匯入欲覆蓋既有變數的自訂變數
@import "修改原有變數、map 的 scss";

// 3. 匯入運作 bs 必須的檔案（包含原本的變數檔案）
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";

// 4. 匯入「新增或刪除」的自訂變數
@improt "刪除或新增 map 的 scss";

//　5. 匯入選用的 bs 檔案（專案有用到的部份）
@import "../node_modules/bootstrap/scss/root";
@import "../node_modules/bootstrap/scss/reboot";
@import "../node_modules/bootstrap/scss/type";
@import "../node_modules/bootstrap/scss/images";
@import "../node_modules/bootstrap/scss/containers";
@import "../node_modules/bootstrap/scss/grid";

// 6. 匯入其餘自訂的 scss 檔案
@import "其他手刻檔案";
```

## 客製化
欲修改的內容有幾個部分  
- 變數 variables
- 修改 map 既有子變數
- 添加子變數至 map
- 刪除 map 既有子變數（難）


### 覆蓋預設變數
預設變數**前**匯入，並且不加上 !default
```sass
// bs 運作的必須檔案先匯入
@import "../node_modules/bootstrap/scss/functions";

// 既有的變數覆蓋成自訂參數，並且拿掉 !default 
$body-bg: #000;
$body-color: #111;

// 匯入其他必須檔案，!default 的參數若是已經有遭到更改，則不會讀取
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";

// Bootstrap and its default variables

// 匯入其他選用檔案
@import "../node_modules/bootstrap/scss/root";
@import "../node_modules/bootstrap/scss/reboot";
@import "../node_modules/bootstrap/scss/type";
// etc
```
###  修改 map 既有子變數
bs 裡，map 裡出現過的變數，都可以找到額外設定一個獨立的變數  
> map 是什麼？[[批次產生樣式 maps + @each]], [[Maps]]

而 map 裡的變數都會從獨立變數匯入  
想要更改 map 就必須從獨立變數改起，map 則維持原樣  

```sass
$primary: #0074d9;
$danger: #ff4136;
```
```sass
$theme-colors: (
  "primary": $primary,
  "danger": $danger
);
```
簡單來說，修改變數的動作，與修改 map 是一樣的  

### 添加子變數至 map
一旦是要無中生有或是化有為無的動作就要特別小心  
這個動作就是無中生有的部分  

要在預設變數匯入之**後**進行  


```sass
// 在預設變數匯入之後進行
// 新建的 map 包含子變數
$custom-colors: (
  "custom-color": #900
);

// 與 既有的 map Merge 起來 
$theme-colors: map-merge($theme-colors, $custom-colors);
```


### 刪除 map 既有子變數
刪除原本 map 裡面的內容，時機跟上述的不太一樣，要在必須的檔案匯入後再執行  
```sass
// Required
@import "../node_modules/bootstrap/scss/functions";
@import "../node_modules/bootstrap/scss/variables";
@import "../node_modules/bootstrap/scss/mixins";

$theme-colors: map-remove($theme-colors, "info", "light", "dark");

// Optional
@import "../node_modules/bootstrap/scss/root";
@import "../node_modules/bootstrap/scss/reboot";
@import "../node_modules/bootstrap/scss/type";
// etc
```
#gulp #bs/customize  
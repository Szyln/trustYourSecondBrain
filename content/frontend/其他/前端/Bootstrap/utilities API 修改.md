# utilities API 修改
[Bootstrap 5 Utilities | New Utility API !!](https://www.youtube.com/watch?v=gNCAmxBwD9I)

## import 順序
在 `utilities.scss` 匯入之前做修改
```sass=
// bs 的必須檔案
@import "../../../node_modules/bootstrap/scss/functions";
@import "../../../node_modules/bootstrap/scss/variables";
@import "../../../node_modules/bootstrap/scss/mixins";

// 自訂的 utilities 
@import "./helpers/utilitiesAPI";
// 原本 bs 的 utilities
@import "../../../node_modules/bootstrap/scss/utilities";

// 剩餘其他選用 bs 檔案
@import "../../../node_modules/bootstrap/scss/bootstrap";
```

## 自訂的 utilitiesAPI 檔案內容
```sass=
// utilities API
$utilities: ()!default;  // 覆蓋原本的檔案

$utilities: map-merge(   // 合併自訂與預設的檔案
  $utilities,
  (
    "font-size": (         // 從 bs utilities 檔案中複製出
      rfs: true,           // 需要修改的 utilities
      property: font-size, // 這裡以 font-size 做示範
      responsive: true,
      class: fs,
      values: $font-sizes
    ),  // 如有多個，用 , 分開，再接續其他 utilties
  )
);
```

## 可添加參數
|選項|類型|介紹|
|-|-|-|
property|必要|屬性的名稱，可以是字串或是字串陣列 ( 例如，水平的 padding 或 margin )。|
|values|必要|清單中的值或 map，在您不希望 class 名稱與值相同時使用。如果將 null 作為 map 鍵值，則不會編譯它。
|class|可選|當您不希望 class 名稱與屬性相同時所使用的變數。如果您不提供 class 鍵值，且 property 鍵值是字串陣列，則 class 名稱將是 property 陣列的第一個元素。
|state|可選|為通用類別生成的虛擬類別類清單，像是 :hover 或 :focus。沒有預設值。
|responsive|可選|用於指示是否要生成響應式類別的布林值。預設值為 false。
|rfs|可選|用於啟用流體縮放的布林值。可以查看 RFS 頁面以了解如何運作。預設值為 false。
|print|可選|用於指示是否要生成 print 類別的布林值。預設值為 false。
|rtl|可選|用於指示是否要將通用類別保留於 RTL 中的布林值。預設值為 true。|

#bs/customize 
---
title: "bs grid system"
tag: 
- 
---
## 配置規則
-   row 底下只能是 column
-   column 之上只能是 row
## Rows（列） 與 Columns（欄）
### gutter
- column 間的水平 padding 
用來控制 column 之間的間距

- 由相鄰的 col 的兩個 padding 所構成
 gutter = col 的 padding * 2
 
 - 背景圖片會無視 gutters
## row 的設定
### 最左、右邊的 column 
 row 會加上負值 margin 抵消多餘的 padding
 確保每一 column 中的內容在視覺上沿左側向下對齊
 
%%目前先隱藏這段 每一 row 也支持使用修飾符 class，以統一 row 與 column  的大小和 Gutters 來更改內容的間距。%%

%%-   在 row 上快速設定 col （等寬）
-   row-cols-{breakpoint}-{欄位數}
-   gutters%%


#bs/grid 

---
title: "GULP 的 Github 部屬"
tag: 
- 
---
# GULP 的 Github 部屬
使用 [[Git]] 做版本管理
> Git 版本管理方法：[[Git#連接遠端版本控制]]

## Github 部屬（每次更新都要重新執行）
生產模式
```shell
gulp build
```
客戶端看到的畫面部屬 [[Github Pages]]（頁面顯示可能要等一下
```shell
gulp deploy  
```
客戶只會看到 dist 裡（編譯後）的檔案

## [[Github Pages]] 取得靜態網頁
branch 要選 gh-pages


## 後續更新
### 客戶端
[[GULP 的 Github 部屬#Github 部屬（每次更新都要重新執行）]]
### 程式端
add>commit>git push -u origin master

#gulp
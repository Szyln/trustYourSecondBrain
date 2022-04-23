---
title: "git add(track)"
tag: 
- 
---
## Track
只有[[git init]]還不會產生效果，需要將裡面的檔案 track 起來，才能追蹤到他們的變化，之後[[git commit]] 的時候就會把他們提交出去了
### 全體 track
```shell
git add .
```
### track 特定副檔名檔案
```shell
git add *.html
```
### 移除 stage 狀態
```shell
git rm --cached "檔名"
```


之後可以用 [[git status]] 再檢查目前狀態


#git
---
title: "Branch"
tag: 
- 
---
# Branch
新增 branch
```shell
git branch login(一個分支的名稱)
```

移動到該 branch
```shell
git checkout login
```
:::info
checkout 可以讓你在不同 branch 的版本間做切換
:::
## 與原本的 branch 做合併
:::warning
一定先 add, commit， 後 merge
:::
如果在新 branch 裡面做了 commit（目前不會影響到主 branch
```shell
git add .
git commit -m "login commit"
```

回到主 branch，與新 branch 做 merge
```shell
git checkout main
git merge login
```

## merge conflict
![](https://i.imgur.com/je8HfGW.png)
 當新分支與主分支同時被修改時，merge 功能會因為不知道該取捨哪個修改，所以必須先處理掉 conflict 狀態才能 merge
 ![](https://i.imgur.com/88WDGGs.png)
決定完之後，需再重新執行 add, commit
#git 
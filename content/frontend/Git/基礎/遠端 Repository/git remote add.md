## 現存本機 repo 加入到遠端 repo
```shell
git remote add origin https://github.com/Szyln/Joanne.CV.git
git branch -M main
git push -u origin main
```

1. 在 github 新增 repo（遠端）
2. 為已存在的本機 repo 連上遠端 repo，並新增 branch
```shell
git remote add <遠端數據庫簡稱> <url>
git branch -M main
```
3. 檢查是否連上，觀看遠端數據庫列表
```shell
git remote
```
4. push 資料上去
```shell
git push -u <遠端數據庫簡稱> main
```
>`-u`: upstream

-   觀看遠端數據庫列表：`git remote`
-   觀看遠端數據庫列表(包含 rul)：`git remote -v`
-   下載遠端數據庫：`git clone <url>`


#git
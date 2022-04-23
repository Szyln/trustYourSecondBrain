---
title: "Working Tree"
tag: 
- 
---
# Working Tree
中文稱 Git 資料夾
代表一個版本的一連串流程，從專案當中取出的獨立版本可以在本機編輯
![working tree](https://w3c.hexschool.com/img/72316309_2739111376108490_535994150261096448_n1fkzgd.jpg)
![工作目錄，預存區及 Git 資料夾。](https://git-scm.com/book/en/v2/images/areas.png)
- Working Directory
	- 在這裡編輯
- Staging Area
	- 在這裡決定下次要 commit 哪些更動
- Git Directory (Repository)
	- 將更動儲存為 snapshot 正式 commit 於此

## Three States
### modified
已修改：但尚未 commit 到 database
### staged
已預存：標記一個已經 modified 的資料，會存到下次 commit 到 snapshot 中
### committed
已提交：已經安全的存在本機 database




#git
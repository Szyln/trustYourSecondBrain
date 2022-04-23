## [[環境建立#該資料夾]]
## 該資料夾
在該資料夾安裝 plug-in
```shell
npm install
```

在該資料夾執行 gulp 
```shell
gulp
```

會跳出瀏覽器
## [[GULP 的 Github 部屬]]

### Jiang V 分享自己常遇到的問題

解決方法
1.因為我都在 git init  之後接著 git add . 卡住  
2.此時再補上一次 sudo git add . 接著打最高權限密碼，然後再繼續  
3.接著 git remote add origin https://~~~~~你的網址，可能會遇到這個錯誤 fatal: remote origin already exists.  
4.接著就輸入 git remote rm origin  
5.再重新輸入 git remote add origin https://~~~~~你的網址  
6.再重新輸入 git push -u origin main 上傳

#gulp
https://spring.io/projects/spring-boot

[課程資訊：Github 免費架站術！輕鬆打造個人品牌](https://hahow.in/courses/5de8fec16117240026540b9c/main)

## 建置環境
### 下載 hugo-extended
https://gohugo.io/
[See the Getting Started Guide for other methods.](https://gohugo.io/getting-started/installing/)
![](https://i.imgur.com/ShUlg77.png)
[Hugo Releases](https://github.com/gohugoio/hugo/releases)
![](https://i.imgur.com/mvg2MWo.png)
找hugo_extended
![](https://i.imgur.com/zVpmjXE.png)
會得到一個執行檔
![](https://i.imgur.com/5z4mKOf.png)


## 下載需要的 hugo themes 
[HUGO themes](https://themes.gohugo.io/)
這裡以 [Liva Hugo](https://themes.gohugo.io/themes/liva-hugo/) 為例
1. Download
2. 下載後 將 liva-hugo-master 資料夾，名稱刪除 -master
3. 將裡面的 exampleSite 拉出，新建 themes 資料夾
4. live-hugo 拉進去 themes
5. extend 資料夾的 hugo 執行檔拉進去 exampleSite
6. exampleSite 執行
```
./hugo server
```

![](https://i.imgur.com/JpHa5QZ.png)
7.   取得本機即時預覽網址    
```
Web Server is available at http://localhost:1313/liva/ (bind address 127.0.0.1)

Press Ctrl+C to stop
```

## 修改程式碼
### config.toml
最重要的設定檔
#### 設定部落格名稱
```toml
title = "部落格名稱"  
```
#### 設定 logo
```
logo = "images/logo.png"
```
static/image
大小可以進主題的程式碼再改
#### contact me
````
# Contact Information
mobile = "0124857985320"
email = "demo@email.com"
location = "Dhaka, Bangladedsh"
````

#### about/index.md
作者大頭貼
```
# image
image: "images/author.jpg"
```

#### 支援 markdown
換行要空一行

## Analytics 分析
可以串接其他 API

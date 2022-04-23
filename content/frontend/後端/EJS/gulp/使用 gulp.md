# 課前該用好的 gulp by Sz
[gulp 環境安裝流程](https://hackmd.io/yWpLNMPRT2yvIR4Zq_idGw?view)


## gulp 環境設置
### 一台電腦做一次
::: info
:::spoiler 全域安裝
1. 確認是否安裝 [Node.js](https://nodejs.org/en/)  (這邊省略安裝步驟)
```shell
node -v
```

2. 安裝 gulp （失敗請參考下面一行）
```shell
npm i gulp@4 -g 
```

#### 失敗的話，用管理員權限安裝
```shell
sudo npm i gulp@4 -g
```


3. 檢查是否安裝好 gulp
```shell
gulp -v
```

:::

### 一個資料夾做一次
1. [下載資料夾](https://github.com/hexschool/web-layout-training-gulp)，更改成想要的專案名稱


#### 在該資料夾
2. 在該資料夾安裝 plug-in
```shell
npm install
```

3. 在該資料夾執行 gulp，會跳出瀏覽器，即時監看
```shell
gulp
```

4. terminal 停止監看
```
按 ctrl + C // 不是 command + C
```
之後一樣打 `gulp` 都可以叫回來，不用擔心

5. 來開始建置 git 囉


## git

確認電腦有沒有安裝 git
```shell
git
```
### 對該資料夾
1. 初始化，會產生 .git 隱藏資料夾
```shell
git init
```
:::success
#### 遠端數據庫 程式端更新
2. 讓 git 關愛所有檔案
```shell
git add .
```
3. 容易焦慮就檢查一下 git 有沒有真的關愛到大家，沒有紅字就可以繼續
```shell
git status
```
4. 有的話就提交囉
```shell
git commit -m "輸入提交訊息"
```
5. 再焦慮的檢查一下有沒有成功提交
```shell
git log
```
:::


### 連上 github 遠端數據庫

1. github 上創新的 repository
2. 獲取網址
```shell
 git remote add origin <這裡貼入 github 給的網址>
```
3. 焦慮的檢查一下有沒有真的連上遠端
    - 有的話會顯示這個遠端數據庫的暱稱，暱稱就是上段預設 `origin` 的部份
    - 沒有的話檢查一下網址有沒有打錯
```shell
git remote
```

4. 選擇分支（這邊還沒有很懂）
```shell
git branch -M main
```



5. （僅限第一次）推上去
```shell
git push -u origin main
```
:::success
6. （第二次開始）推上去
```shell
git push
```
### 遠端數據庫 客戶端更新
1. 生產模式（還沒有很懂）
```shell
gulp build
```
2. gh-pages（給客戶端演示用） 建置，也會設定好 github pages，這段要給他耐心與愛心
```shell
gulp deploy
```
3. 檢查 github > setting > github pages > source 有沒有對，改完也要有耐心與愛心
4. github pages 給你的網址就是你的展示畫面囉！一樣要給他耐心與愛心
:::

:::success
**綠色框框的內容，每次上傳更新都要做**
:::

## 編譯？
編譯就像翻譯一樣，在溝通的雙方語言不同時
就需要進行一個語言轉換的過程

我們寫程式時也一樣，也很容易遇到我們寫的語言，跟處理的軟硬體，懂的語言不同的狀況

這時候中間的轉換就會需要一個類似翻譯的動作
這裡就可以先簡單理解為編譯囉

## 學到的 gulp 編譯
gulp 整合了很多個原本往往要很多工具才能做到的事
- SCSS 是一個很好管理的 CSS 寫法，但瀏覽器不懂
- layout 的管理不想手動複製貼上，但瀏覽器也看不懂
但瀏覽器是讀不懂的
- 圖片未經處理，檔案巨大
- js 常常每個瀏覽器看起來不一樣
在 gulp 裡面，他 layout, scss, 圖片壓縮, js兼容的管理 都一併幫你完成囉！

## 資料夾結構
- dist
	- 編譯後的結果
	- **不要動**
- app：撰寫資料的位置
	- assets：HTML, CSS, JS, 圖檔影片等等放這，不要改名稱，以後可能會遇到會叫做 public 的
		- script：gulp 幫你處理相容問題
		- style：gulp 幫你編譯
			- sass
		- images：：gulp 幫你壓縮省流量
	- index.html
- gulpfile.js
	- enbOptions.js：路徑，可查看輸出的路徑，若要更改路徑要記得 `ctrl+C` 關閉後，`gulp` 重開

## 新增新頁面
複製 index.html 去改名稱，如果要監看該頁面，在瀏覽器網址尾段加上該檔名

### HTML 結構
定義 layout 格式，可以對進行共通設定
```html
---
title: <title>                // head 裡面那個 title 標籤
layout: ./app/layout.ejs      // 共同版型， header, footer 終於幸福ㄌ
engine:ejs                    // 使用的樣板語言，跟我們所學的內容很像
current:index                 // 暫時不動囉
---

<body 內容>

```


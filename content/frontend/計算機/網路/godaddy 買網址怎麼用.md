# godaddy 買網址怎麼用
彩蛋週｜課程直播｜切版班 by Sz

[網站上線全攻略](https://hackmd.io/WqYJs4b4SnCD9WeEG8MMVA?view)

## 步驟
1. 申請網址（godaddy）
2. 代管（cloudflare）
3. 管理 DNS，可以新增很多個導向網站
4. 以導向 github 為例
5. 加密
6. 新增一律加密規則（免費版有三次）
7. 主機
8. 上線後搜尋引擎的設定（google search console）
9. google analytics(GA) 觀察客戶行為
10. SEO

## 申請網址(godaddy)
```
名稱.頂級網域
```
市面上有很多地方可以買、也有代理商（不同網域）
其實在哪買沒什麼差
想續約要注意網址蟑螂
::: warning
`.com`, `.com.tw` 是公司用，可能會被檢舉
:::

### 購買步驟
![](https://i.imgur.com/LKUyAFo.png)
全部no thank you
買純網址即可，他提供的加值服務可以透過下個步驟完成

## 代管（cloudflare）（耐心）
![](https://i.imgur.com/sq05zlE.png)
- 加密 (SSL，可使用 https 協定)
- DNS 導到不同網站
- 可免費使用



### 管理 DNS
::: info
DNS 讓你可以自訂網址，方便指向對應主機位置
:::
網路管理員->管理 DNS
買好的網址前綴可以無限新增，來導向不同的位置
![](https://i.imgur.com/zbhMze2.png)
```
可自訂新增的前綴.名稱.頂級網域
```
`www.買的網址` ->某個主機
`shop.買的網址` ->某個主機(CNAME)

#### CNAME
可以再進入導向的網站後台設定，設定托管會連到哪個細部網頁

#### 不同的前綴有不同功用
|類型|功用|
|-|-|
|A|IP|
|mx|信箱|
|cname|例如 github|
 
## 代管步驟
1. 複製到 godaddy 網頁名稱伺服器
2. ->輸入自己的名稱伺服器(cloudflare)


## 以導向 github 為例
:::info
github pages 本身有加密，但如果要自訂網址，則要自己準備（在 cloudflare）
:::
## custom domain（耐心）
![](https://i.imgur.com/HF9s6zV.png)
經由 CNAME 導入的 github，
可以再到 github 的 custom domain 上去設定，讓他直接指回代管
![](https://i.imgur.com/SFzNM4X.png)
他會 publish 到沒有 https 的網址
但因為 cloudflare 有提供
記得在「規則」的地方自動轉成 https
輸入記得要改成 https，就會有了
![](https://i.imgur.com/S3vV9bI.png)
:::    warning
目前已知 bug
重新 deploy 完會被導回預設網址，要重設定（耐心）
:::
## 回到 cloudflare
### SSL/TLS
跟 https 加密的設定有關
### 規則
可以設定一律用 https， github pages 就會成功加密了（免費版限三次）



## 為什麼需要主機
容量
:::    info
github 有容量限制（各repo 1G），真的太大的網站還是需要主機
:::
## 購買主機通路
- emanager
- heroku


## google search console(耐心)
檢查網站狀態
1. 資源->新增資源
![](https://i.imgur.com/I8GZXLv.png)
2. 驗證需要再回 cloudflare 新增 txt 類型的驗證文字



## 安裝 Google Analytics(GA) 追蹤流量
分析顧客行為
沒有買網域也可以用
要貼一串到網站程式碼內
![](https://i.imgur.com/faY7K5f.png)
新增帳戶，再新增資源
![](https://i.imgur.com/WR6wOBC.png)
21:35

## SEO
:::danger
h1 可以寫錯，但 title 不行
:::
```htmlembedded=
<title>
 本頁主題 - 分類 - 品牌
</title>
```
- 
- 每個頁面標題不該一樣
- 本業主題該放最前面，而非品牌名
- 數量要達 10 頁以上，Google 才會開始讓你的連結在搜尋引擎上曝光

## 分析類似網站
https://www.similarweb.com/ja/


[[輕量化]]

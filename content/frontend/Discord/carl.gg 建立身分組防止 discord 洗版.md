# carl.gg
![](https://i.imgur.com/MoCy4wt.png)

carl. gg 可以透過回應表符的方法，來讓成員加入想要的身分組，可以做到的效果像是
- 不用管理員設定，成員自己選擇要加入什麼身分組
- 管理員可以按照身分組區分私人頻道，防止伺服器變大之後，避免成員被不感興趣的頻道洗版

這個機器人可以做到其他很多效果，這邊就只針對回應表符指定身分組的功能做說明

## 邀請機器人到伺服器
登入完後選擇你要加入機器人的伺服器（你必須是管理者或有管理權限）
![](https://i.imgur.com/XpHhGlB.png)
確定伺服器正確後「繼續」
![](https://i.imgur.com/RVKzwH2.png)
以下清單是他會要有的權限，如果你本身沒有更動這些權限的權限（？）的話，後續安裝會有些問題，ok 後「授權」，結束後會有個不是機器人驗證
![](https://i.imgur.com/V9jgFmV.png)
## 快速導覽（可跳過）
進到快速開始的導覽（可以直接跳過）
![](https://i.imgur.com/PlpWqic.png)
設定打指令的時候前綴字，可跳過
![](https://i.imgur.com/FsBpaP8.png)
用戶進到你的伺服器時顯示的招呼語，可跳過
![](https://i.imgur.com/yfG862R.png)

示範怎麼建立連結身分組的投票區塊
新增任何一個都會幫你自動建立對應的身分組，如果他的選項不合你使用，可跳過晚點自己建
![](https://i.imgur.com/1IkVCBX.png)
沒特別研究，就照他的建立新的 muted role（create new role）
![](https://i.imgur.com/9fZ1HJQ.png)
沒特別研究，可跳過
![](https://i.imgur.com/AplUMBx.png)
快速導覽完成頁面
跟你推薦一下他們另一個機器人，是累積貢獻值的系統，有需要才裝
![](https://i.imgur.com/3Pp1vZa.png)
## 設定畫面
### 編輯機器人名稱
進去設定畫面後，這裡可幫機器人編輯名稱
![](https://i.imgur.com/lnKzmIN.png)
### Reaction roles
以下會講解這些內容在哪裡設定
![](https://i.imgur.com/k4e009Q.png)

---

Reaction roles 這裡可以建立身分組投票
![](https://i.imgur.com/NIOGAIN.png)

### 基本設定
- Mode
	- Post embed 就可以
	- `#你要顯示這個投票的頻道`
- Content

![](https://i.imgur.com/SPKxd01.png)

### 投票設定


下面有兩個選項，都會用到
- Show embled builder：投票內容描述
- Add emoji：新增投票項目（對應身分組）
![](https://i.imgur.com/SKW9Zzb.png)

#### 投票內容描述 (Show embled builder)
![](https://i.imgur.com/k4e009Q.png)
![](https://i.imgur.com/qtaifH2.png)
我的範例：
![](https://i.imgur.com/yNx7xXo.png)

#### 新增投票項目（對應身分組）(Add emoji)
身分組要在 DC 伺服器上先建好（建完後要等一下，重整網頁才會出現在的選項中）
![](https://i.imgur.com/1OTF2lE.png)

### 參與權限與投票方式
- 第一項：選擇投票方式
	- normal：可以複選、取消、重選
	- unique：只能單選
- 第二項：指定特定身分組可以選，如果群組很大建議設定
- 第三項：黑名單（不可以參加投票的成員）
![](https://i.imgur.com/IBidXcc.png)

### 完成建立
Create 按下去之後龜龜就會發文了，發完後沒辦法做太大更改，要更改建議直接砍掉這個投票再建一次

#discord/bot
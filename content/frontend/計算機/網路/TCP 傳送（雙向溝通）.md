# TCP 傳送（雙向溝通）
 initial connection
嚴謹，需要握手揮手
## TCP 三項交握（建立連線）
建立三項交握後，瀏覽器跟伺服器才會建立雙向溝通

```
瀏覽器  --   [SYN]   --> 伺服器	// 1
瀏覽器 <-- [SYN/ACK] --  伺服器	// 2
瀏覽器  --   [ACK]   --> 伺服器	// 3 TCP 三項交握
```
## request（發送請求）
```
瀏覽器  --   [GET HTTP1.1]   --> 伺服器	// request
瀏覽器 <--     [TCP 傳送]     --  伺服器   // 伺服器給資料
瀏覽器  --   [HTTP 200 OK]   --> 伺服器	// 伺服器表示傳好了
```

在 [[Wireshark]]上會有這樣的訊息
GET 完後就會開始 TCP [[封包]]傳送
TCP 會分成很多個小[[封包]]傳送
送完就會收到 `200 OK` 的[[狀態碼]]
![](https://i.imgur.com/w6cQ1YI.png)
![](https://i.imgur.com/DTy9BJg.png)

## TCP 中斷連線
TCP 四次揮手，中斷連線
```
瀏覽器  --   		      [確認收齊資料，申請關閉]  			    --> 伺服器
瀏覽器 <--     			[申請通過，準備關閉]					  --  伺服器
瀏覽器  --   [收到關閉通知，回戳確認，等待一段時間後，瀏覽器端也關閉]   --> 伺服器
```

- 從 [[Wireshark]] 來看過程發生什麼事： [[Wireshark#對應 TCP IP]]
- 從 [[TCP IP]] 來看發生什麼事：[[TCP IP#傳輸 封包 的過程]]

#internet #backEnd #request 
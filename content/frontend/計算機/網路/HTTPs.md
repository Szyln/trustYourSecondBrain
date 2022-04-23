# HTTPs 與 HTTP 的差異？
- Hyper Text Transfer Protocol over Secure Socket Layer
- 有沒有加密，get, post 什麼都看不到
-  因此 HTTP 的狀況下不要用 POST，資料都會被看光光
-  HTTP 是 80 port、HTTPS 是  443 port
-  HTTP 是 應用層、HTTPS 是傳輸層

## [[Wireshark]] 上的樣子
![](https://i.imgur.com/SnWGOsS.png)
有透過 HTTPS 加密的文件，是沒辦法直接查看[[封包]]內容的，TLSv1.2 就是代表 HTTPs
![](https://i.imgur.com/2YSAmhs.png)
詳細資料也會多一行 Secure Sockets Layer([[SSL]] 憑證)



## 其他連結
-    [執行過程](https://zh.wikipedia.org/wiki/%E5%82%B3%E8%BC%B8%E5%B1%A4%E5%AE%89%E5%85%A8%E6%80%A7%E5%8D%94%E5%AE%9A#%E8%BF%87%E7%A8%8B) 
	-    [TLS 1.2（SSL 3.3）](https://zh.wikipedia.org/wiki/%E5%82%B3%E8%BC%B8%E5%B1%A4%E5%AE%89%E5%85%A8%E6%80%A7%E5%8D%94%E5%AE%9A) 

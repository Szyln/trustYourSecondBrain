# Wireshark 
- [wireshark 下載網址](https://www.wireshark.org/download.html) 、 [指令表](http://packetlife.net/media/library/12/tcpdump.pdf) 
## 介面
### filter
![](https://i.imgur.com/PMO44yx.png)
Wireshark 的 filter 功能，可以篩選特定封包
### [[封包]]
![](https://i.imgur.com/fmmQQ4b.png)
 有網路傳輸的時候就可以看到有很多封包進來，每個封包會這樣一條一條進來
 ### 資訊
![](https://i.imgur.com/ab7QoRh.png)

裡面詳細資訊可以從這裡看

#### 對應[[TCP IP]]
- 網路連結層（的實體層）：第一行，對應的是實際用哪條光纖、哪個網路口做傳送的
- 網路連結層：以太 Ethernet ，顯示對方與自己的網路卡的 [[MAC]]
- 網路層：Internet Protocol Version 4 (IPv4)
- 傳輸層：Transmission Control Protocol (TCP)，包含[[Port]]資訊
	- Port: 自己的 Port 跟對應對方的 Port
- 應用層：Hypertext Transfer Protocol(HTTP)
- Secure Socket Laye (SSL)： 如果有 [[HTTPs]] 就會有這行資訊
- 
#### 實際上的格式
 ![](https://i.imgur.com/k41LCno.png)
但事實上，封包內容都是以 16 進位儲存，使用這個格式跟共同網路規範有關（例如 [[TCP IP]]）
## 常見指令
```filter
// 尋找來源 IP
ip.src== xxx.xxx.xxx.xxx
// 或是（src = 來源 / dst = 目的地）
ip.src== xx.xx.xx.xx or ip.dst == xx.xx.xx.xx
```

[[Port]]
```
// port
tcp.port == 80
```

```
// 網路請求
http.request.method=="POST"
```

不知道 IP 可以用這個指令可取得該網址的 [[IP]]
```terminal
ping {該網址}
````


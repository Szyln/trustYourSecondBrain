# Port 接口
連上 [[IP]] 後，一個 IP 可能有多個 Port 提供不同的 Server
```
// mac 的查詢 port 功能
lsof -nP -i | grep LISTEN
```

## 常見的 Port Number

- 80: HTTP
- 20: FTP
- 53: DNS
- 443: HTTPs
- 3389: 遠端桌面

## 網址
1. 利用裝置輸入網址
```
www.youtube.com
```
2. [[DNS]] 將網址轉換成 [[IP]]
```
208.65.153.238
```
3. [[IP]] 後面接上 Port
```
208.65.153.238:80
```

## Port 不可重複
不能把不同功能開在同一個 Port
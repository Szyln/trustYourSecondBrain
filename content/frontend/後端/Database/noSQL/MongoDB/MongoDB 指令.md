# MongoDB 指令
[[MongoDB 環境建置]] 運行之後
```shell
Sz-de-MacBook-Pro:~ sz$ mongosh

Current Mongosh Log ID: 61b045fbdafe6b9b3b4c2152

Connecting to: **mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000**

Using MongoDB: 5.0.4

**Using Mongosh**: 1.1.6


For mongosh info see: **https://docs.mongodb.com/mongodb-shell/**


To help improve our products, anonymous usage data is collected and sent to MongoDB periodically (https://www.mongodb.com/legal/privacy-policy).

You can opt-out by running the **disableTelemetry()** command.
  

**------**

 **The server generated these startup warnings when booting:**

 2021-12-08T13:05:25.198+08:00: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted

 2021-12-08T13:05:25.198+08:00: Soft rlimits for open file descriptors too low

**------**
```

就可以開始執行指令了，一開始長相會是這樣
```shell
test>
```
## 檢視數據庫
```shell
show dbs
```
## 當前數據庫
```shell
db
```
## 切換（新建）到特定數據庫
如果該名稱的 DB 尚未存在的話就會新建
```shell
use nameDB
```
## 
對照 [[SQL]] 的 table，MongoDB 對應到 collections
```shell
show collections
```

## 當 JS 用
他也是 JS 的 shell，可以運行也可以寫入資料類型
```shell
13 * 2
```
# MongoDB Atlas
> 要注意不同專案不要用到同一個 cluster（collection 要清掉）


雲端版本的 [[MongoDB]]


## Network Access
Current 跟 Anywhere IP 都新增

## Database Access
新增 User

## Database(Cluster)
按 Connect -> Connect your application

### 取得連線 URI
這段的 URI 貼到 `.env` 裡面後把他貼到 mongoose.connect 裡面
```
// .env 檔
DB_CONNECT=mongodb+srv://sz:<換成密碼>@cluster0.hk85a.mongodb.net/<數據庫命名>? retryWrites=true&w=majority
```
>[[dotenv（使用 env 變數）]]

### [[利用 Mongoose 連上 MongoDB]]
```js
// 以下 DB 記得改成用 env 存取 atlas 版本
mongoose.connect(process.env.DB_CONNECT)
```

![[利用 Mongoose 連上 MongoDB#^86a132]]


#js #json #expressJs #mongoose #mogodb 
[Install MongoDB Community Edition on macOS](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-os-x/)

> 現行版本 10.14 以上都支援，但 homebrew 有限支援，10.14 測試可以安裝，可能會需要更新 command line

## 前置
```shell
xcode-select --install
```
## 安裝 mongoDB
```shell
brew tap mongodb/brew
```
```shell
brew install mongodb-community@5.0
```
```shell
brew --prefix
```

## 運行
運行 MongoDB (i.e. the `mongod` process) **as a macOS service**
```shell
brew services start mongodb-community@5.0
```

> 停止
> ```
> brew services stop mongodb-community@5.0
> ```

## 檢查
You should see the service `mongodb-community` listed as `started`.
```shell
brew services list
```

## 連接 Connect and Use MongoDB
[[Kernel#Shell]] 可以打開與 mongoDB 互動的介面
```shell
mongosh
```
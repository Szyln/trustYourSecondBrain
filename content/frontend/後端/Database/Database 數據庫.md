# Database
- 發出請求後，（可能有加密），有確定好就會從數據庫 [[Database 數據庫]] 抓檔案（html, css, js）發給你

## C.R.U.D
 - 所有的 [[DBMS(RDBMS)]] 一定有的四種語法
 - [[ODM]] / [[ORM]] 也會有類似的功能

|[[DBMS(RDBMS)]] / ODM(ORM)|Create|Read|Update|Delete|
|-|-|-|-|-|
|SQL|[[SQL create 製作表格]]|[[SQL read 檢視表格內容]]|[[SQL update 更新既有表格內容]]|[[SQL delete 刪除既有表格內容]]|
|MongoDB|[[MongoDB CRUD#Insertion create]]|[[MongoDB CRUD#find read]]|[[MongoDB CRUD#Update]]|[[MongoDB CRUD#Delete]]|
|Mongoose|[[Create]]|[[Find(Read)]]|[[Update]]|[[Delete]]|

## SQL and NoSQL
|類型|SQL|NoSQL|
|-|-|-|
|定義|Relational DB|SQL 之外|
|構造|table|object(JSON)|
|[[DBMS(RDBMS)]]|[[mySQL]]|[[MongoDB]]|
|優點|高穩定、連結性（歷史久）|高伸縮性、自由度（新）|
|Scaling|Sequential search（慢）|hash function(快)|

>像是個人的檔案資料，每個人會有的內容都不一樣，就適合用 NoSQL，反之，像是產品資訊，有一定規則，就是和 SQL

> Scaling 與網頁開發較無關，主要是講找資料的時候使用的方法
### SQL
- [[SQL]] 彼此有連結的關係，彼此有相通的資料（看起來 coda 的表格的 lookup 功能也是這種類型）

### NoSQL

- [[Key-Value Pair]] 的形式

#### Storage 資料的使用（[[深層拷貝、非 string 類型的資料類型轉換]]）



## 架構
- 每個 [[DBMS(RDBMS)]] / [[ODM]] / [[ORM]] 都有類似的架構，只是對應名稱有點不同
- [[SQL]] 中，製作 table 的時候，會先製作出每個 column 的內容，決定屬性還有條件
- [[Mongoose]] 則是會定義 Schema


|  (R)DBMS | Start from |
|:--------:|:----------:|
| SQL      | Table      |
| MongoDB  | Collection |
| Mongoose | Schema     |





#js #database #json #sql 
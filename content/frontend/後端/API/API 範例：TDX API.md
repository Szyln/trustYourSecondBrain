## API 範例：TDX API
-   [Web API：TDX 觀光 API](https://tdx.transportdata.tw/api-service/swagger)
    -   我想獲得台灣觀光景點資料
    -   我輸入說明文件上的[網址請求](https://ptx.transportdata.tw/MOTC/v2/Tourism/ScenicSpot?$top=30&$format=JSON)方式
    -   TDX 伺服器回應我對應的 JSON 格式資料
    -   [範例 Code](https://codepen.io/hexschool/pen/dyRjQRW?editors=1010)

```js
let data;


axios.get('https://ptx.transportdata.tw/MOTC/v2/Tourism/ScenicSpot?$top=30&$format=JSON').then(function(res){
  let data = res.data;
  console.log(data); 
  document.querySelector('.container').innerHTML = `
 <h1>${data[0].Name}</h1>
 <img src="${data[0].Picture.PictureUrl1}">` 
})

```
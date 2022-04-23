---
title: "vite 發布圖片不會正常顯示問題"
tag: 
- 
---
# vite 發布 gh-page 圖片不會正常顯示
## css background 的解決方式
- 建立  `<root>/public` 路徑，圖放這裡
- `background-image: url(/icon.jpg)` 
	- 不使用這個寫法： `public/icon.png` 
	- 使用這個寫法： `/icon.png`

## img 標籤的 src 解決方式
- 放在 public 沒辦法讀取
- 使用 import 可以但超麻煩


## 還在看的資料
[2022-02-08 vue3+vite assets动态引入图片的几种方式，解决打包后图片路径错误不显示的问题](https://www.jianshu.com/p/ddfb5a8b458b)
[css url() assets in html not handled in build process #3980](https://github.com/vitejs/vite/issues/3980)


#vite #未完成 #js/react #bug
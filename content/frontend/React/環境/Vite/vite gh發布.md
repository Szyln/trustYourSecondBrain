---
title: "vite gh發布"
tag: 
- 
---
# vite gh-page 發布
>[Deploying Vite App to GitHub Pages](https://dev.to/shashannkbawa/deploying-vite-app-to-github-pages-3ane)
## 步驟
### git 建置
```shell
git init
git add .
git commit -m "first-commit"
git branch -M main
git remote add origin http://github.com/username/repo-name.git
git push -u origin main
```

### gh-page 路徑建置
```js
// vite.config.js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'


// https://vitejs.dev/config/
export default defineConfig({
	base: '/slicing.DOYOGA/',		// 這裡寫入 repo 名稱
	plugins: [react()]
})
```

### 生成發布模式
```shell
npm run build
```
#### 預覽發布模式
沒問題之後再發布到 gh-page
```shell
npm run preview
```

### gh-page 分支建立
```shell
git add dist -f
```

```shell
git commit -m "Adding dist"
```

```shell
git subtree push --prefix dist origin gh-pages
```

## 靜態資源（assets）問題
[[vite 發布圖片不會正常顯示問題]]

#vite #js/react 
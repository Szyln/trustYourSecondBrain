# dart-sass(sass) 建置

>[Install Sass](https://sass-lang.com/install)
>[Sass Basics](https://sass-lang.com/guide)

##  安裝到電腦 (global)
### npm
```shell
npm i -g sass
```
### Homebrew (Mac)
[the Homebrew package manager](https://brew.sh/)
```
brew install sass/sass/sass
```

### From Chocolatey or Scoop (Windows)

 [the Chocolatey package manager](https://chocolatey.org/)
```shell
choco install sass
```
或
[the Scoop package manager](https://github.com/lukesampson/scoop) 
```shell
scoop install sass
```

>## 加入到 vite 專案
>引用官方文件：
> ```shell
>npm add -d sass 
> ```

## 執行指令
運行將 `.sass`, `.scss` 編譯成 `.css` 的指令
```shell
sass <路徑/all.scss> <路徑/all.css>
```

## 即時監控更新
每次寫新的 Sass 就要執行一次指令不太實際，可以使用 `-w` （ `--watch` 的縮寫）來執行 
```shell
sass --w <路徑/all.scss> <路徑/all.css>
```

### 簡化指令（選用）
在使用 [[Node]] 環境下， `package.json` 可以加入 `scripts` 方便執行指令更快速
舉例這裡新增 `build-css` 的指令後，就可以縮短這整串，直接輸入 `npm run build-css` 即可
```json
"scripts": {
	"build-css": "sass -w src/style/scss/all. scss src/style/all. css"
},
```


#vite #js/react #css/scss #node/npm 
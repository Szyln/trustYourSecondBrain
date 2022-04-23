---
title: "webpack Get Started"
tag: 
- 
---
## SASS 設定
建議的 sass-loader： [[dart-sass(sass) 建置]]

```shell
npm install sass-loader sass webpack --save-dev
```
```js
rules: [
	{
		test: /\.css$/i,
		// css 設定中再 chain 一個 'sass-loader'
		use: ['style-loader', 'css-loader', 'sass-loader'],
	},
]
```


## 開發工具
像是 live server 的工具
1.  webpack's [Watch Mode](https://webpack.js.org/configuration/watch/#watch)：需要重整
2.  [webpack-dev-server](https://github.com/webpack/webpack-dev-server)：平常都是用這個
3.  [webpack-dev-middleware](https://github.com/webpack/webpack-dev-middleware)

## 除 bug
// tell you where the bug came from

devtool: 'inline-source-map',

## code splitting 
https://webpack.js.org/guides/code-splitting/
可以同時讀取不同 bundle，加速讀取速度


#webpack #js/react 
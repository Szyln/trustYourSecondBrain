https://qiita.com/annaaida/items/f2c372000e8358ea8d8f
[[webpack Get Started]]
対してwebpackは、バンドルツールなのでバンドルに特化していて、**モジュール同士の依存関係をうまい具合に、かつ速く一枚のJavaScriptファイルにバンドル**してくれるものです。
整理、最佳化模組內容，watch 模式中只會

webpackのバンドルが速いという話が出ましたが、なぜかと言うとwebpackのwatchモードでは差分ビルドといって前回保存分と今回の保存分との差のみバンドルしてくれるから。

Webpackとは、CSSやJavaScript、画像など**Webコンテンツを構成するあらゆるファイル(アセット)を「モジュール」**という単位で取り扱い**「バンドル」という１つのファイルに最適な形で変換する**ためのツールです。（バンドルとは複数ファイルを1 枚のファイルにまとめること）

・機能ごとにファイルを分割（モジュール化）する開発ができるから  
・ジュール（npmなどでインストールできるパッケージなど）も利用できるから  
・リクエスト数を減らせるから  
・依存関係を解決したファイルを出力できるから

>`ビルド`  
webpackにおいての「ビルド」は「**バンドルを出力するまでの一連の処理**」という意味で使われていることが多い（気がする）。

## 設定
```js
// webpack.config.js

// output.pathに絶対パスを指定する必要があるため、pathモジュールを読み込んでおく
const path = require('path');

module.exports = {
  // モードの設定、v4系以降はmodeを指定しないと、webpack実行時に警告が出る
	// development, production, none
  mode: 'development',
  // エントリーポイントの設定，從這個檔案開始分析模組的依存關係
  entry: './src/js/app.js',
  // 出力の設定
  output: {
    // 出力するファイル名
    filename: 'bundle.js',
    // 出力先のパス（絶対パスを指定する必要がある）
    path: path.join(__dirname, 'public/js')
  }
};
```

- `Loaders` 將圖像、CSS 等 JS 之外的檔案作為 JS 讀取，在 bundle 前的動作。画像やCSSなどの**JavaScript 以外のファイルをJavaScriptで扱えるように変換**したり、バンドルする前にモジュールに対して実行する機能のこと。TypeScriptをJavaScriptに変換、画像をDataURLに変換、コードをチェックするなど、ローダーによって機能は様々。
	- TS -> JS
	- 圖像 -> DataURL
	- 檢查程式碼等

- `Plugins` モジュールのバンドル時に実行される様々な処理。バンドル時にやりたい処理を呼び出す。

- `resolve` 特定の処理の指定、定義するやつ

- `Browser Compatibility` （どのブラウザに対応するか）

## env
Node.jsの環境変数は、process.envというオブジェクトに格納されます。  
環境変数というのは、アプリケーションを動作させる際の最も基本的な設定内容が入った箱のようなものです。

productionを指定すると本番環境を意味します。  
developmentを指定すると開発環境を意味します。  
指定した内容に基づいた環境設定の動作を反映させることができます。

## webpack-dev-serverとは

簡易的にサーバーを立ち上げつつ「webpack」コマンドを実行してくれるもの

## watchモード

### [](https://qiita.com/annaaida/items/f2c372000e8358ea8d8f#npm-run-watch%E3%81%A8%E3%81%AF)npm run watchとは

開発用のコマンドで、ファイルの変更を監視してブラウザに自動的に反映してくれる

### [](https://qiita.com/annaaida/items/f2c372000e8358ea8d8f#npm-run-build%E3%81%A8%E3%81%AF)npm run buildとは

本番公開用のコマンドで、トランスパイルされ圧縮をして「public」フォルダに吐き出す


https://goworkship.com/magazine/how-to-webpack/
![](https://i0.wp.com/goworkship.com/magazine/app/uploads/2018/09/before-2.png?resize=840%2C473&ssl=1)

#webpack #js/react 
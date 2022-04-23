# container
非滿版的容器，將最重要的內容放在畫面中間

## 響應式的 container
因為非滿版，所以需要響應式的變化來因應各種載具
### 狀況一樣的
- 背景永遠滿版＋內容在電腦版非滿版＋手機版滿版
- 沒有背景＋內容在電腦版非滿版＋手機版滿版
### 狀況不一樣
- 電腦非滿版＋平板、手機滿版

> 可再往下方[[container#bs 的響應式 container]]段落了解

## max-width
此時 max-width 就很重要了，
代表在不需要滿版時，內容最大要多寬
設定會比斷點還要小（因為非滿版）
```scss
.container {
  max-width: 1200px  // 非滿版
  @media (max-width:768px) {
    max-width: 720px // 平板環境非滿版
  }
}
```

## padding
因應縮放，或是不同載具尺寸
可能會導致畫面比設定的 max-width 還要窄
雖然 max-width 的設定，不像 width 一樣寫死
所以不會產生 X 軸
但一樣會因為畫面已經貼到邊上，造成侷促感
會下 padding 來避免這種狀況

```scss
.container {
  max-width: 1200px  // 非滿版
  padding: 0 10px // 畫面介於 1200-768 間，會呈現滿版，左右各間距 10px
  @media (max-width:768px) {
    max-width: 720px // 平板環境非滿版
	padding: 5px // 畫面介於 720px 以下，會呈現滿版， 左右各間距 5px
  }
}
```

## bs 的響應式 container
bs 針對不同情況的 container 有不同的樣式可以設定
![](https://i.imgur.com/B6BHJHH.png)
### 用法
有些內容只有限定電腦版非滿版，更窄的就滿版了，那就也沒必要設定置中了
```scss
.container-lg {
  @media (max-width: 768px) {
  	width:100%; // 到達 md 就滿版
	padding; 0 10px // 還是有左右留白
  }
}
```

### bs 內建的不夠，想客製化 container
```scss
```scss
// Source mixin
@mixin make-container($padding-x: $container-padding-x) {
  width: 100%;
  padding-right: $padding-x;
  padding-left: $padding-x;
  margin-right: auto;
  margin-left: auto;
}

// Usage
.custom-container {
  @include make-container();
}
```

#css #scss #bs
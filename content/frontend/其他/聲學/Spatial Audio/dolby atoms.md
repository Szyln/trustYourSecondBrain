---
title: "dolby atoms"
tag: 
- 
---
# 突破 channel base
5.1
7.1
- pan through array
- bed

![](https://i.imgur.com/ch3bEb8.png)
scalable / adaptive 
- 高解析度
- 高適應性（到客戶端）

![](https://i.imgur.com/Rkl6MF9.png)
- bed 音床，基礎聲音背景
- object 空間中的物件
- 合併起來會是一個 atoms deliverable

## workflow(Protools)
![](https://i.imgur.com/xwHFnWB.png)
![](https://i.imgur.com/AfBuLus.png)
io 藉由 madi 協定傳送到渲染器

![](https://i.imgur.com/FRgW8tp.jpg)

### render input
![[Pasted image 20210917152541.png]]
![[Pasted image 20210917152904.png]]

要講一個音軌channel跟真的喇叭輸出之間的關係

pro tools 音訊設定
input: dolby audio bridge(送到renderer)
![[Pasted image 20210917153059.png]]
### dolby atoms production suite
plugin
處理 atoms 的複雜處理，最後可以 render 到喇叭環境
但沒有太複雜的需求的話，也可接到現成的介面，render 成 binaural 等
![[Pasted image 20210917153355.png]]
一開始可以先用試用版軟體＋耳機做嘗試

## 效能
很吃效能
![[Pasted image 20210917153718.png]]

## dolby cinema
第一間
桃園星光影城

![[Pasted image 20210917154117.png]]
HE RMU= Home Entertainment Rendering Mastering Unit

## MTRX
![[Pasted image 20210917154329.png]]
可以連結到多個 hdx 系統
複雜的大型系統

## binaral 跟 stereo輸出
兩個的渲染不一樣要注意

## 實際設定
io -> bus -> use dolby atoms renderer stereo
default

## panner
dolby atoms panner
也有 pt 內建的 panner

低頻就算 pan 可能效果也不大

覺得要呈現空間感跟石膏翻模很像

bass 組可以放 bed
節奏組 再來華麗無雙


## control
跟studio one 一樣都有觸控版的 controller
空間panning好幫手free

## airpods pro 
![[Pasted image 20210917162616.png]]
# Ambisonics 動手做
## Ambisonics in Reaper
[Ambisonics in Reaper](https://www.youtube.com/watch?v=fc5IXiR4KiQ)
### Why don't you use Reaper?
- 價格讚
- ambisonic 領域中算蠻主流的
- nuendo, ableton, pro tools 其實都可以做到（其他 daw 還是要查）


## 目前有的工具類型
受眾有兩個極端
- 學術派（研究）
- 製作派（劇場、音樂）

導致尋找工具時，可以找到 
- open source 完全免費（開源社區、研究）
- 超貴的工具（有大廠支援）

### free tools
- [IEM](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa3JrMUdmcEZmU1NmazE0YkZCR3JZUDg5Zmp0QXxBQ3Jtc0ttUm04ZlZFUmZZLWJVcGNJRk5kaEVYNHlHZUtIUTZ4S0ZkcV9EUnZuYlNReUI4X1Q1NUFYMlk2UWhhem9TamxrRmY2RXRtMWR3eVlXWkdQbWVHY1M3TTA0V2NPemwtaGZIOTFNV2V6a2YwX2I3eFdBUQ&q=https%3A%2F%2Fplugins.iem.at%2F)
	- 7OA
- [SPARTA](https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbUVoWWlId0JWZXlJOHR5YUowQVphVjJ4UXo4QXxBQ3Jtc0ttTlNjNk1tYmVhY1NvTmdKTmZUMlAyMlVEaDVlM2UwVTVyQWpKLV91OFl0NEo2Z3Zua041T2hBWmlYbjhRdG5GSFZfNXd3all3Q1pGNmtEVmkyMXl5STVYZDl3QTBhV1phZWdqNS1pUUZic3daS1NrQQ&q=http%3A%2F%2Fresearch.spa.aalto.fi%2Fprojects%2Fsparta_vsts%2F)
	- 7OA
- [ATK](https://www.ambisonictoolkit.net/)
	- FOA

## workflow	(ATK)
![](https://www.ambisonictoolkit.net/assets/images/documentation/workflow/atk-network.png)
### Author 生產
讀取或產生 soundfield ，進行**編譯**
Capture or synthesise an Ambisonic soundfield.

### Image 加工
對空間加工，使原物件產生原本沒有的互動效果
Spatially filter an Ambisonic soundfield.

### Monitor 監管
監控產出符合聆聽者環境的效果
Playback or render an Ambisonic soundfield.
## Reaper IEM 建置
[IEM官方demo](https://www.youtube.com/watch?v=wTNe4P6sYTg&list=PLLnvq7Y-dSoaEERYb3eIjdj2rJt1tYKL8&index=1)
[IEM官方詳細介紹](https://plugins.iem.at/docs/plugindescriptions/)
### instrument track
#### 物件導入到場景（stereo -> ambisonic (7OA)）
routing -> track channel -> 64ch
#### panner 讓物件真的動起來
FX -> IEM(stereo encoder)
![](https://i.imgur.com/hGrn2wF.png)

![](https://i.imgur.com/f6M5mHp.png)
水平/垂直
但只是導入到場景內，還是會只有 2ch，stereo encoder 是要讓 stereo 可以換成 ambisonic  

### master track
#### 場景
routing -> track channel -> 64ch（目前的 monitor 還是只有在 2ch ）

#### decode
如果沒有 decode 其實 master track 聆聽的結果是不會呈現 360 度的 
 nx head track waves
 ### 輸出 bounce
 - decode 要關掉
 



## Reaper ATK 建置
[atk+reaper+蚊子聲贊喔beeformat](https://youtu.be/ClgVMjczaFc) 
- Ambisonic Toolkit
- FOA
- 這個可以試試，decode 有 HRTFs preset
- atk 官網有提供 sample 音檔

### instrument track
routing -> track channel -> 4ch
#### panner
FX -> ATK FOA Planewave 
![](https://i.imgur.com/XwGmZsm.png)

可以再看官網的其他複雜建構
#### 手動改變automation
- 手繪
- 錄製
![](https://i.imgur.com/3tFOzH2.png)
把 azimth 抓出來 autimation
- letch
### master track 
routing -> 4ch
#### decode
![](https://i.imgur.com/RXc1SHo.png)
FX -> ATK FOA Decode Binaural
需要選 HRTF

### 輸出
master 的 fx (decode)記得關
![](https://i.imgur.com/KqH9SyH.png)



## Reaper ambiX 建置
[ambiX給的文獻](http://www.matthiaskronlachner.com/wp-content/uploads/2013/01/ICSA2014_KronlachnerZotter_AmbisonicTransformations.pdf)
[ambiX給的文獻2](https://lac.linuxaudio.org/2013/papers/51.pdf)
### decode
#### preset
binaural decoder presets：如果想從耳機聽(含 decoder matrices + binaural loudspeaker impulse responses)
```
Windows 7/8: _C:\Users\username\AppData\Roaming\ambix\binaural_presets\_  
MacOS: _~/Library/ambix/binaural_presets/_  
Linux: _~/ambix/binaural_presets/_
```
如果要自己做 preset，要自己建立 decoding matrix，可以用**Ambisonic Decoder Toolbox** by **Aaron Heller** 然而看起來爆幹難[[Source repo](https://bitbucket.org/ambidecodertoolbox/adt.git "Ambisonic Decoder Toolbox Repository")] [[LAC Article](http://lac.linuxaudio.org/2014/papers/17.pdf "Ambisonic Decoder Toolbox Linux Audio Conference Article")].
## zylia zm-1 錄的
這真的很誇張w
[3OA的直升機](https://www.youtube.com/watch?v=RnpqaQB8b5k)
- [ ] [直升機音效](https://soundbible.com/323-Military-Helicopter.html)（等等自己試試看）
只有左右的定位，沒有辦法清楚表達「空間的反射」

## logic pro X
## Ambisonic data exchange formats
[Ambisonic data exchange formats](https://en.wikipedia.org/wiki/Ambisonic_data_exchange_formats)
### 混亂時期
在早期的多軌錄音有過格式混亂的時期
在研究 HOA 的系統時，並沒有一個統一的格式標準，而且在聲學中並還沒有導入太多有關球諧函數的概念，所以有些人透過化學、量子力學、電腦製圖等其他領域去設計格式，導致不同的研究雖然最終是在講同一件事但卻無法相容。
### 格式必須的要件
- [Component ordering](https://en.wikipedia.org/wiki/Ambisonic_data_exchange_formats#Component_ordering)
-  [Normalisation](https://en.wikipedia.org/wiki/Ambisonic_data_exchange_formats#Normalisation)
-  [Polarity](https://en.wikipedia.org/wiki/Ambisonic_data_exchange_formats#Polarity)
#### Component ordering
##### FuMa
![](https://i.imgur.com/GKkWdEh.png)
##### ACN
![](https://i.imgur.com/evF1bgW.png)
SN3D, N3D 都用這個
#### Normalisation
- maxN
- SN3D
#### Polarity
### Reference table of layouts and normalisations
For Furse-Malham (and traditional B-format), sort by FuMa column and multiply the spherical harmonic by the maxN factor.
-   For basic AmbiX, sort by ACN and use the SN3D factor.
-   For extended AmbiX and all other combinations, good luck!
### 檔案格式
- `.amb`：FuMa
- `.caf`： AmbiX
### Ambisonic Channel Number (ACN)
![](https://i.imgur.com/e9hD5Vj.png)

為了未來有更高的 HOA，目前已經引入了 ACN(Ambisonic Channel Number) 這個公式
目前已經廣泛運用在 SN3D, N3D 等格式中
## SN3D
[HOA Technical Notes - SN3D B-Format](https://blueripplesound.com/b-format)
### B-Format
B-Format 是在 HOA 中最主流的音訊格式，他是 multichannel 但不對應聲道，解碼後，會直接呈現一個 soundfield

傳統的 multichannel 是對應聲道的，好處就是不需要再解碼，就可以直覺對應視聽設備

B-format 乍聽之下似乎有點麻煩，但他可以解決傳統 channel-based 的問題，就是不管視聽配置為何，只需要處理一次，而不需為不同配置重新混音了

### Coordinate System
ambisonic 的 Coordinate System 一般設定 X 前，Y 左，Z 上

### Content
有三種狀況可以使用 B-Format

-   [[Ambisonics#Panning]]
-   [[Ambisonics#Recording]]
-   [[Ambisonics#Upmixing]]

### Panning
將音訊編譯進 HOA 最簡易的方法，就是將 mono pan（或我們說 encode）進一個 B-Format 裡，符合他的格式

目前有幾種 B-format，數學上是一樣的，但並不相容，目前最主流是 SN3D

#### FuMa, N3D and SN3D
- FuMa 是早期的經典格式（自1970）
- SN3D 目前主流（例如 YT）
- N3D 與 SN3D 有點不同，在數學上比較易於使用，但在工作室內比較少見
### Recording
使用 ambisonic 麥克風
### Upmixing
![](https://blueripplesound.com/sites/default/files/images/o3aup51.png)
如果想要將 channel based 轉為 B-Format，有幾種方法
- 把每個聲道都當做一個聲音物件，把他們各自 pan 到 soundfield 中原有的位置
- 另一種就是使用現成的 upmixing 的插件或工具

# 其他
[logic pro X 作法](https://beyondstereoentertainment.wordpress.com/2020/10/15/spatial-audio-in-a-daw/)

[學習推薦ㄉ目錄](https://www.courville.uqam.ca/ambisonic/)
[MPEG-H](https://www.iis.fraunhofer.de/en/ff/amm/broadcast-streaming/mpegh.html)
https://github.com/hyperdelia/hex002-womb

[sandbox測試了很多東西？]https://codesandbox.io/u/kirbysayshi

https://medium.com/samsung-internet-dev/audio-on-the-web-for-games-and-vr-efcd523a3d58

[宇宙](https://www.youtube.com/watch?v=Wl8axtBNdQw)
preset
https://www.youtube.com/watch?v=VCXQp7swp5k

fb htrfs
https://news.nweon.com/86521

openal 3d audio
https://openal.org/games/


題外
https://threejs-journey.xyz/

網站
https://gothamsiti.it/
https://www.dermast.art/
https://www.chiaraluzzana.com/work

[high fidelity](https://www.highfidelity.com/solutions/spatial-audio-api-and-sdks)

calla
https://www.calla.chat/
推薦網站
https://www.awwwards.com/

mozilla vr
https://blog.mozvr.com/
互動藝術程式創作入門
https://hahow.in/courses/5d1ba52a0d5f3b0021dbb996/main




## sony 360 reality audio
[Sony 360 Reality Audio review: This headphone-virtualization system expands music beyond your head](https://www.techhive.com/article/3519268/sony-360-reality-audio-review.html)
## free daw which is cool
[tracktion](https://www.tracktion.co-m/)
LMMS
## 把手機當成頭部追蹤器 
目前 mac 好像沒有在支援
暫緩這篇
[opentrack phone head track](https://www.youtube.com/watch?v=6Pts_sotjMA)

## list of ambisonic software wiki
[List of Ambisonic software](https://deletionpedia.org/en/List_of_Ambisonic_software)

## plugins for PD
[cubemixer](https://ambisonics.iem.at/xchange/products/cubemixer)

## logic pro 
https://japanese.engadget.com/apple-logic-pro-025039322.html?1
開始支援 atoms

那本書
https://link.springer.com/chapter/10.1007/978-3-030-17207-7_1
---
title: "jitsi"
tag: 
- 
---
# jitsi 低延遲設定（台灣地區）
## 推薦給音樂相關的語音、視訊交流
- 對想開歌窗的人來說，jitsi 可以直接輸出瀏覽器音效（chrome 限定）
- jitsi 是開源軟體，比較不用被大公司綁架
- 就算沒有知識背景，也可以用現成的台灣伺服器使用，實現低延遲效果
- 音質可以自己設定
- 
## 其他選擇
 想開歌窗需要權衡很多要素
 - 錢
 - 方便性
 - 使用限制
 - 品質

|使用軟體|環境建置（伴奏）|使用限制|品質|參加簡單度|
|-|-|-|-|-|-|
|discord|自助+閹割*|需註冊|音質差*|需註冊|
|直播|自助|一人主持|佳（可自訂）|無腦|
|jitsi|有內建(chrome)|需搭配其他平台來邀請他人|佳（可自訂）|無腦|
|其他會議軟體|自助|-|不可調整|-|

>註：discord 可以透過升級（付費）的方法取得較高音質的輸出

條列一下[用公開的 Jitsi 服務也可以上遠端音樂課？](https://blog.abysm.org/2021/06/hd-audio-using-public-jitsi-server/)提到的重點

- 音質可調整
- 有內建輸出瀏覽器音效功能（chrome限定）
- 有台灣伺服器低延遲

- jitsi 就算沒有自己架站的知識背景，也可以用現成


config.audioQuality.stereo=true
- `disableAP` ：以下三項全關
- `disableAGC`：Auto Gain Control
- `disableAEC`：Acoustic Echo Cancellation
- `disableNS`：Noise Suppression（降噪）
- `disableHPF`：Disables Highpass Filter


config.audioQuality.opusMaxAverageBitrate=128000
config.enableNoisyMicDetection=false

https://jitsi.pdis.dev/唱兩首來打扣耐久#config.enableNoisyMicDetection=false&config.stereo=true&config.audioQuality.opusMaxAverageBitrate=92000&config.p2p.enabled=false&config.startAudioOnly=true&config.prejoinPageEnabled=true&config.enableWelcomePage=true
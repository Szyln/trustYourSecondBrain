---
title: "Quartz 發布 obsidian"
tag: 
- 
---
# Quartz 發布 Obsidian
>[Quartz](https://quartz.jzhao.xyz/)

[[Quartz 特性]]

## 安裝步驟
>[Get started](https://quartz.jzhao.xyz/notes/setup/)
>- 你需要的知識：
>	- [ ] git, Github 基礎理解
>	- [ ] 終端機基礎操作

### [[Fork]] 原作者的 repo
>[quartz 的 repo](https://github.com/jackyzha0/quartz)

這樣你就會在你的 github 上看到一個內容一樣的檔案
![](https://i.imgur.com/DNBGWvR.png)

### clone 到自己的本機
把這個檔案 clone 下來到你要的位置
```shell
git clone https://github.com/jackyzha0/quartz.git
```

## 管理、新增筆記
建議使用 Obsidian，以下用 Obsidian 示範
### 連結既有 repo 筆記 submodule

[git submodule 教學](https://kmsheng.medium.com/git-submodule-%E6%95%99%E5%AD%B8-96ab0255c88c)

https://github.com/shiftyp/submodule-gh-pages-example
[Obsidian 遠端、發佈相關](其他/硬體、生產力/Obsidian/Obsidian%20遠端、發佈相關.md)
### Obsidian 設定
將一個 vault 放到 `/content` 資料夾內，必須的設定如下
![](https://i.imgur.com/YEir2BK.png)
模版設定要打開
![](https://i.imgur.com/z6wVNIn.png)
以後每個檔案都用得到，建議可以設定 Obsidian 快捷鍵
![](https://i.imgur.com/qFPgAwE.png)

### Quartz 設定
`/content/templates` 資料夾不要動

## 排除想要保持私人的筆記
>[Ignoring Notes](https://quartz.jzhao.xyz/notes/ignore-notes/)

## 發布筆記
>[Deploying Quartz to the Web](https://quartz.jzhao.xyz/notes/hosting/)

```toml
baseURL = "https://<YOUR-DOMAIN>/"
```
```toml
baseURL = "https://<YOUR-GITHUB-USERNAME>.github.io/quartz/"
```
```yaml
- name: Deploy  
  uses: peaceiris/actions-gh-pages@v3  
  with:  
	github_token: ${{ secrets.GITHUB_TOKEN }} # this can stay as is, GitHub fills this in for us!
	publish_dir: ./public  
	publish_branch: master
	cname: <YOUR-DOMAIN>
```



#obsidian/quartz

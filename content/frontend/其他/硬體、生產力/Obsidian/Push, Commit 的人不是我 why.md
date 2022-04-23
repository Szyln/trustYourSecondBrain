# Push 的人不是我 why
>[Why are my commits linked to the wrong user?](https://docs.github.com/en/pull-requests/committing-changes-to-your-project/troubleshooting-commits/why-are-my-commits-linked-to-the-wrong-user)



1. 把 github 的設定內的 email 貼到以下指令內
![](https://i.imgur.com/lq40cUO.png)
```shell
$ git config --global user.email "<設定內的email>"
```
2. 然後檢查一下
```shell
$ git config --global user.email
email@example.com
```

## 還是怪怪的話再做這個
[Adding an email address to your GitHub account](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-email-preferences/adding-an-email-address-to-your-github-account)

#git #obsidian 
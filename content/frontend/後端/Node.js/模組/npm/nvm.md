# nvm
[nvm github](https://github.com/nvm-sh/nvm)：詳細指令請參照
[nvm：快速安裝、切換不同版本的 Node.js](https://noob.tw/nvm/)

安裝
```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
```

結束後先重開 terminal

```shell
command -v nvm
```

## 指定安裝版本
```shell
nvm install node # 最新版
```

```shell
nvm install 14.7.0 # or 指定版本
```

---
## 安裝過程大概長這樣
```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 14926  100 14926    0     0  21470      0 --:--:-- --:--:-- --:--:-- 21476
=> Downloading nvm from git to '/Users/sz/.nvm'
=> 正複製到 '/Users/sz/.nvm'...
remote: Enumerating objects: 354, done.
remote: Counting objects: 100% (354/354), done.
remote: Compressing objects: 100% (302/302), done.
remote: Total 354 (delta 40), reused 160 (delta 27), pack-reused 0
接收物件中: 100% (354/354), 214.65 KiB | 959.00 KiB/s, 完成.
處理 delta 中: 100% (40/40), 完成.
* （開頭指標分離於 FETCH_HEAD）
  master
=> Compressing and cleaning up git repository

=> Appending nvm source string to /Users/sz/.bash_profile
=> Appending bash_completion source string to /Users/sz/.bash_profile
=> You currently have modules installed globally with `npm`. These will no
=> longer be linked to the active version of Node when you install a new node
=> with `nvm`; and they may (depending on how you construct your `$PATH`)
=> override the binaries of modules installed with `nvm`:

/usr/local/lib
├── corepack@0.10.0
├── gulp@4.0.2
=> If you wish to uninstall them at a later point (or re-install them under your
=> `nvm` Nodes), you can remove them from the system Node as follows:

     $ nvm use system
     $ npm uninstall -g a_module

=> Close and reopen your terminal to start using nvm or run the following to use it now:

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
Sz-de-MacBook-Pro:~ sz$ nvm use node
-bash: nvm: command not found
Sz-de-MacBook-Pro:~ sz$ 
```




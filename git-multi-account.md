# 在同台電腦要對一個以上的遠端檔案庫做操作時的做法
## 情境說明
有一個個人的檔案庫(GitHub)及公司的檔案庫(GitLab)，每次都會需要去切換使用者來跟遠端的檔案庫做溝通。
通過以下的設置利用SSH驗證來達成簡化操作流程的目的。

## 作法

1. 製作一個SSH Key

```
ssh-keygen -t rsa -C "your.email@example.com" -b 4096
```

上面的指令會要求輸入SSH Key的檔案名稱，預設會是*id_rsa*
不要改掉此SSH，因為這是你本來帳號所使用的Key
所以請將此檔案名稱重新命名(ex: id_rsa_github)。

2. 將此Key加入

```
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_rsa_github
```

3. 新增SSH Config檔案

```
touch config
```
建立config檔案(在~/.ssh下)

4. 打開Config檔，在裡面設定如下

```
# gitLab.com
Host gitlab.com
RSAAuthentication yes
IdentityFile ~/.ssh/id_rsa

# github.com
Host github.com
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_github
```

IdentityFile按照相對應的檔名設定

5. 在github/gitlab中新增ssh key

6. 測試是否正確連線(請重開git bash再做此步驟)

```
ssh -T git@<gitdomain>.com
#<gitdomain>: git domain(ex: github)
```
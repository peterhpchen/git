# Git Config
> 設定Git設定檔

## 初次設定
設定`user`資訊, 於`git commit`時需要
```
git config user.name '[name]'
git config user.email '[email]'
```

## Git設定檔的層級
一個Git檔案庫會有三個不同層級的設定檔, 以下依照優先權介紹

1. `.git/config`: 在檔案庫的.git資料夾下會有一個config檔案, 此為這個檔案庫的設定檔, 只有這個檔案庫可以使用此設定, 同時也是對於這個檔案庫來說優先權最高的
    * 使用`git config --local`設定此層級資料(為預設行為, 可以省略`--local`)
2. `~/.gitconfig`: 在登入帳號目錄下的`.gitconfig`是第二層級的設定檔, 此帳號下可以使用此設定, 只有第一層級的設定檔未設定的項目才會生效
    * 使用`git config --global`設定此層級資料
3. `etc/gitconfig`: 這個設定只會在前兩項沒設定的項目才會生效, 同時也是涵蓋範圍最大(所有登入帳號及檔案庫)的設定檔
    * 使用`git config --system`設定此層級資料

## 移除git config 設定
```
git config --unset [config name]
```

## 設置指令別名
設定別名以減少輸入指令所消耗的時間
```
git config alias.[command alias name] [command name]
```
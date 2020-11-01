# 回到執行任何指令之前

使用時有可能會使用錯指令，這時可以使用 `git reflog` ，此指令會 show 出使用者所下的所有指令，並且依照指令的順序編號，這使我們可以使用 `git reset --hard` 回到之前的狀態。

```bash
git reflog # 列出使用的指令
git reset --hard HEAD@{5} # 回到五個指令之前的狀態
```

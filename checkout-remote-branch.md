# checkout 遠端分支

checkout 遠端有而本機沒有的分支，可以使用:

```bash
git fetch # 取得遠端資訊
git checkout -t <remote>/<branch> # 建立新分支，會由 <remote> 的 <branch> 狀態點建立
```

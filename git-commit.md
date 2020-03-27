# Git Commit

`git commit` 是將目前在 staging area 中(`git add` 的檔案)提交至 git repo 上:

```bash
git commit -m "Add README"
```

如果沒有加 `-m` ，則會跳出編輯器(預設是 vi)供你編輯提交訊息。

## 修改最近一個 commit

有時會手誤將錯誤的資訊提交，可能是提交訊息或是作者...等等資訊，這時可以用 `--amend` 做修改:

```bash
git commit --amend -m "Add README and License"
```

上面這個例子就修改了提交訊息。

要修改作者也行:

```bash
git commit --amend --author="peterhpchen <peterhsinpingchen@gmail.com>"
```

實際操作後會發現到雖然我們只修改作者但依然會跳出修改提交訊息的編輯畫面，如果不想要跳出編輯的話可以加上 `--no-edit` :

```bash
git commit --amend --author="peterhpchen <peterhsinpingchen@gmail.com>" --no-edit
```

> 避免修改已 push 的 commit，如果修改已 push 的 commit 的話會需要用 push force 才能提交到遠端 repo ，用 push force 會將原本遠端的 commit 修改，如果其他人使用此 repo 的話會造成對方的 branch 錯誤。

## 參考資料

* [Stack Overflow: How to change the commit author for one specific commit?
](https://stackoverflow.com/a/3042512)
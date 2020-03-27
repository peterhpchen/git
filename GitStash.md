# Git Stash
> 儲存目前的變更至Stash

在工作時會遇到突然有急單打斷目前正在進行的工作, 當工作進行到一半時有更緊急的事件需要處理, 可是目前的工作又還沒告一個段落不想要做commit的動作, 這時就可以將目前的工作進度暫存至Stash中
```
git stash
```
上面的指令會將你的目錄下的變更儲存至Stash中, 使目錄恢復至HEAD所指的Commit節點

緊急事件完成後, 我們要恢復原來的工作狀態, 可以使用下列指令恢復最新的stash至你的工作目錄
```
git stash apply
```
stash的實做是透過stack的方式, 所以也可以使用: 
```
git stash pop
```
如果在stash中存了多個儲存時, 用`git stash list`來列出目前有的堆疊
```
git stash list
```
堆疊的名稱會像下列所示
```
stash@{0}: WIP on master: 049d078 added the index file
stash@{1}: WIP on master: c264051 Revert "added file_size"
stash@{2}: WIP on master: 21d80a5 added number to log
```
取出特定的儲藏
```
git stash stash@{1}
```
這樣會取出第二個儲藏的堆疊。

## 查詢 stash 存放的變更紀錄

當需要查詢 stash 中存有那些檔案及變更時，可以用 `git stash show` 來查詢:

```bash
git stash show
```

像上面這樣不帶參數時，會查最近的 stash ，也就是 `stash@{0}` ，如果要指定查詢的 stash 的話可以在參數中指定:

```bash
git stash show stash@{1}
```

`stash show` 的 `options` 與 `git diff` 是一樣的，因此可以用 `--name-only` 來輸出只有檔案名稱的列表:

```bash
git stash show --name-only
```
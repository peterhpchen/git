# git remote

設定追蹤的遠端 Repository。

我們需要設置追蹤的遠端庫才能做拉取或推入的動作。

## 瀏覽目前設置的遠端庫

```bash
git remote -v
```

```bash
origin  http://test/hello.git (fetch)
origin  http://test/hello.git (push)
```

* `origin`: remoote name
* `http://test/hello.git`: repository 路徑

## 修改目前的遠端庫

```bash
git remote set-url origin  http://test/hello.git
```

修改 origin 的路徑為 http://test/hello.git

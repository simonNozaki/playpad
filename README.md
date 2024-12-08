# playpad

REPLで試すには少しスペースが狭い感じがするが、わざわざ命名して残すほどでもない書き捨てのスクリプトを管理しやすくする実行可能メモ帳。

各種言語でのコンパイルや実行はこのプロジェクトでは感知せず、あくまでファイルの生成・削除に特化する。

## 前提条件

- Ruby: 3.3.5
- Visual Studio Codeでの実行を推奨

## 使い方

メモ書きとなるファイルは `jots` 配下に置かれる。

```bash
> rake --tasks
rake jots:new[ext]       # Create a new jot with the file extension
rake jots:rm[file,exts]  # Delete jots by some condition
```

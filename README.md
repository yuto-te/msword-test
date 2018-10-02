## msword-test
pandocを使ってMicrosoft Office Wordで作成した.docxファイルの差分が見えるようになった

### 設定

#### Pathにpandocが存在することが前提

.gitattributesに
```
*.docx diff=pandoc
```
を追加する．

.git/configに
```
[diff "pandoc"]
    textconv=pandoc --to=markdown
    prompt = false
[alias]
    wdiff = diff --word-diff=color --unified=1
```
を追加する．

### 使用方法
`git wdiff sometext.docx` でdocxファイルの差分が見られる．

### 参考文献
[Microsoft Word + pandoc + git によるドキュメント管理](https://qiita.com/mazzzzam/items/ed6f516eb663056b0ffe)

救済が得られた
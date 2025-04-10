# 色々
## github上でvscodeを開く
* github.comをgithub.devに変更する
    * 例: https://github.dev/EbookFoundation/free-programming-books/blob/main/books/free-programming-books-ja.md

## 検索
* ~ under the hood とつけるとフレームワークの内部の情報などを拾いやすい

## dockerでのコマンド（todo:後で別に分けた方が良い..）
* dbとアプリをcomposeでまとめてあるが、dbをdownさせたくない時
```bash
# appサービスだけを再起動（既存のコンテナを削除して新しく作り直す）
docker compose up --force-recreate app

# appサービスだけをビルドして再起動
docker compose up --build app
```
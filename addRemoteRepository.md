# 提出リポジトリのつくりかた
====

手順としては以下です。
- Github にリポジトリを新規作成する
- git remote add コマンドでリポジトリを追加する

## Github にリポジトリを新規作成

[この organization](https://github.com/DevelopmentPractice201308) でリポジトリを新規に作成します。手順としては
- 右上の create a new repo ボタンをクリック
- owner を DevelopmentPractice201308 に変更
- リポジトリ名は自分のユーザアカウント_sample_app としてください (sample_app の場合)
- あとは通常のリポジトリの作成方法と同様です

## git remote add コマンド

以下のコマンドにより、.git/config にエントリが追加されます。

    git remote add github git git@github.com:DevelopmentPractice201308/yamanetoshi_sample_app.git

これで以下のコマンドで作成したリポジトリに push が可能となります。

    $ git push -u github master

sample_app については DevelopmentPractice201308 という organization への提出は必須です。

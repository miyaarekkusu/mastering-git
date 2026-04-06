# Git/GitHub練習

## Gitバージョン確認

git --version

## Gitユーザー、メール名設定

git config --global user.name 'alex.dev'
git config --global user.email 'alexdev@gmail.com'

## Git空きリポジトリ作成

git init

git config --global init.defaultBranch main

- master から mainになる

## Gitステータス参照

git status

## Git選択したファイルを追加

git add ##

## Git全ファイルを追加

git add ./

## Gitコミット(コードの今の状態を複写)

git commit -m 'READMEファイルを追加'

## Git現在状態変更

ステータスからハッシュ値を参照
git checkout 'ハッシュ値'

## メインの状態に戻すためのコマンド

git checkout -f main

2種類のリポジトリが存在する。ローカルとリモートリポジトリ。git initをするときローカルが作成される。GitHubなどのバージョンの管理サービスのサーバーにプッシュし、リモートリポジトリから協力者などとコードの共有する。

## masterブランチをmainという名前に変更

git branch -M main

自分のパソコン上のローカルリポジトリと、リモートリポジトリをリンク(GitHubでリポジトリを作成する必要がある)

git remote add something_else リモートリポジトリurl

リンクしたら、プッシュするときに毎回urlを貼るではなく、originとして扱いできる

git push -u origin main

- 'feature-branch'からこの内容を追加

## Git BranchとMergeの役割

# Branchの役割

- 「作業分担」を作る仕組み
- メインの開発ラインから独立した作業空間を作ることができる。メインの作業ラインを触らず。例えばmainブランチで安定板が動いているとき、新機能の開発やバグ修正は別ブランチで行います。こうすることで、途中の壊れたコードがmainに影響しません。

git branch feature/login # ブランチを作成
git checkout feature/login # ブランチに移動

省略型
git checkout -b feature/login

- git push --set-upstream origin feature/login
- git push -u origin feature-branch
  ローカルブランチをリモートに送りつつ、追跡関係を設定するコマンド。両方同じ動作

- upstream設定済みなら'git push'だけでok

# Mergeの役割

別ブランチでの変更をまとめて、メインのラインに統合することが目的です。作業が完了したらmainに切り替えてからマージします

git checkout main
git merge feature/login

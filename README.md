## Hello, Git!

- 'feature-branch'からこの内容を追加

## Git BranchとMergeの役割

## Branchの役割

- 「作業分担」を作る仕組み
- メインの開発ラインから独立した作業空間を作ることができる。メインの作業ラインを触らず。例えばmainブランチで安定板が動いているとき、新機能の開発やバグ修正は別ブランチで行います。こうすることで、途中の壊れたコードがmainに影響しません。

git branch feature/login # ブランチを作成
git checkout feature/login # ブランチに移動

省略型
git checkout -b feature/login

## Mergeの役割

別ブランチでの変更をまとめて、メインのラインに統合することが目的です。作業が完了したらmainに切り替えてからマージします

git checkout main
git merge feature/login

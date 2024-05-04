---
title: git游戏
toc: true
date: 2024-05-04 22:05:17
tags: 工具向
description: 学习如何使用git的小游戏
---
基础篇：

### 第一关：学习git commit

”

一個 commit 在 git repo 中會記錄目錄下所有文件的快照。感覺像是大量的複製和貼上，但 git 的速度更快！

git 希望 commit 儘可能地不占空間，所以每次進行 commit 的時候，它不會單純地複製整個目錄。實際上它把每次 commit 視為從目前的版本到下一個版本的變化量，或者說一個 "（delta）"。

git 會保存 commit 的歷史紀錄，所以，絕大部分的 commit 的上面都會有 parent commit，在我們的圖形表示中，箭頭方向表示從 parent commit 到所對應的 child commit，保存這樣子的一個歷史紀錄是非常有用的。

要學的東西有很多，但現在你可以把 commit 當作是當下的 project 的快照。commit 不佔空間且可以快速切換！

“

![img](/img/QQ截图20240504220402.png)

两次 git commit即可

```
git commit
git commit
```

### 第二关： 建立git branch

”

git 的 branch 只是一個指向某個 commit 的 reference，只要記住使用 branch 其實就是在說：「我想要包含這一次的 commit 以及它的所有 parent 的 commit。」

“

![img](/img/QQ截图20240504221304.png)

```
git branch bugFix
git checkout bugFix
```

### 第三关：git merge

”

一個 commit 如果有兩個 parent commit 的話，那就表示：「我想把這兩個 parent commit 本身及它們的 所有的 parent commit 都包含進來。」

“

![img](/img/QQ截图20240504222044.png)

先在bugfix commit ，再在main分支commit，最后merge

```
git branch bugFix
git checkout bugFix
git commit
git checkout main
git commit
git merge bugFix
```

### 第四关：git rebase

”

*rebasing* 是 merge branch 的第二種方法。rebasing 就是取出一連串的 commit，"複製"它們，然後把它們接在別的地方。

“

![img](/img/QQ截图20240504223932.png)

先commit bugFix分支，再commit main分支，最后切换到bugFix分支rebase到main上

```
git branch bugFix
git checkout bugFix
git commit
git checkout main
git commit
git checkout bugFix
git rebase main
```

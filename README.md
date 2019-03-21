# 记录一些git的操作命令

## git clone

* 将远程仓库克隆到本地来

## git status

* 查看已经发生变更的文件

## git add

* 将本地仓库的改变添加到暂存区

## git commit

* 将暂存区的文件提交到本地仓库

## git push

* 将本地文件更新到远程仓库

## git diff

* 查看本地与远程仓库的差异

## git pull

* 将远程仓库更新到本地

## git merge [branch]

* 在master下合并分支的内容

## 主干合并分支

* 先进入分支更新至最新的仓库代码，git checkout [branch], git pull
* 切换回主干, git checkout master
* 再主干上合并分支branch，git merge branch --squash
* 提交合并后的代码: git commit -m ''
* 最后push到远程仓库
* 或者直接git pull origin [branch]，然后再将改动进行提交。

## 分支合并主干

* 先在主干更新至最新, git pull(master)
* git checkout [branch]
* git merge master
* git commit -m ''
* git push origin [branch]
* 或者直接git pull origin master，然后再将改动进行提交。

## 在分支上对上一次的提交进行修改

* git add *
* git commit --amend
* git push [origin (branch)] -f

## git rebase [--abort][`master`][`-i HEAD~3`]

* 合并多条commit
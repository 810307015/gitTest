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
* git pull的默认行为是git fetch + git merge。
* git pull --rebase 是git fetch + git rebase。

## git fetch

* 从远程获取最新版本到本地，不会自动合并分支。

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

## git rebase [--abort][`master`][`-i HEAD~3`][--skip]

* `git rebase`从新定义起点
* `--abort`会回到rebase操作之前的状态，之前的提交的不会丢弃。
* `master`合并主干修改
* `--continue`用于修复冲突，提示开发者，一步一步地有没有解决冲突，fix conflicts and then run "git rebase --continue"。
* `-i HEAD~3`将分支上与HEAD版本相近的三条数据的提交合并。
* `--skip`强制继续`rebase`，将引起冲突的commits丢弃掉。

```command
pick：保留该commit（缩写:p）
reword：保留该commit，但我需要修改该commit的注释（缩写:r）
edit：保留该commit, 但我要停下来修改该提交(不仅仅修改注释)（缩写:e）
squash：将该commit和前一个commit合并（缩写:s）
fixup：将该commit和前一个commit合并，但我不要保留该提交的注释信息（缩写:f）
exec：执行shell命令（缩写:x）
drop：我要丢弃该commit（缩写:d）
```

## git reflog

* 找回丢失的commit信息。
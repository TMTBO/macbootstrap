# Git 的常用封装

## 帮助信息

1. 输入 `gh COMMAND` 可以获取对应命令的帮助，比如 `gh commit`，等价于 `git help --man commit`，将在终端中打开这个命令的帮助文档

## 配置用户信息

1. `gcn bestswifter` 配置用户名，等价于 `git config user.name`
2. `gcng bestswifter` 配置全局用户名，等价于 `git config --global user.name`
3. `gce ktzhang@bestswifter.com` 配置邮箱，等价于 `git config user.email`
4. `gceg ktzhang@bestswifter.com` 配置全局邮箱，等价于 `git config --global user.email`

## git log

这个命令非常常用，也非常复杂，常见的有以下几种：

1. 输入 `gg`，它会单行展示提交历史，也支持展示分支的关系
   如图所示：
   ![](http://images.bestswifter.com/QQ20171220-113955@2x.png)
2. 输入 `gg --stat`，它在 gg 的基础上会展示每次提交具体改动的文件
   如图所示：
   ![](http://images.bestswifter.com/QQ20171220-114134@2x.png)

## git diff

1. 输入 `gd` 即可查看工作区内的变动，等价于命令 `git diff`
2. 输入 `gds` 可以查看暂存区的变动，也就是查看那些被 `git add` 了的文件的变动，等价于命令 `git diff --staged`
3. 输入 `gdc` 可以查看最近一次提交的变动，等价于命令 `git diff HEAD^ HEAD`

## git push

1. 输入 `gpo` 可以快速的将提交推送到远程仓库，等价于命令 `git push origin`，如果不写分支名则默认把当前分支推送到远程仓库对应的分支上
2. 如果远程仓库的名称不是默认的 origin，可以使用 `gp repo_name`，因为 `gp` 等价于 `git push`

## git commit

1. 输入 `gcam` 可以在不 add 的前提下一次性提交所有改动，等价于命令 `git commit -a -m`

## git remote

1. 输入 `grsh` 可以查看所有的远程仓库，输入 `grsh origin` 可以查看 origin 仓库中的分支、track 信息，等价于命令 `git remote show`

## 常见工作流

注意，这里说的工作流不是 git-workflow 的意思，而是一些常见命令的组合。

1. 输入 `gsfrs` 可以先暂存(stash) 当前改动，拉取远程代码，rebase 以后再应用暂存，等价于命令 `git stash;git fetch;git rebase;git stash pop;`。**警告⚠️** 如果 rebase 的过程中遇到冲突，不会自动 pop 暂存，需要手动执行命令

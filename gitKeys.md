## git相关命令

- 提交文件至暂存区：git add file

- 暂存区文件进行提交：git commit -m "messgae"

- 查看当前状态：git status

- 查看提交历史：git log

- 查看历史命令：git reflog

- 撤销或回退版本：git reset hard HEAD^

- 丢弃工作区的修改：git checkout -- file

- 删除工作区的文件：git rm file

### 远程仓库相关

- 本地修改（分支）推送至Github：git push origin <branchNme>

- 从远程仓库克隆：git clone <link>

- 要查看远程库的信息： git remote

- 查看远程库的详细内容：git remote -v

- 抓取远程新提交：git pull
> 如果git pull提示no tracking information，则说明本地分支和远程分支的链接关系没有创建，用命令git branch --set-upstream-to <branch-name> origin/<branch-name>。

### 分支基本命令

- 查看分支：git branch

- 创建分支：git branch <name>

- 切换分支：git checkout <name> 或者 git switch <name>

- 创建+切换分支：git checkout -b <name> 或者 git switch -c <name>

- 合并某分支到当前分支：git merge <name>

- 删除分支：git branch -d <name>
>如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。-D的D一定要大写

- 查看合并分支图：git log --graph
> Fast forward 模式，这种模式下，删除分支后，会丢掉分支信息。
> 所以在合并时，可以强制关闭，例如在master分支时使用 git merge --no-ff -m "merge with no-ff" dev；
> 因为本次合并要创建一个新的commit，所以加上-m参数，把commit描述写进去。

### bug分支
- 把当前工作现场“储藏”起来，等以后恢复现场后继续工作：git stash

- 查看隐藏的列表：git stash list

- 恢复现场：git stash apply

- 删除现场：git stash drop

- 恢复并删除现场：git stash pop

- 复制一个特定的提交到当前分支：git cherry-pick <commit-id>

### 分支的其他操作

- 把本地未push的分叉提交历史整理成直线：git rebase

### 标签

- 给当前分支添加标签：git tag <name>
> 默认标签是打在最新提交的commit上的。有时候，如果忘了打标签，比如，现在已经是周五了，但应该在周一打的标签没有打，怎么办？
> 方法是找到历史提交的commit id，然后打上就可以了

- 查看标签信息：git show <tagname>

- 创建带有说明的标签：git tag -a <tag-name> -m "message" <commit-id>
> 用-a指定标签名，-m指定说明文字

> 注意：标签总是和某个commit挂钩。如果这个commit既出现在master分支，又出现在dev分支，那么在这两个分支上都可以看到这个标签。

- 标签删除：git tag -d <tag-name>
> 创建的标签都只存储在本地，不会自动推送到远程。所以，打错的标签可以在本地安全删除。

- 标签推送向远程：git push origin <tagname>
  
- 一次性推送全部尚未推送到远程的本地标签：git push origin --tags

- 删除远程标签，要先删除本地的，然后：git push origin :refs/tags/<tagname>

## command 操作命令 or vim 命令

- 删除命令：rm
- 使用vim打开文件：vi file
- 显示文件内容：cat file
- 展示目录下内容：ls / dir

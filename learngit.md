# learngit
learngit

`$ git init`

进入一个文件夹后使用该命令，将该文件夹初始化为一个git可以管理的仓库

`$ git add file`

将文件加入到仓库中，该文件必须在git管理仓库的目录或子目录下

`$ git commit -m "xxxx"`

**commit**命令 每次改动之后都需要向仓库进行提交 -m 后面的参数是本次提交的说明 修改多个文件后可以一次性提交

`$ git status`

显示仓库的状态，例如一个文件被修改过但是没有提交这次修改

`$ git diff file`

查看文件的变动位置和内容

`$ git log`

查看历史版本，简化版查看使用参数`--pretty=oneline` commit id经过**SHA1**加密
**HEAD**代表当前版本,**HEAD**^代表上一个版本，**HEAD～100**代表往上100个版本

`$ git reset --hard HEAD^`

将当前版本回退到上一个版本，回退过后用`log`指令查看版本库状态发现当前版本的版本号已经看不到了

`$ git reset --hard commitid`

可以直接恢复到commitid对应的版本

`$ git reflog`

`reflog`指令用来记录每一次指令，如果不记得commitID可以根据提交时的说明找到对应的版本

`$ git diff HEAD -- file`

查看工作区和版本库里面最新版本的区别

`$ git checkout -- file`

file在未添加到暂存区时，撤销修改就回到了和版本库一模一样的状态
file添加到暂存区后又做了修改，撤销修改就回到了添加到暂存区后的状态
**checkout**其实是用版本库里的版本替换工作区的版本，无论修改还是删除，都可以*一键还原*

`$ git reset HEAD file`

可以将暂存区的修改回退到工作区

`$ git rm file`

从版本库中删除该文件，删除之后务必`commit`

###远程仓库###

`$ git remote add origin git@github.com:lizhigeng66/repo-name.git`

关联远程仓库，repo-name是仓库名称

`git push -u orgin master`

关联之后第一次推送master分支的所有内容。之后每次更新不加`-u`即可推送最新修改。

##Git 指令和技巧

1: ```git init```
仓库的初始化，在当前目录中新建一个git代码库。

2: ```git init [project-name]```
在当前目录新建一个目录并对其初始化。

3: ```git clone [url]```
从远端克隆一个项目到当前目录中。会在当前目录中新建一个和远端项目名相同的目录。

4: ```git branch```
显示所有本地分支

5: ```git branch -r```
显示所有远端分支(r是remote的缩写，代表远端)

6: `git branch -a`
显示所有本地和远端分支(a是all的缩写，代表全部)

7: `git branch [branch-name]`
新建一个分支

8: `git checkout -b [branch-name]`
新建一个分支，同时切换到该分支上

9: `git checkout [branch]`
切换到指定分支上

10: `git checkout -`
切换到上一个分支

11: `git merge [branch]`
合并指定分支到当前分支

12: `git branch -d [branch]`
删除指定分支

13: `git push origin --delete [branch]`
    `git branch -dr [remote/branch]`
删除远端分支

14: `git add [file1] [file2] ...`
添加指定文件到暂存区，在push之前调用，把需要推送到远端的代码送上车

15: `git add [dir]`
将指定目录添加到暂存区，包括该目录下所有内容

16: `git add .`
将当前目录中所有文件添加到暂存区

17: `git rm [file] [file2]...`
将工作区中的文件删除，并把删除的文件放入暂存区，远端也会执行删除操作

18:`git rm --cached [file]`
停止追踪指定文件，文件会保留在工作区，但是该文件的变化不会被git检测

19: `git mv [file-origin] [file-renamed]`
修改文件名，并将文件放入暂存区

20: `git commit -m [message(自己写的备注信息，一般用来标注本次提交的改动)]`
提交暂存区到仓库区

21: `git commit [file1] [file2] ... -m [message]`
提交暂存区指定的文件到仓库区

22: `git commmit -a`
提交工作区自上一次commit操作之后的变化，直接到仓库区

23: `git commit -v`
提交时显示所有的diff信息

24: `git commit --amend -m [message]`
使用一次新的commit来替代上一次commit，如果代码没有任何变化，则用来修改commit的备注信息

25: `git status`
查看所有变更的文件

26: `git log`
显示当前分支的版本历史

27: `git log --stat`
显示commit历史，以及每次commit发生变更的文件

28: `git log -S [keyword]`
根据关键词搜索提交历史

29: `git log [tag] HEAD --pretty=format:%s`
显示某个commit之后所有的变动，每个commit占一行

30: `git log [tag] HEAD -grep feature`
暂时不知道

31: `git log --follow [file]`
    `git watchchanged [file]`
显示某个文件的修改历史

32: `git log -p [file]`
显示指定文件的每一次diff记录

33: `git -5 --pretty --oneline`
显示过去5次提交记录

34: `git shortlog -sn`
显示所有提交过的用户，按照提交次数排序

35: `git diff`
显示暂存区和工作区的差异

36: `git blame [file]`
显示指定文件在什么时候，由什么人修改过

37: `git diff HEAD`
显示暂存区和上一个commit的差异

38: `git diff [first-branch] [second-branch]`
显示两个分支间的差异

39: `git diff --shrotstat "@{0 day age}"`
显示今天写了多少代码

40: `git show [commit]`
显示某次提交的元数据和内容变化

41: `git show [commit]:[filename]`
显示最后一次提交发生变化的文件

42: `git reflog`
显示当前分支最近几次提交信息

43: `git fetch [remote]`
下载远端仓库所有变动

44: `git remote -v`
显示所有的远程仓库

45: `git remote show [remote]`
显示某个远端仓库的信息

46: `git remote add [name] [url]`
添加一个新的远端仓库，并命名

47: `git pull [remote] [branch]`
拉取远端仓库的变化，并合并到本地

48: `git push [remote] --force`
推送本地指定分支到远端

49: `git push [remote] --all`
推送所有本地分支到远端

50: `git checkout [file]`
恢复暂存区的指定文件到工作区

51: `git checkout [commit] [file]`
恢复某个commit的指定文件到暂存区和工作区

52: `git checkout`
恢复暂存区的所有文件到工作区

53: `git reset [file]`
重置暂存区的指定文件，与上一次commit保持一致，当前工作区不变

54: `git reset --hard`
重置缓存区与工作区，与上一次commit保持一致

55: `git reset [commit]`
重置当前分支的指针为指定的commit，同时重置暂存区，当前工作区不变

56: `git reset --hard [commit]`
重置当前分支的HEAD为指定commit同时重置暂存区和工作区,与指定commit一致

57: `git reset --keep [commit]`
重置当前HEAD为指定commit,但保持暂存区和工作区不变

58: `git revert [commit]`
新建一个commit,用来撤销指定commit,覆盖指定commit的变化,并且应用到当前分支

59: `git stash`
    `git stash pop`
暂时将未提交的变化移除，稍后再移入
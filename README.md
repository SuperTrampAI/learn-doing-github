# learn-doing-github

## 配置
1. git config --global user.name "Example Surname"
2. git config --global user.email "your.email@gmail.com"
3. git config --global alias.add-commit '!git add . -A && git commit' 自定义组合命令 使用为： git add-commit -m "message"
4. ssh-keygen -t rsa -C "youremail@example.com" windows下打开git bash创建ssh key
  在用户主目录下有.ssh目录，文件名中有：id_rsa(私钥)和id_rsa.pub(公钥)


gitk --all 启动一个图形界面
git add . 是把文件修改添加到暂存区
git commit 把暂存区的所有内容提交到当前分支

## 创建
1. touch text.txt  创建文件
2. mkdir book 创建文件夹
3. mv text.txt book 移动text.txt 到book目录下，前提是text.txt和book文件夹必须要同一个目录下
## 显示
1. pwd 显示当前路径
2. ls 查看当前路径下的文件名列表

## 删除
1. rm text1.txt 删除文件
2. rm -r book 删除文件夹
3. reset 清空base中的所有内容
4. git rm  然后git commit

## push to github
1. git add book  把文件加入到缓冲区
   git add .  添加当前目录的所有文件到缓存区
   git add -p 添加每个变化前，都会要求确认。对于同一个文件的多个变化，可以实现分次提交
2. git commit -m "message"
3. git commit --amend -m "更改commit message"
4. git push 推送到github
5. git add . && git commit -m "More chaanges - typo in the commit message" 添加文件到仓库中，并commit
6. git commit -a -m "File book.txt is now removed" -a 的使用，用处在哪？
7. git add -A .  用法暂时不明确

git rm -r --cached .metadata
git rm --cached book  停止追踪指定文件，但该文件会保留在工作区


$ git mv [file-original] [file-renamed]  改名文件，并且将这个改名放入暂存区

## 分支 使用新命令 git switch 进行分支切换
1. git branch 列出所有本地分支
2. git branch -r 列出所有远程分支
3. git branch -a 列出所有本地分支和远程分支
4. git branch supertramp 新建分支，但仍然停留在当前分支

## 分支操作
1. git checkout -b dev 创建分支并切换
   git checkout master 切换分支
2. git merge dev 合并指定分支(dev)
3. git merge --no-ff -m "message" dev 合并分支，可以使用git log git log --graph --pretty=oneline --abbrev-commit 查看分支历史
git show  推出git show ：键入q

## 查看
1. git status 显示有变更的文件/是否修改过文件
2. git log 显示当前分支的版本历史
3. git log --stat 显示commit历史，以及每次commit发成变更的文件
4. git whatchanged 显示某个文件的版本历史，包括文件改名
5. git log -p file 显示指定文件相关的每一次diff
6. git log -5 --pretty --oneline 显示过去5次提交
   git log --pretty=oneline
7. git shortlog -sn 显示所有提交过的用户，按提交次数排序
8. git blame file 显示指定文件是什么人在什么时间修改过
9. git diff 显示暂存区和工作区的代码差异
10. git diff --cached README.md 显示暂存区和尚一个commit 的差异
    git diff HEAD -- book.txt 查看工作区和版本库里面最新版本的区别
11. git 显示指定文件相关的每一次diff []...[] 两次提交之间的差异
12. git diff --shortstat "@{0 day ago}" 显示今天写了多少行代码/修改的内容
13. git show 显示每次提交的元数据和内容的变化
14. git show --name-only  显示某次提交发生变化的文件
15. git reflog  显示当前分支的最近几次提交/查看命令历史
16. git rebase 从本地master拉取代码更新当前分支

## 远程同步
1. git fetch 下载远程仓库的所有变动
2. git remote -v 显示所有远程仓库
3. git remote show 显示某个远程仓库的信息
4. git remote add [shortname] [url] 增加一个新的远程仓库，并命名
5. git pull 取回远程仓库的变化，并与本地分支合并
6. git push 上传本地指定分支到远程仓库
7. git push --force 强行推送当前分支到远程仓库，即使有冲突
8. git push --all 推送所有分支到远程仓库

## 撤销
1. git checkout -- [file] 恢复暂存区的指定文件到工作区 /丢弃工作区的修改
    file 修改后，还没有放到暂存区，撤销修改就回到和版本库一样
    file已经添加到暂存区，又做了修改，撤销修改就回到调价到暂存区后的状态
2. git checkout .  恢复暂存区的所有文件到工作区
3. git reset [file] 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
4. git reset --hard 重置暂存区与工作区，与上一次commit保持一致
6. git reset --hard HEAD^ 回退到上一个版本
7. git reset HEAD book.txt  把暂存区的修改撤销，重新回到工作区。HEAD 表示最新版本



git tag v1.0 打标签
git log --pretty=oneline --abbrev-commit 查看历史提交记录
git tag v0.9 f52c633 为指定哪一次的提交打标签，f52c633为commit id
git tag version1.6 -m 'version 1.6'

git merge testing 合并分支

git branch -d testing 删除分支

git mergetool 解决冲突

git rebase -i HEAD~7 合并最后的七个分支

cat  book.txt 打开txt文件

## vi操作
1. i 进入编辑模式
2. esc 进入命令模式
3. q 退出不保存，如果有改动文件，则报错(先键入:符号)
4. q! 强制退出，舍弃改动的内容(先键入:符号)
5. x 保存并退出(先键入:符号)

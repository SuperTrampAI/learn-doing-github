# learn-doing-github

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

## push to github
1. git add book  把文件加入到缓冲区
  a. git add .  添加当前目录的所有文件到缓存区
  b. git add -p 添加每个变化前，都会要求确认。对于同一个文件的多个变化，可以实现分次提交
  c.
  d.
2. git commit -m "message"
3. git push 推送到github

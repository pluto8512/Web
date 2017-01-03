#Git
1. 在项目的根目录初始化一个仓库： git init
2. 查看项目目录： ls
3. 查看隐藏的.git目录： ls -a

> .git文件夹就是本地仓库
  正确的提交方式是先pull再push,防止远端有文件而本地没有该文件而提交不上

###配置用户信息
1. 配置用户名: git config user.name "testName"
2. 配置邮箱: git config user.email "test@sina.com"
3. 查看配置好的用户信息： git config --list

###提交代码
1. 从当前目录add: git add ./xxx.xxx
2. commit到本地仓库: git commit -m "我们写的代码"
3. 检查有没有需要提交的代码: git status
关键词： modified->修改 （ps:红色表示没有提交到暂存区 绿色表示没有提交到仓库）
working directory clean 工作目录干净的 不需要提交的

> 添加当前目录下修改或添加的的所有文件到暂存区add: git add . 
add commite合并: git commit -a -m "合并提交" 

###设置提交时忽略的文件
1. 创建.gitignore文件
2. 添加要忽略的文件当前目录下的路径： /xxx.xxx

###查看日志 比对文件差异
1. 查看日志： git log （简洁形式：git log --oneline）
2. 比对文件差异：git diff 版本号1 版本号2 被比对的文件路径

###版本回退
1. 回退到上次提交：git reset --hard Head （上上次提交 git reset --hard Head~1）
2. 按版本号回退： git reset --hard Head 版本号

###查看之前每次操作
git reflog (ps: 结合版本回退就可以方便的回退到之前的任意一个版本)

> head指向哪个版本，该版本就是你上次提交的版本，也就是你将在上面修改代码的版本
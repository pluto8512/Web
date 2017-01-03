#Git
1. 在项目的根目录初始化一个仓库： git init
2. 查看项目目录： ls
3. 查看隐藏的.git目录： ls -a

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

*. 添加当前目录下修改或添加的的所有文件到暂存区add: git add . 
add commite合并: git commit -a -m "合并提交" 

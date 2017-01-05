###browsersync使用方法
1. 在要监视的文件的目录打开命令行
2. 启动browsersync: `browser-sync start --server --files "./xxx.html,./app.css,./*.css,./*.*" `
`ps:(*.css:当前目录下的全部css文件，*.*:当前目录下的全部文件)`
3. 终止browsersync: ctrl+c

###browsersync异步刷新css样式
1. 添加监视： `browser-sync start --server --files "./xxx.html,./xxx.css"`
2. 异步加载外联css样式： 点击按钮才出现的样式就可以异步修改了

###browsersync浏览器兼容性测试
1. 同时打开多个浏览器
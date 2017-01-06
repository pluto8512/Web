###gulp安装部署
1. 安装gulp-cli命令 : npm install gulp-cli -g
2. 检测gulp : gulp -v
3. 在项目里面安装gulp : npm install gulp --save-dev
4. 在项目根目录创建 :  gulpfile.js
5. 在gulpfile.js里面写代码： 
```javascript
// 得到gulp对象
var gulp = require('gulp');
// 新建任务
gulp.task('script',function(){
   //匹配
   gulp.src('./js/index.js')
   .pipe(gulp.dest('./js/dist'));
   //指定输出的目录   
});
```
6. 使用gulp : gulp [任务名]

![](/assets/gulp命令执行.png)
### gulp的使用方法
+ 首先下载插件
+ 在gulpfile.js里面写'搬运'代码： 

```javascript
// 得到gulp对象
var gulp = require('gulp');
// 新建任务
gulp.task('script',function(){
   //匹配
   gulp.src('./js/index.js')
   .pipe(gulp.dest('./js/dist'));
   //指定输出的**目录**   
});
```
+ 在gulpfile.js里面写'搬运压缩js'代码：

```javascript
var gulp = require('gulp');
// 引入gulp-uglify代码压缩插件
var uglify = require('gulp-uglify');

// 新建任务
gulp.task('script',function(){
    //匹配
    gulp.src('./js/index.js')
        .pipe(uglify())
        .pipe(gulp.dest('./js/dist'));
    //指定输出的目录
});
```
+ 在gulpfile.js里面写'搬运合并压缩js'代码：

```javascript
var gulp = require('gulp');
// 引入gulp-uglify代码压缩插件
var uglify = require('gulp-uglify');

// 新建任务
gulp.task('script',function(){
    //匹配
    gulp.src(['./js/1.js','./js/2.js'])
        .pipe(concat('./js/index.js'))
        .pipe(uglify())
        .pipe(gulp.dest('./js/dist'));
    //指定输出的目录
});
```
+ 在gulpfile.js里面写'搬运压缩html'代码：

```javascript
var gulp = require('gulp');
// 引入gulp-uglify代码压缩插件
var uglify = require('gulp-uglify');

// 新建任务
gulp.task('script',function(){
    //匹配
    gulp.src(['./js/1.js','./js/2.js'])
        .pipe(concat('./js/index.js'))
        .pipe(uglify())
        .pipe(gulp.dest('./js/dist'));
    //指定输出的目录
});
```


+ 使用gulp : gulp [任务名]
![](/assets/gulp命令执行.png)

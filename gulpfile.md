+ 安装 npm i -g gulp
+ npm init 文件夹中
+ npm i gulp --save-dev

```javascript

'use strict';

// 文件名是固定的
// 此处程序都是由node完成

// 引入模块
let gulp = require('gulp');

// 注册一个任务 合并压缩--
// 通过 gulp say名字 可以执行
gulp.task('say', function() {
    console.log('hello world');
});

// 复制文件任务
gulp.task('copyFile', function() {
    // gulp.src 取文件
    // pipe(可以执行函数)
    // gulp.dest 目的*通配符号
    gulp.src('src/*.html').pipe(gulp.dest('dist/'));
});

// 自动化监视, 当文件完成时候 执行后面的任务
// gulp.watch('srcfile.name'， ['taskname', 'taskname2']);
gulp.task('watchFile', function() {
    gulp.watch('src/*.html', ['copyFile']);
});


```
## 常用插件
+ 一些常用的插件 安装引入后直接使用 .pipe(less()).pipe(cssnano())..
+ less 编译
+ gulp-connnect 创建本地服务器 --->> browser-sync 代替
+ gulp-concat 合并文件
+ gulp-uglify 最小胡 js文件
+ gulp-rename 重命名文件
+ gulp-cssnano 压缩css 文件
+ gulp-minify-html 压缩html 文件
+ gulp-imagemin 最小化图像

## browser-sync 同步插件
```javascript

var bs = require("browser-sync").create();
// http://localhost:3001 是界面设置管理
// .init starts the server
gulp.task('server', function() {
    bs.init({
        server: {
            baseDir: './', // 启动服务的目录 默认 index.html    
            index: 'index.html' // 自定义启动文件名
        }
    });
})

```
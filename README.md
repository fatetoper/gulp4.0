# gulp

使用gulp命令行\脚本命令需添加相对路径的工作目录,默认为当前目录;
主要为了解决不用每次都重新安装依赖
```
gulp task --url=path
```

单独运行task时不会构建,需要添加mode参数,默认为空;
```
gulp --url=path --NODE_ENV=production
```
## 注意事项

静态文件添加版本号必须使用引号;  

需要作为雪碧图合并的图片不加引号,在雪碧图使用'?v='过滤,添加了版本号的就不会合并为雪碧图;  

##
* 创建基本结构
* 热更新
* 代理
* sass,css,js压缩并生成map文件
* 雪碧图
  >实现了两种  
  >1.gulp --url=path sprite 生产单独的sprite文件 只包含img/icon开头的图片  
  >2.在每个css中混入
* 图片压缩
* 静态文件添加版本号
  > 如果需要控制版本号长度,gulp-rev-append-all->index.js两处'?v=' + hash.digest('hex')添加字符串截取即可

## 脚本命令

注意修改脚本命令的url参数(工作目录)  

folder 创建基本结构  
dev 开发环境(不会构建,只是热更新、代理)  
clean 删除dist的文件  
build 构建  
build:clean 删除并构建  

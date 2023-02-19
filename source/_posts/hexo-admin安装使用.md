title: hexo-admin安装使用
author: wps
tags: []
categories: []
date: 2023-01-30 17:55:00
---
1.安装
``` bash
$ npm install hexo-admin --save
```
2.密码保护
部署在GitHub的跳过这一步

3.发布文章
进入博客根目录下的_config.yml添加以下代码
```yml
admin:
  deployCommand: './admin_hexo.sh'
```

新建脚本文件写入以下代码
``` bash
#!/usr/bin/env sh
hexo clean
hexo g -d
```
win系统的话需要修改一下依赖文件
根目录进入node_modules\hexo-admin\deploy.js
var proc = spawn(command, [message], {detached: true})
改为 var proc = spawn((process.platform === "win32" ? "hexo.cmd" : "hexo"), ['d']);
``` js
module.exports = function (command, message, done) {
  done = once(done);
  var proc = spawn((process.platform === "win32" ? "hexo.cmd" : "hexo"), ['d', '-g']);
  var stdout = '';
  var stderr = '';
  proc.stdout.on('data', function(data){stdout += data.toString()})
  proc.stderr.on('data', function(data){stderr += data.toString()})
  proc.on('error', function(err) {
    done(err, {stdout: stdout, stderr: stderr});
  });
  proc.on('close', function () {
    done(null, {stdout: stdout, stderr: stderr});
  });
}
```
进入后台点击Deploy
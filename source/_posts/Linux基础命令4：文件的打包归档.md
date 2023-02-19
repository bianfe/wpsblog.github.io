title: Linux基础命令4：文件的打包归档
date: 2023-02-07 19:57:48
categories:
- 运维
tags:
- Linux
---
- tar
  - 打包文件
  - 语法：tar [主选项+辅选项] 文件或目录
    主选项：
    - -c: --create 新建一个压缩文档
    - -x: --extrac t解压文件
    - -t：--list 查看压缩文档里的所有内容
    - -r：--append 向压缩包里追加文件
    - -u：--update 更新原压缩包中的文件


  - 使用其他工具打包压缩一起
  - 语法：
    辅助选项：
    - -z: 是否用gzip压缩或解压
    - -j： 是否用bzip压缩或解压
    - -v： 显示操作过程
    - -f：使用文档名
    - -C：切换到指定目录
    - --exclude FILE：在压缩过程中，不要将FILE打包

## 一.打包


压缩为gzip格式
```
# tar -czvf
```

压缩为bzip2格式
```
# tar -cjvf
```

## 二.解压

解压为bzip2格式
```
tar -xzvf file.tar.gz
```

解压为bzip2格式
```
tar -xjvf file.tar.bz2
```



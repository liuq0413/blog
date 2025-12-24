---
title: Ubuntu操作
date: 2025-12-15 14:41:10
tags: 
categories: Ubuntu
---
# Ubuntu的操作

## 文件操作

### 查看文件大小
### 1. ls查看文件
    ls -lh
- l是显示详细信息，包括大小。
- h是让文件大小以人类易读的单位（KB, MB, GB）显示，而不是字节数

### 2. du查看目录
    du -sh Documents/
    du -sh Documents/* 可以列出文件下文件夹或者文件最大
- s是总结，只显示总大小，不显示目录里每个子项。
- h同样易读


### 3. 管道符
**｜** ：左边命令的输出，变成右边命令的输入

    ls -t | head -n -3 | xargs rm -f

####  xargs 命令
 > xargs把管道传来的每一行文本变成参数，传给后面的命令

### 4. zip
zip目录，排除某些文件

    zip -r archive.zip my_project/ -x "my_project/secrets.txt" "my_project/*.log"

#### unzip
    unzip archive.zip -d /path/to/target/
- -d参数指定目标目录，目录不存在时会自动创建。


### 5. rm






## 系统操作


# mac的操作

## 文件操作

### 1. 显示隐藏文件

    cmd + shift + .

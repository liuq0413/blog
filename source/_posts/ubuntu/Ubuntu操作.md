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



### 6. 文件权限

#### chmod 修改文件权限

**数字方式（八进制）**
    chmod 755 filename
    chmod 644 filename
- 三个数字分别代表：所有者(u)、所属组(g)、其他人(o)的权限
- 4=读(r)，2=写(w)，1=执行(x)
- 755 = rwxr-xr-x（所有者可读写执行，组和其他人可读执行）
- 644 = rw-r--r--（所有者可读写，组和其他人只读）

**符号方式**
    chmod u+x filename          # 给所有者添加执行权限
    chmod g-w filename          # 移除组的写权限
    chmod o=r filename          # 设置其他人权限为只读
    chmod a+x filename          # 给所有人添加执行权限
    chmod u=rwx,g=rx,o=r filename  # 分别设置三种用户的权限
- u=所有者(user)，g=组(group)，o=其他人(other)，a=所有人(all)
- +添加权限，-移除权限，=设置权限

**递归修改目录权限**
    chmod -R 755 directory/
- -R参数递归修改目录及其所有子文件和子目录的权限

#### chown 修改文件所有者

    chown user:group filename
    chown user filename         # 只修改所有者
    chown :group filename       # 只修改所属组
    chown -R user:group directory/  # 递归修改目录
- 需要root权限或sudo执行
- -R参数递归修改目录及其所有子文件

#### 查看文件权限

    ls -l filename
- 第一列显示权限，如：-rwxr-xr-x
- 第一位：-表示文件，d表示目录
- 后9位：每3位一组，分别表示所有者、组、其他人的rwx权限




## 系统操作


# mac的操作

## 文件操作

### 1. 显示隐藏文件

    cmd + shift + .

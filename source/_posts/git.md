---
title: git
date: 2025-12-16 01:23:13
tags:
categories: git 
---

# git 

## git reset

> git reset --soft \<commit>
- 撤销上一次提交，但保留所有更改在暂存区，方便你修改后重新提交。


## git restore
- 撤销 工作区​ 的修改（文件已修改，但未执行 git add）

> git restore \<file-path>
```bash
    git restore readme.md  # 放弃 readme.md 文件的所有未暂存修改
```
2. 撤销 暂存区​ 的修改（文件已执行 git add，但未 git commit）
> git restore --staged \<file-path>
```bash
    git restore --staged readme.md  # 将 readme.md 从暂存区撤出
```

- 等效旧命令：git reset HEAD \<file-path>


## 创建git

### git init



### 问题

## ？ 添加子module
> git submodule stats # 显示submodules 
> git submodule add -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly # 添加子模块


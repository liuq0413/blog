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


## git add

- 添加文件到暂存区

> git add \<file-path>
```bash
    git add readme.md        # 添加单个文件
    git add .                # 添加所有修改的文件
    git add *.js             # 添加所有 .js 文件
```

## git commit

- 提交更改到本地仓库

> git commit -m "message"
```bash
    git commit -m "更新文档"           # 提交并添加提交信息
    git commit -am "快速提交"          # 添加并提交已跟踪的文件
    git commit --amend                 # 修改最后一次提交
    git commit --amend -m "新信息"     # 修改最后一次提交信息
```

## git push

- 推送本地提交到远程仓库

> git push [remote] [branch]
```bash
    git push                        # 推送到默认远程分支
    git push origin main            # 推送到 origin 的 main 分支
    git push -u origin main         # 首次推送并设置上游分支
    git push --force                # 强制推送（谨慎使用）
    git push --tags                 # 推送所有标签
```

## git pull

- 从远程仓库拉取并合并更改

> git pull [remote] [branch]
```bash
    git pull                        # 拉取默认远程分支
    git pull origin main            # 从 origin 拉取 main 分支
    git pull --rebase               # 使用 rebase 方式拉取
```

## git status

- 查看工作区和暂存区的状态

> git status
```bash
    git status                      # 查看详细状态
    git status -s                   # 查看简短状态
    git status --short              # 同上
```

## git log

- 查看提交历史

> git log [options]
```bash
    git log                         # 查看完整提交历史
    git log --oneline               # 单行显示提交历史
    git log -n 5                    # 只显示最近 5 条提交
    git log --graph                 # 图形化显示分支
    git log --all --graph --oneline # 显示所有分支的图形化历史
    git log --author="name"         # 查看特定作者的提交
```

## git diff

- 查看文件差异

> git diff [options]
```bash
    git diff                        # 查看工作区与暂存区的差异
    git diff --staged               # 查看暂存区与最后一次提交的差异
    git diff HEAD                   # 查看工作区与最后一次提交的差异
    git diff commit1 commit2        # 查看两次提交之间的差异
    git diff -- file-path           # 查看特定文件的差异
```

## git stash

- 暂存当前工作区的更改

> git stash [options]
```bash
    git stash                       # 暂存当前更改
    git stash save "message"        # 暂存并添加说明
    git stash list                  # 查看所有暂存列表
    git stash pop                   # 应用并删除最新的暂存
    git stash apply                 # 应用最新的暂存但不删除
    git stash drop                  # 删除最新的暂存
    git stash clear                 # 清空所有暂存
```

## 创建git

### git init

- 初始化一个新的 git 仓库

> git init [directory]
```bash
    git init                        # 在当前目录初始化
    git init my-project             # 在指定目录初始化
```

### git clone

- 克隆远程仓库到本地

> git clone [url] [directory]
```bash
    git clone https://github.com/user/repo.git
    git clone https://github.com/user/repo.git my-folder
    git clone -b branch-name https://github.com/user/repo.git
```

### 创建分支

- 创建并切换到名为 "name" 的新分支。
> git checkout -b name

> git switch -c name
```bash
    git checkout -b feature-branch  # 创建并切换到新分支（旧方式）
    git switch -c feature-branch   # 创建并切换到新分支（新方式）
    git branch feature-branch      # 只创建分支，不切换
```

## git branch

- 分支管理

> git branch [options]
```bash
    git branch                      # 查看所有本地分支
    git branch -a                   # 查看所有分支（包括远程）
    git branch -r                   # 查看远程分支
    git branch -d branch-name       # 删除已合并的分支
    git branch -D branch-name       # 强制删除分支
    git branch -m old-name new-name # 重命名分支
```

## git merge

- 合并分支

> git merge [branch]
```bash
    git merge feature-branch        # 合并 feature-branch 到当前分支
    git merge --no-ff feature-branch # 不使用快进合并
    git merge --abort               # 取消合并
```

## git checkout

- 切换分支或恢复文件

> git checkout [branch|file]
```bash
    git checkout main               # 切换到 main 分支
    git checkout -b new-branch      # 创建并切换到新分支
    git checkout -- file-path      # 恢复文件到最后一次提交的状态
```

## git remote

- 管理远程仓库

> git remote [command]
```bash
    git remote -v                   # 查看所有远程仓库
    git remote add origin url       # 添加远程仓库
    git remote remove origin        # 删除远程仓库
    git remote rename old new       # 重命名远程仓库
    git remote set-url origin url   # 修改远程仓库地址
    git remote show origin          # 查看远程仓库详细信息
```


## git fetch

- 从远程仓库获取更新但不合并

> git fetch [remote]
```bash
    git fetch                       # 获取默认远程仓库的更新
    git fetch origin               # 从 origin 获取更新
    git fetch --all                # 获取所有远程仓库的更新
```

## git rebase

- 变基操作，将当前分支的提交重新应用到目标分支上

> git rebase [branch]
```bash
    git rebase main                # 将当前分支变基到 main
    git rebase -i HEAD~3           # 交互式变基最近 3 个提交
    git rebase --continue          # 继续变基操作
    git rebase --abort             # 取消变基操作
    git rebase --skip              # 跳过当前提交
```

## git tag

- 标签管理

> git tag [options]
```bash
    git tag                         # 查看所有标签
    git tag v1.0.0                  # 创建轻量标签
    git tag -a v1.0.0 -m "版本1.0"  # 创建附注标签
    git tag -d v1.0.0               # 删除标签
    git push origin v1.0.0          # 推送标签到远程
    git push origin --tags          # 推送所有标签
    git checkout v1.0.0             # 切换到标签
```

## git cherry-pick

- 选择性地应用某个提交到当前分支

> git cherry-pick [commit]
```bash
    git cherry-pick commit-hash     # 应用指定提交
    git cherry-pick -n commit-hash  # 应用但不自动提交
    git cherry-pick commit1 commit2 # 应用多个提交
```

## git revert

- 撤销指定提交，创建新的提交来反转更改

> git revert [commit]
```bash
    git revert HEAD                 # 撤销最后一次提交
    git revert commit-hash          # 撤销指定提交
    git revert -n commit-hash       # 撤销但不自动提交
```

## git reset 详细说明

> git reset [mode] [commit]
```bash
    git reset --soft HEAD~1        # 撤销提交，保留更改在暂存区
    git reset --mixed HEAD~1       # 撤销提交和暂存，保留更改在工作区（默认）
    git reset --hard HEAD~1        # 撤销提交、暂存和工作区更改（危险）
    git reset --hard commit-hash   # 重置到指定提交
```

## 删除远程remote

> git remote -v 

 - 删除名为 origin 的远程仓库：
> git remote remove origin



## git config

- 配置 git 设置

> git config [options]
```bash
    git config --global user.name "Your Name"           # 设置全局用户名
    git config --global user.email "email@example.com"  # 设置全局邮箱
    git config --list                                  # 查看所有配置
    git config user.name                               # 查看用户名
    git config --global core.editor "code --wait"      # 设置默认编辑器
    git config --global alias.st status                # 设置别名
```

## git rm

- 从 git 中删除文件

> git rm [options] [file]
```bash
    git rm file.txt                  # 删除文件并暂存删除操作
    git rm --cached file.txt         # 从暂存区删除，但保留工作区文件
    git rm -r folder/                # 递归删除文件夹
```

## git mv

- 移动或重命名文件

> git mv [old] [new]
```bash
    git mv old-file.txt new-file.txt # 重命名文件
    git mv file.txt folder/          # 移动文件到文件夹
```

## git clean

- 清理未跟踪的文件

> git clean [options]
```bash
    git clean -n                     # 预览将要删除的文件（dry-run）
    git clean -f                     # 删除未跟踪的文件
    git clean -fd                    # 删除未跟踪的文件和目录
    git clean -i                     # 交互式清理
```

## git show

- 显示提交的详细信息

> git show [commit]
```bash
    git show                         # 显示最后一次提交
    git show commit-hash             # 显示指定提交
    git show HEAD~1                  # 显示倒数第二次提交
    git show branch-name             # 显示分支的最新提交
```

## git blame

- 查看文件的每一行是谁修改的

> git blame [file]
```bash
    git blame readme.md              # 查看文件每一行的作者
    git blame -L 10,20 readme.md    # 查看第 10-20 行
```

## git bisect

- 二分查找定位问题提交

> git bisect [command]
```bash
    git bisect start                 # 开始二分查找
    git bisect bad                   # 标记当前提交为有问题
    git bisect good commit-hash      # 标记某个提交为正常
    git bisect reset                 # 结束二分查找并重置
```

## git reflog

- 查看引用日志，找回丢失的提交

> git reflog
```bash
    git reflog                       # 查看所有引用日志
    git reflog show branch-name      # 查看特定分支的日志
```

## git submodule

- 子模块管理

> git submodule [command]
```bash
    git submodule status             # 显示子模块状态
    git submodule add url path       # 添加子模块
    git submodule init               # 初始化子模块
    git submodule update             # 更新子模块
    git submodule update --init --recursive # 初始化和更新所有子模块
    git submodule deinit path        # 取消初始化子模块
```

## 常用组合命令

```bash
    # 查看状态并查看差异
    git status && git diff

    # 添加、提交、推送
    git add . && git commit -m "message" && git push

    # 拉取并合并
    git pull origin main

    # 创建分支并推送
    git checkout -b feature && git push -u origin feature

    # 查看最近 5 次提交的统计信息
    git log --oneline --graph -5 --stat
```

### 问题

## ？ 添加子module
> git submodule stats # 显示submodules 
> git submodule add -b master https://github.com/jerryc127/hexo-theme-butterfly.git themes/butterfly # 添加子模块


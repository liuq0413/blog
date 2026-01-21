---
title: Ubuntu命令
date: 2025-12-15 14:41:10
tags: 
categories: Ubuntu
---
# Ubuntu 命令

## VNC 命令

### 1. 启动 VNC 服务器

    vncserver :3 \
      -geometry 1920x1080 \
      -depth 24 \
      -SecurityTypes VncAuth \
      -localhost no

- `:1` 指定显示端口号（5901）
- `-geometry` 设置分辨率
- `-depth` 设置颜色深度
- `-SecurityTypes VncAuth` 设置认证方式
- `-localhost no` 允许远程连接

**简化启动命令**

    vncserver :1

**启动多个会话**

    vncserver :1
    vncserver :2

### 2. 查看 VNC 会话

    vncserver -list

显示所有正在运行的 VNC 会话

### 3. 停止 VNC 服务器

    vncserver -kill :1

停止指定端口的 VNC 会话

**停止所有 VNC 会话**

    vncserver -kill :*
    # 或者
    pkill -9 vnc

### 4. 修改 VNC 密码

    vncpasswd

按提示输入新密码

### 5. 查看 VNC 进程

    ps aux | grep vnc

查看所有 VNC 相关进程

### 6. 重启 VNC 服务器

    vncserver -kill :1
    vncserver :1

先停止再启动

### 7. 配置 VNC 启动参数

**编辑配置文件**

    ~/.vnc/xstartup

**示例配置（使用 GNOME 桌面）**

    #!/bin/bash
    unset SESSION_MANAGER
    unset DBUS_SESSION_BUS_ADDRESS
    exec /etc/X11/xinit/xinitrc
    [ -x /etc/vnc/xstartup ] && exec /etc/vnc/xstartup
    [ -r $HOME/.Xresources ] && xrdb $HOME/.Xresources
    x-window-manager &

**配置后需要添加执行权限**

    chmod +x ~/.vnc/xstartup

### 8. 客户端连接 VNC

**使用 VNC Viewer 连接**

    服务器IP:5901

- 端口号 = 5900 + 显示号（如 :1 对应 5901）

**使用 SSH 隧道连接（推荐）**

    ssh -L 5901:localhost:5901 user@server_ip

然后本地连接 `localhost:5901`

### 9. 安装 VNC 服务器

**Ubuntu/Debian**

    sudo apt update
    sudo apt install tigervnc-standalone-server tigervnc-common

**设置初始密码**

    vncpasswd

### 10. 查看 VNC 日志

    ~/.vnc/*:1.log

查看指定会话的日志文件

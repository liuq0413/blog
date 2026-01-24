---
title: vscode
date: 2025-12-16 01:00:55
tags:
categories: vscode
---

这篇整理一些 **VS Code 常用快捷键速查**（默认键位）。我按使用场景分组，并同时给出 **macOS** 与 **Windows/Linux** 的对应按键。

> 说明：不同键盘布局/插件可能会改键；以 VS Code 菜单显示为准。你也可以在“键盘快捷方式”里搜索命令并自定义。

## 通用（打开/命令/面板）

- **命令面板**
  - macOS：`⇧ Shift + ⌘ Command + P`（或 `F1`）
  - Win/Linux：`Ctrl + Shift + P`（或 `F1`）
- **设置（Settings）**
  - macOS：`⌘ Command + ,`
  - Win/Linux：`Ctrl + ,`

## 编辑（最常用）

- **格式化文档**
  - macOS：`⇧ Shift + ⌥ Option + F`
  - Win/Linux：`Shift + Alt + F`
- **向上/向下复制当前行**
  - macOS：`⇧ Shift + ⌥ Option + ↓/↑`
  - Win/Linux：`Shift + Alt + ↓/↑`
- **向上/向下移动当前行**
  - macOS：`⌥ Option + ↓/↑`
  - Win/Linux：`Alt + ↓/↑`
- **删除当前行**
  - macOS：`⇧ Shift + ⌘ Command + K`
  - Win/Linux：`Ctrl + Shift + K`
- **整行缩进 / 反缩进**
  - macOS：`⌘ Command + ]` / `⌘ Command + [`
  - Win/Linux：`Ctrl + ]` / `Ctrl + [`
- **自动换行（Toggle Word Wrap）**
  - macOS：`⌥ Option + Z`
  - Win/Linux：`Alt + Z`

## 多光标 / 选区

- **在下一个匹配处添加光标（选中下一个相同单词）**
  - macOS：`⌘ Command + D`
  - Win/Linux：`Ctrl + D`
- **跳过当前匹配，选择下一个**
  - macOS：`⌘ Command + K` 然后 `⌘ Command + D`
  - Win/Linux：`Ctrl + K` 然后 `Ctrl + D`
- **选中所有匹配（一次性多光标）**
  - macOS：`⇧ Shift + ⌘ Command + L`
  - Win/Linux：`Ctrl + Shift + L`
- **在上/下一行插入光标**
  - macOS：`⌥ Option + ⌘ Command + ↑/↓`
  - Win/Linux：`Ctrl + Alt + ↑/↓`
- **列选择（矩形选择）**
  - macOS：按住 `⇧ Shift + ⌥ Option` 再用鼠标拖拽 / 方向键
  - Win/Linux：按住 `Shift + Alt` 再用鼠标拖拽 / 方向键


## 代码跳转 / 智能提示（对编程很关键）

- **转到定义（Go to Definition）**
  - macOS：`F12`（或按住 `⌘` 点击）
  - Win/Linux：`F12`（或按住 `Ctrl` 点击）
- **查看定义（Peek Definition）**
  - macOS：`⌥ Option + F12`
  - Win/Linux：`Alt + F12`
- **转到引用（References）**
  - macOS：`⇧ Shift + F12`
  - Win/Linux：`Shift + F12`
- **重命名符号（Rename Symbol）**
  - macOS：`F2`
  - Win/Linux：`F2`
- **快速修复 / Code Action**
  - macOS：`⌘ Command + .`
  - Win/Linux：`Ctrl + .`

## 终端 / 面板

- **新建集成终端**
  - macOS：``Ctrl + ` ``
  - Win/Linux：``Ctrl + ` ``
- **显示/隐藏终端（切到终端面板）**
  - macOS：``Ctrl + ` ``
  - Win/Linux：``Ctrl + ` ``

## 调试（Debug）

- **开始/继续**
  - macOS：`F5`
  - Win/Linux：`F5`
- **停止**
  - macOS：`⇧ Shift + F5`
  - Win/Linux：`Shift + F5`
- **单步跳过 / 单步进入 / 单步跳出**
  - macOS：`F10` / `F11` / `⇧ Shift + F11`
  - Win/Linux：`F10` / `F11` / `Shift + F11`
- **切换断点**
  - macOS：`F9`
  - Win/Linux：`F9`

## 窗口 / 编辑器管理

- **拆分编辑器**
  - macOS：`⌘ Command + \`
  - Win/Linux：`Ctrl + \`
- **在编辑器组之间切换**
  - macOS：`⌘ Command + 1/2/3`
  - Win/Linux：`Ctrl + 1/2/3`
- **切换到下一个/上一个编辑器标签**
  - macOS：`⌃ Control + Tab` / `⌃ Control + ⇧ Shift + Tab`
  - Win/Linux：`Ctrl + Tab` / `Ctrl + Shift + Tab`

- **Remote-SSH：为不同主机指定默认系统（Windows / Linux）**  
  远程连接（Remote - SSH）时，如果你希望某台机器默认按 Windows 或 Linux 处理，可在 `settings.json` 配置：

```json
{
  "remote.SSH.remotePlatform": {
    "my-win-host": "windows",
    "my-linux-host": "linux"
  }
}
```

  - `my-win-host` / `my-linux-host`：一般对应你 `~/.ssh/config` 里的 `Host` 名（或 Remote-SSH 列表里显示的连接条目名）
  - 可选值：`windows` / `linux` / `macos`


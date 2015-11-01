# Linux使用笔记

## 右键在当前位置打开终端
1. 安装nautilus-open-terminal
```
sudo apt-get install nautilus-open-terminal
```

2. 重新加载文件管理器
```
nautilus -q
```
或者注销再登录

## 终端颜色配置
针对用户的配置，应该将配置信息写入~/.bashrc文件。由于默认配置**没有使用不同颜色突出不同的内容**，并且**路径名字太长时命令需要在新的一行中显示**。

### 颜色配置
1. 需要对~/.bashrc中的PS1变量进行定制。
```
gedit ~/.bashrc
```
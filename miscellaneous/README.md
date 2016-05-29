# 恢复到初始状态

### 概述

Sublime Text可以通过删除data文件夹的方式恢复到初始状态。不同操作系统这个文件夹的位置也不同：

- OS X：`~/Library/Application Support/Sublime Text 3`
- Windows：`%APPDATA%\Sublime Text 3`
- Linux：`~/.config/sublime-text-3`

恢复到初始状态，你需要：

1. 退出Sublime Text
2. 删除上面列出的data文件夹
3. 重启Sublime Text

重启时，一个新的data文件夹会被创建，就像是第一次启动Sublime Text一样。需要注意的是这也会删掉你所有的设置和包。

### OS X Lion

在Lion中，`~/Library`文件夹默认是隐藏的。要导航到那个地方，需要从菜单栏的` Go/Go to Folder`操作，输入`~/Library`。

### Windows

Windows中，缓存文件是存放在独立的位置的，`%LOCALAPPDATA%\Sublime Text 3`，这是为了提高性能。


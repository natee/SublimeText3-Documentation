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



# OS X命令行

### 概述

Sublime Text包含了一个命令行工具，*subl*，以在命令行操作文件。在Sublime Text中这可以被用来打开文件或项目，也可以像unix工具一样作为一个*EDITOR*使用，如作为*git*和*subversion*。

## 起步

第一步是给*subl*添加一个链接。假设你已经把Sublime Text放到了`Applications`文件夹下，并且你的路径下有`~/bin`目录，你可以运行：

```
ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl

```

## 使用

执行`subl —help`，

```shell
Usage: subl [arguments] [files]         edit the given files
   or: subl [arguments] [directories]   open the given directories
   or: subl [arguments] -               edit stdin

Arguments:
  --project <project>: Load the given project
  --command <command>: Run the given command
  -n or --new-window:  Open a new window
  -a or --add:         Add folders to the current window
  -w or --wait:        Wait for the files to be closed before returning
  -b or --background:  Don't activate the application
  -s or --stay:        Keep the application activated after closing the file
  -h or --help:        Show help (this message) and exit
  -v or --version:     Show version and exit

--wait is implied if reading from stdin. Use --stay to not switch back
to the terminal when a file is closed (only relevant if waiting for a file).

Filenames may be given a :line or :line:column suffix to open at a specific
location.
```

## EDITOR

要把Sublime Text作为许多命令的editor来给输入增加提示，设置EDITOR的环境变量：

```
export EDITOR='subl -w'

```

指定`-w`表示只有文件关闭时`subl`命令才会退出。




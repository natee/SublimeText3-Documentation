## 列选择

### 概述

列选择可以选择文件中的一个矩形区域。

### 使用鼠标

**OS X**

- 鼠标左键 + Option

- 或：鼠标中键


- 添加到选择：Command
- 从选择中减去：Command+Shift

**Windows**

- 右键 + Shift
- 或：鼠标中键


- 添加到选择：Ctrl
- 从选择中减去：Alt

**Linux**

- 右键 + Shift

- 添加到选择：Ctrl
- 从选择中减去： Alt



### 使用键盘

**OS X**

- Ctrl + Shift + Up
- Ctrl + Shift + Down

**Windows**

- Ctrl + Alt + Up
- Ctrl + Alt + Down

**Linux**

- Ctrl + Alt + Up
- Ctrl + Alt + Down



## 使用键盘进行多选

#### 添加一行

使用Ctl+Alt+Up 和 Ctrl+Alt+down（OS X：Ctrl+Shift+Up 和 Ctrl+Shift+Down）在当前选中文本的上方或下方添加一行。

#### 把选择块拆分成行选择

选择一个多行文本，按下Ctrl+Shift+L（OS X： Command+Shift+L ）就可以把这多行文本的选择拆分成多个选择，每个选择是一行。

#### 快速选择下一个

快速选择下一个和当前选择的单词一样的内容，Windows和Linux上按下Ctrl+D（OS X：Command+D）。

Windows和Linux上按下Ctrl+K,Ctrl+D（OS X：Command+K,Command+D）来跳过下一个匹配项。

#### 一次性找到所有

Windows和Linux上按下Alt+F3（OSX：Ctrl+Command+G）直接选中所有匹配项。

#### 单个选择

按下Escape即可从多选状态恢复到单选状态。

## 自动补全

### 概述

自动补全在你输入时显示一个补全列表，因此你可以输入少量字符就可以完成一个很长的单词输入。对于源代码和HTML（必须得输入<）这个功能是默认启用的。

### 禁用自动补全

可以通过`auto_complete`设置来禁用自动补全。把下面一行加入到`Preferences` 中`Settings - User`文件中即可：

```
"auto_complete": false
```

如果自动补全被禁用了，你可以手动显示自动补全的提示，或者直接tab键补全为排在补全列表中第一个的值。

### 手动显示补全

按下`Ctrl + Space`。

### 按下Tab键生效

默认情况，按下Enter键即可是补全生效，但是这会使完成补全和换行产生歧义，设置`auto_complete_commit_on_tab`的值为true，Enter键则只会进行换行操作，tab键才会完成补全操作。

## Tab键补全

### 概述

按下Tab键来执行补全操作。默认是启用的。

### 禁用Tab补全

把下面一行加入到`Preferences/File Settings - User`中：

```
"tab_completion": false
```

### 插入常量Tab符

按下`shift+tab`插入一个常量tab符。

### 改变补全

有时候补全列表的文本并不是需要的，为了增加一个可选项，按下`Ctrl + Space`，这将使补全回退，并展示一个标准的补全列表。

## 无干扰模式

### 概述

无干扰模式将只在显示器中以全屏模式显示你的文件，可以在菜单栏中的`View - 切换无干扰模式`进入无干扰模式，快捷键也可以。

### 定制化

无干扰模式将使某些设置生效，默认设置（位于`Packages/Default/Distraction Free.sublime-settings`）是：

```json
{
	"line_numbers": false,
	"gutter": false,
	"draw_centered": true,
	"wrap_width": 80,
	"word_wrap": true,
	"scroll_past_end": true
}
```

你可以在`Packages/User/Distraction Free.sublime-settings`文件中编辑这些设置，从菜单栏中的`Preferences/File Settings - More`打开这个配置文件。

值得注意的是上面的`word_wrap`这个选项，值为80表示当有80个字符时会换行，你可能会设置成一个更大的值，设置成0将在窗口宽度时换行。

## Vintage模式

### 概述

Vintage是Sublime Text中一个vi模式的包，这允许你在Sublime Text中使用vi命令。

Vintage模式是开源的，在[GitHub](https://github.com/sublimehq/Vintage) 上贡献你的代码吧。

### 启用VI模式

默认是禁用的，在菜单栏`Preferences/Settings - Default`打开配饰文件，从`ignored_packages`字段中移除"Vintage"即可启用vi模式。vi模式默认是以插入模式开始的，这可以在用户设置中进行修改：

```json
"vintage_start_in_command_mode": true
```

### 支持的操作

Vintage包含最基本的操作：d（删除）、y（复制）、c（修改）、gu（小写）、gU（大写）、g~（交换）、g?、<（取消缩进）、>（缩进）。

也包含很多其它的操作。也支持文本对象，包括单词、括号、引号、标签等。

### 不支持的操作

插入模式是Sublime Text编辑状态，支持Sublime Text按键绑定：不支持vi的插入模式额按键绑定。

不实现Ex commands，除了通过命令面板执行的`:w`和`:e`之外。

### Under the Hood

Vintage模式是完全通过按键绑定和插件API实现的，例如，如果你想绑定`jj`为退出插入模式的命令，你可以添加如下按键绑定：

```json
{ "keys": ["j", "j"], "command": "exit_insert_mode",
	"context":
	[
		{ "key": "setting.command_mode", "operand": false },
		{ "key": "setting.is_widget", "operand": false }
	]
}
```

### OS X Lion

在Lion中，长按按键并不会重复输入，而是会打开一个提示菜单来在有差异的字符间进行选择，这在命令模式下工作可能不太好，所以你也许想禁用它，在terminal中输入下面的命令：

```
defaults write com.sublimetext.2 ApplePressAndHoldEnabled -bool false
```

### Ctrl按键

Vintage支持这些ctrl按键绑定：

- Ctrl+[：退出
- Ctrl+R：重做
- Ctrl+Y：向下一行
- Ctrl+E：向上一行
- Ctrl+F：向下翻页
- Ctrl+B：向上翻页

然而，由于回合Sublime Text中其他按键绑定冲突，Windows和Linux中这些命令默认都被禁用了，启用方式为修改：

```
"vintage_ctrl_keys": true
```

### Ex模式

在 [VintageEx](https://github.com/SublimeText/VintageEx)查看Vintage的Ex模式。

## 项目

### 概述

Sublime Text中的项目有两个文件组成：一个包含项目定义的sublime-project文件和一个包含用户特定数据（如用户打开的文件和编辑的文件）的sublime-workspace文件。

一般来说，sublime-project文件会被纳入版本控制中，sublime-workspace则不会。

### 项目格式

sublime-project文件是JSON，提供了3个顶层的key，`folders`：包含的文件夹，`settings`：覆盖默认的文件设置，`build-system`：项目制定的构建系统。例子：

```json
{
    "folders":
    [
        {
            "path": "src",
            "folder_exclude_patterns": ["backup"],
            "follow_symlinks": true
        },
        {
            "path": "docs",
            "name": "Documentation",
            "file_exclude_patterns": ["*.css"]
        }
    ],
    "settings":
    {
        "tab_size": 8
    },
    "build_systems":
    [
        {
            "name": "List",
            "shell_cmd": "ls -l"
        }
    ]
}
```

**folders**

每个文件夹必须有一个`path`，额外可以有`file_exclude_patterns`，` file_include_patterns,`，`folder_exclude_patterns`， `folder_include_patterns`和`follow_symlinks`。

`path`是相对于项目路径的相对路径，或者是一个绝对路径。

`name`表示在侧边栏显示的名称。

**settings**

覆盖默认设置，但无法覆盖语法设置。

**build_systems**

数组，除了常规的设置外，数组的每一项必须指定一个`name`，这里列出的数组可以通过菜单栏的**Tools/Build Systems**访问。


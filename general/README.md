#Sublime Text非官方文档
##目录
- [关于文档](#通用)
  - [完善文档](#完善文档)
- [安装](#安装)
  - [32位和64位](#32位和64位)
  - [Windows](#windows)
  - [OS X](#os-x)
  - [Linux](#linux)
  - [发布渠道](#发布渠道)
- [基本概念](#基本概念)
  - [概述](#概述)
  - [通用惯例](#通用惯例)
  - [需要花时间来掌握Sublime Text](#需要花时间来掌握sublime-text)
  - [Data目录](#data目录)
  - [Packages目录](#packages目录)
  - [Sublime Text是可编程的](#sublime-text是可编程的)
  - [包、插件、资源和其它项](#包-插件-资源和其它项)
  - [Textmate兼容性](#textmate兼容性)
  - [vi/Vim模式](#vi-Vim模式)
  - [emacs模式](#emacs模式)
- [编辑](#编辑)
  - [概述](#概述)
  - [多文本选择](#多文本选择)
  - [多行选择合并成一行](#多行选择合并成一行)
  - [列选择](#列选择)
  - [选择文本的其它方式](#选择文本的其它方式)
  - [置换](#置换)
  - [更多...](#更多...)
- [搜索和替换](#搜索和替换)- 
  - [单文件搜索](#单文件搜索)
  - [多文件搜索](#多文件搜索)
  - [正则表达式](#正则表达式)
- [构建系统（批量处理）](#构建系统-（批量处理）)
  - [文件格式](#文件格式)
  - [构建系统存放位置](#构建系统存放位置)
  - [运行构建系统](#运行构建系统)
- [文件导航和文件管理](#文件导航和文件管理)
  - [跳转到任何位置](#跳转到任何位置)
  - [侧边栏](#侧边栏)
  - [项目](#项目)
  - [侧边栏和项目的其它设置](#侧边栏和项目的其它设置)
  - [工作空间](#工作空间)
  - [面板](#面板)
- [定制化](#定制化)
  - [设置](#设置)
  - [缩进](#缩进)
  - [按键绑定](#按键绑定)
  - [菜单](#菜单)
  - [色彩主题](#色彩主题)
- [扩展性和自动化](#扩展性和自动化)
  - [命令](#命令)
  - [宏](#宏)
  - [Snippets](#snippets)
  - [补全](#补全)
  - [命令面板](#命令面板)
  - [语法定义](#语法定义)
  - [插件](#插件)
  - [包](#包)
- [命令行](#命令行)
- [参考](#参考)
  - [语法定义](#语法定义)
  - [配色方案](#配色方案)
  - [构建系统](#构建系统)
  - [按键绑定](#按键绑定)
  - [设置](#设置)
  - [符号](#符号)
  - [注释](#注释)
  - [补全文件](#补全文件)
  - [Metadata文件](#metadata文件)
  - [命令面板](#命令面板)
  - [插件](#插件)
  - [Python API](#python-api)
  - [命令](#命令)
  - [Windows键盘快捷键](#windows键盘快捷键)
  - [OSX键盘快捷键](#osx键盘快捷键)
- [词汇表](#词汇表)

##关于文档
欢迎来到Sublime Text编辑器的非官方文档。

Sublime Text是一个可以运行在OS X、Windows和Linux上的多功能编辑器，你可以用它来写代码或是写散文.

如果你刚开始使用Sublime Text，可以先看看[基本概念](#基本概念)这部分内容。

###完善文档
如果你想帮助完善此文档，先去[GitHub](https://github.com/guillermooo/sublime-undocs)上fork仓库，本文档是用[Sphinx](http://sphinx-doc.org/)创建的。

[返回目录](#目录)

##安装
请务必阅读官网的[使用条件](http://www.sublimetext.com/buy)，它是一款收费软件。

不同平台上安装Sublime Text的方法不一样。

###32位和64位
####OS X
Sublime Text在OS X上只有一个版本，所以你可以忽略这部分。

####Windows
如果你的windows系统比较新的话就用64位的版本，运行64位出错的话就试试32位的。

####Linux
执行下面的命令查看的的操作系统类型。

```
uname -m
```

###Windows
####便捷版还是普通版
Sublime Text在Windows上有普通和便捷两个版本。除非你知道你是需要使用便捷版本，否则还是建议你安装普通版本。

**安装普通版本**会把数据存放到两个目录中：安装目录和*数据目录*（用户特定的目录，后面会解释的）。普通版本的Sublime Text也集成了文件管理器。

**安装便捷版本**会把所有文件都存放到一个目录中，即使这个文件夹被移动了位置，编辑器仍然可以正常使用。

####如何安装普通版本的Sublime Text？
1. 下载安装包
2. 双击安装包

####如何安装便捷版本的Sublime Text？
1. 下载压缩文件
2. 解压到一个文件夹
   文件夹中可以看到一个可执行的*sublime_text.exe*文件。


###OS X
1. 下载.dmg文件
2. 打开.dmg文件
3. 把Sublime Text拖动到*应用程序*文件夹中

使用下面的命令创建一个快捷方式。

```
ln -s  "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```

###Linux
下载安装包并且手动解压，或者你也可以使用命令解压。
####Ubuntu
#####i386

```
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime-text_build-3047_i386.deb
```

#####x64

```
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime-text_build-3047_amd64.deb
```

####其它版本Linux
#####i386

```
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime_text_3_build_3047_x32.tar.bz2
tar vxjf sublime_text_3_build_3047_x32.tar.bz2
```

#####x64

```
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime_text_3_build_3047_x64.tar.bz2
tar vxjf sublime_text_3_build_3047_x64.tar.bz2
```

现在我们应该把解压的文件移动到合适的位置。

```
sudo mv Sublime\ Text\ 3 /opt/
```

最后，用下面的命令创建一个快捷方式。

```
sudo ln -s /opt/Sublime\ Text\ 3/sublime_text /usr/bin/sublime
```

在Ubuntu下，如果你想把Sublime Text添加到统一的启动器中，那么你需要继续往下看。
首先，创建一个新文件。

```
sudo sublime /usr/share/applications/sublime.desktop
```
然后，把下面的代码粘贴到里面。

```
[Desktop Entry]
Version=1.0
Name=Sublime Text 3
# Only KDE 4 seems to use GenericName, so we reuse the KDE strings.
# From Ubuntu's language-pack-kde-XX-base packages, version 9.04-20090413.
GenericName=Text Editor

Exec=sublime
Terminal=false
Icon=/opt/Sublime Text 3/Icon/48x48/sublime_text.png
Type=Application
Categories=TextEditor;IDE;Development
X-Ayatana-Desktop-Shortcuts=NewWindow

[NewWindow Shortcut Group]
Name=New Window
Exec=sublime -n
TargetEnvironment=Unity
```

如果你已经注册过Sublime Text，但是每次打开还是提示要你注册，尝试以下命令。

```
sudo chown -R username:username /home/username/.config /sublime-text-3
```
*username*替换为你的账户名，这将修复授权错误的问题。

###发布渠道
写这个文档的时候，Sublime Text已经有了Sublime Text2和Sublime Text3两个版本，通常来说，Sublime Text3是更好的选择。尽管3还是测试版本，但是它和2一样稳定并且有更多的功能。

如果使用3遇到了问题或者你需要的一些插件或包不支持3，那么就去用2。

####获取Sublime Text3
Sublime Text3现在提供了2个发布渠道。

- [测试版](http://www.sublimetext.com/3)(默认的，推荐)
- [开发版](http://www.sublimetext.com/3dev)

比起开发版，**测试**版经过了更好的测试，在日常使用中更加可靠。**大多数用户都应该用测试版。**

*开发版*不太稳定：开发版可能会有bug，并且可能不能正常运行，更新频次也更高。

**开发版本仅供注册用户下载。**

####获取Sublime Text2
[Sublime Text2](http://www.sublimetext.com/2)

[返回目录](#目录)

##基本概念
###概述
为了充分理解本指南的余下内容，你必须非常熟悉本节内容提出的一些概念。

###通用惯例
本指南是以Windows用户的角度写的，大多数指令只需稍作变化就可以在其它平台上运行了。

如果没做其它说明，相对路径（例如，`Packages/User`）从[Data目录](#Data目录)开始。

假设键盘快捷键是默认的，如果你用的不是美式英语键盘，那么一些快捷键可能会不起作用。这是由Sublime Text内部处理按键所决定的。

###需要花时间来掌握Sublime Text
掌握Sublime Text需要时间和实践，幸运的是，它是建立在少数概念之上的，当所有部分聚集到一起形成一个统一的系统时。

本指南将教会你如何使用和配置Sublime Text。

对于程序员来说Sublime Text是一个多功能编辑器，但是你却不一定要以程序员的身份使用它，你也不必进行广泛地配置来使它进行工作。

接下来的章节中，我们将做一些概述，当你花一定的时间使用这款编辑器你就会对对它变得熟悉起来。

###Data目录
*Data目录*几乎存放了用户的所有有趣的配置文件，数据目录是基于平台定位的。

- Windows： `%APPDATA%\Sublime Text 3`
- OS X： `~/Library/Application Support/Sublime Text 3`
- Linux： `~/.config/sublime-text-3`

如果你使用的是**便捷版本**（Windows才有），查看`Sublime Text 3/Data`。

注意`Data`目录仅仅存在于便捷版本中，正常版本的Data目录如上面说的。

###Packages目录
这是位于Data目录下的一个重要目录，所有被支持的编程和标记语言的资源都存放在这里。

你可以从主菜单访问包目录**（Preferences → Browse Packages...）**。

本指南中，我们指的packages folder是*Packages*， *packages path*，*packages folder*或*packages directory*。

####用户包
`Packages/User`包含了用户自定义的插件、片段、宏等等，可以把它理解为包目录下你的私人空间，更新Sublime Text并不会覆盖`Packages/User`。

###Sublime Text是可编程的
这个消息对程序员非常有用，其它用户只需要知道Sublime Text允许用户通过编程来给Sublime Text添加他们自己的功能。

Sublime Text通过一个应用程序编程接口（API）把它的内部暴露出来了，所以用户可以通过Python进行编程。编辑器中包含了一个嵌入式Python解释器，这个解释器对于检查编辑器的设置和开发插件时进行API测试非常有用。

Sublime Text和插件输出信息到*控制台*中，按住`Ctrl+～`或者从主菜单选择**View → Show Console**来打开控制台。

这里是Sublime Text中Python的控制台。

![控制台](./assets/basic-concepts-console.png "控制台")

####系统Python VS Sublime Text 3内嵌Python
Sublime Text 3内嵌Python解释器和你的系统中的Python解释器是独立的。

内嵌Python解释器仅仅可以用来和插件API进行交互，不能用于其它开发。

###包、插件、资源和其它项
Sublime Text中几乎所有的东西都可以被扩展和自定义，你可以编辑编辑器的行为，添加宏或是代码片段，扩展菜单栏及其它更多的操作，你甚至可以通过编辑器的API开发一个全新的功能作为插件。

Sublime Text夸张的灵活性导致你必须学习很多的配置文件。

Sublime Text的配置文件必须是符合特定结构或格式的文本文件：主要是JSON文件，但是你也可以看到XML文件，对于更高级的扩展选项则是用Python文件。

本指南中，为了简便，把所有的配置文件统称为*资源文件*。

Sublime Text会在包目录下找资源文件，

###Textmate兼容性
这部分内容对从Textmate（Mac下的一款编辑器）切换到Sublime Text的用户来说很有用。

除了命令之外，Sublime Text和Textmate有着良好的兼容性。此外，Sublime Text要求所有的语法定义有一个*.tmLanguage*扩展，所有的偏好文件有*.tmPreferences extension*扩展。特别地，*.plist*文件将被忽略，即使它处于*Syntaxes*或*Preferences*子目录下。

###vi/Vim模式
这部分内容对从Vim切换到Sublime Text的用户来说很有用。

vi是一个古老的模态编辑器，允许户只能通过键盘进行所有的操作。Vim是一个现代版的vi，仍然被广泛地使用着。

Sublime Text提供了一个*Vintage*包来模拟vi，*Vintage*包默认是被忽略的，官网了解更多[Vintage](http://www.sublimetext.com/docs/3/vintage.html)的内容。

[Vintageous](http://guillermooo.bitbucket.org/Vintageous)（一个开源项目）是Vintage演化而来的，提供了更好的vi/Vim体验，更新也比Vintage更快。

###emacs模式
这部分内容对从emacs切换到Sublime Text的用户来说很有用。

emacs是程序员的另一款编辑器。

Sublime Text不提供模拟emacs的包，但是你可以用其它用户开发的第三方包。

[返回目录](#目录)

##编辑
###概述
Sublime Text有非常多的编辑功能，这里只能介绍一点皮毛。

###多文本选择
多文本选择让你高效地修改文本，任何的赞美都无法形容它了，原因：

选择一些文本，按下`Ctrl+D`进行**多选**，如果想跳过当前项，按下`Ctrl+K,Ctrl+D`。

误选了按`Ctrl+U`撤销最后一次选中项。

###多行选择合并成一行
`Ctrl+L`选中单行文本，`Ctrl+Shift+L`把多行选择变成单行选择的编辑状态。

###列选择
你可以选择文件中的一个矩形区域，这会用到多文本选择。

####使用鼠标
Windows

| 选择块    | 右击+`⇧`        |
| ------ | ------------- |
| 添加到选择  | `Ctrl`+右击+`⇧` |
| 从选择中移除 | `Alt`+右击+`⇧`  |

Linux

| 选择块    | 右击+`⇧`        |
| ------ | ------------- |
| 添加到选择  | `Ctrl`+右击+`⇧` |
| 从选择中移除 | `Alt`+右击+`⇧`  |

OSX

| 选择块    | 右击+`⌥`         |
| ------ | -------------- |
| 添加到选择  | `⌘`+右击+`⇧`     |
| 从选择中移除 | `⌘`+`⇧`+右击+`⇧` |

####使用键盘
| Windows | Ctrl + Alt + Up/Down |
| ------: | -------------------- |
|   Linux | Alt + `⇧` + Up/Down  |
|    OS X | `⌃` + `⇧` + Up/Down  |

###选择文本的其它方式
所有的选项都可以在**Selection**菜单处找到，列出一部分：

- 选择单词（`Alt + Shift + <arrow>`）
- 选择到括号（`Ctrl + Shift + M`）
- 选择到缩进（`Ctrl + Shift + J`）
- 选择到作用域（`Ctrl + Shift + Space`）

###置换
`Ctrl+T`用来置换选中的两块内容。

###更多...
**Edit、Selection、Find和Goto**菜单里面有很多编辑功能，大多数时候你只会用到其中的一部分，其它部分只会在你有需要的时候才会用到。

[返回目录](#目录)

##搜索和替换
Sublime Text提供两种主要搜索方式：

- 单文件搜索
- 多文件搜索

两种方式都支持正则表达式。

###单文件搜索
####搜索
键盘快捷键与搜索面板对应关系：

| 打开搜索面板 | Ctrl + F      |
| ------ | ------------- |
| 正则表达式  | Alt + R       |
| 大小写匹配  | Alt + C       |
| 精确匹配   | Alt + W       |
| 下一个    | Enter         |
| 上一个    | Shift + Enter |
| 所有     | Alt + Enter   |

####增量搜索
键盘快捷键与增量搜索面板对应关系：

| 打开增量搜索面板 | Ctrl + I      |
| -------- | ------------- |
| 正则表达式    | Alt + R       |
| 大小写匹配    | Alt + C       |
| 精确匹配     | Alt + W       |
| 下一个      | Enter         |
| 上一个      | Shift + Enter |
| 所有       | Alt + Enter   |

增量搜索面板和普通搜索面板的唯一区别就在于`Enter`键的行为不同，增量搜索中，按下`Enter`键后会选中下一个匹配项并直接关闭搜索面板，到底用哪一种搜索形式见仁见智。

####替换文本
键盘快捷键与替换面板对应关系：

| 打开替换面板 | Ctrl + H           |
| ------ | ------------------ |
| 下一个    | Ctrl + Shift + H   |
| 所有     | Ctrl + Alt + Enter |

####小技巧
#####其它搜索方式
[跳转到任何位置](#跳转到任何位置)提供了`#`操作符在当前文件中进行搜索。

#####其它和搜索有关的按键
下面这些按键只有在搜索面板隐藏时才有用

| 向前搜索最近匹配的搜索项 | F3         |
| ------------ | ---------- |
| 向后搜索最近匹配的搜索项 | Shift + F3 |
| 选择所有匹配项      | Alt + F3   |

你还可以基于当前的选择进行搜索

| 搜索当前选中内容 | Ctrl + E         |
| -------- | ---------------- |
| 替换当前选中内容 | Ctrl + Shift + E |

#####多行搜索
你可以在搜索面板输入多行匹配式，`Ctrl+Enter`换行。

![多行搜索](./assets/search-and-replace-multiline.png "多行搜索")

注：搜索面板是可以调整大小的。

###多文件搜索
####搜索
键盘快捷键与搜索文件对应关系：

| 打开搜索面板 | Ctrl + Shift + F |
| ------ | ---------------- |
| 正则表达式  | Alt + R          |
| 大小写匹配  | Alt + C          |
| 精确匹配   | Alt + W          |
| 下一个    | Enter            |

####搜索作用域
**where**限制了搜索的范围，你可以通过下面的一些方法来定义范围：

- 添加单个目录（即使在windows上，也使用Unix风格的路径）
- 使用通配符添加/排除文件
- 点击右侧选择按钮（`<open folders>`，`<open files>`...）

可以用逗号分隔多个过滤条件，例如：

![""](./assets/search-in-files-with-filters.png "")

####结果格式
你可以自定义搜索结果的展示形式，这里有一些可选项：

- 在单独的视图中展示
- 显示上下文

![""](./assets/search-and-replace-search-results.png "")

####导航结果
如果搜索到匹配项，可以用下面的按键来切换搜索结果。

| 下一个  | F4         |
| ---- | ---------- |
| 上一个  | Shift + F4 |


###正则表达式
正则表达式不做介绍了，直接看图：

!["正则表达式"](./assets/search-and-replace-regex-sample.png "正则表达式")

[返回目录](#目录)

##构建系统（批量处理）
> [构建系统的参考](#构建系统)，这里包含了可选参数、变量等的完整参考文档。


> 注意：构建系统目前正处于开发版本重做状态，以下的信息可能过时。
> 到[论坛](http://www.sublimetext.com/forum/viewtopic.php?f=2&t=17471&sid=81fd17a6c886e151a3f69c0eaa87272d)查看更多信息。

构建系统让你可以通过外部程序运行你的文件，如整理、翻译等等。

可执行的构建系统必须处于*PATH*下。

###文件格式
带有`.sublime-build`扩展名的JSON文件。

####示例

```
{
    "cmd": ["python", "-u", "$file"],
    "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
    "selector": "source.python"
}
```

**cmd**

必须，这里包含了真正需要执行的命令：

	python -u /path/to/current/file.ext
​	
**file_regex**

一个Perl风格的正则表达式捕获从外部程序的输出的错误信息。

**selector**

如果设置了** Tools | Build System | Automatic** ，Sublime Text会通过匹配的`selector`自动为当前文件找到编译系统。

除了配置选项，你也可以用一些变量，例如上面用到的`$file`。

###构建系统存放位置
必须存储在Packages文件夹下（例如*Packages/User*），很多的包都包含它们独自的构建系统。

###运行构建系统
按下`F7`键或**Tools | Build**。

[返回目录](#目录)

##文件导航和文件管理
###跳转到任何位置
这个功能可以非常便捷地对你的项目文件进行导航。
![](./assets/file-management-goto-anything.png)

键盘快捷键对应关系：

| 打开功能                | Ctrl + P |
| ------------------- | -------- |
| 选择当前项并关闭Go Anything | Enter    |
| 选择当前项               | →        |
| 关闭Go Anything       | Esc      |

当你在Go Anything输入框中输入文字时，Sublime Text就会在当前项目中进行搜索，最匹配的结果会有一个预览。这个预览只是*短暂*的，除非你对这个预览文件进行了一些操作。其它情况你也会获取一个短暂的预览视图，比如点击了左侧文件。

####运算符
你也可以使用一些操作符，注：这些操作符都可以单独使用，也可以跟在搜索项后面。例：

```
models:100
```

先搜索models，然后跳转到第100行。

#####支持的操作符
**@symbol**

符号跳转：输入@symbol跳转到symbol符号所在的位置

**#term**

关键字跳转：输入#term跳转到term所在的位置

**:line_number**

行号跳转：输入:111，跳转到111行，如果行号太大则跳转到文件最后一行。

键盘快捷键对应关系：

| @    | Ctrl + R |
| ---- | -------- |
| #    | Ctrl + ; |
| :    | Ctrl + G |


###侧边栏
不论项目是展开还是收起状态，侧边栏总是会有一个激活项目，这样就可以进行项目内检索了。

键盘快捷键对应关系：

| 切换侧边栏          | Ctrl + K, Ctrl + B |
| -------------- | ------------------ |
| 聚焦侧边栏          | Ctrl + 0           |
| 导航侧边栏          | 箭头                 |
| 退出聚焦侧边栏，重新聚焦视图 | Esc                |

###项目
项目组会让你的工作更有组织，总是会有一个激活项目存在，如果没有的话，Sublime Text会默认创建一个隐士的项目。

切换项目快捷键`Ctrl + Alt + P`。

项目的metadata存储在一个扩展名为`.sublime-project`的JSON文件中，不管有没有`.sublime-project`文件，你都可以看到`.sublime-workspace`文件（Sublime Text会用到，你无法编辑它）。

有关项目的[官方文档](http://www.sublimetext.com/docs/2/projects.html)。

####`.sublime-project`格式

```
{
    "folders":
    [
        {
            "path": "src",
            "folder_exclude_patterns": ["backup"]
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
            "cmd": ["ls"]
        }
    ]
}
```

**folders**：包含的文件夹。

`path`

必须，相对于项目的相对路径，或是绝对路径。

`name`

可选，如果存在，则会出现在侧边栏。

`folder_exclude_patterns`

可选，通配符组成的列表，匹配到的文件夹会被排除在项目外。

`folder_include_patterns`

可选，通配符组成的列表，匹配到的文件夹会被包含在项目中。

`file_exclude_patterns`

可选，通配符组成的列表，匹配到的文件会被排除在项目外。

`file_include_patterns`

可选，通配符组成的列表，匹配到的文件会被包含在项目中。

**settings**：个性化设置。

只会在当前项目中生效的设置，这个会覆盖用户设置。

除了全局设置外，几乎所有的设置都可以被覆盖。

**build_systems**：构建系统。

在`.sublime-project`中你可以定义项目的构建系统，`name`必须唯一，可以在**Tools → Build Systems**菜单看到设置的构建系统。

###侧边栏和项目的其它设置
**binary_file_patterns**

通配符组成的列表，匹配到的文件会被展示到侧边栏，但是会被排除在Go Aythings之外。

###工作空间
工作空间可以看作是在同一个项目中不同的视图，例如，在做某些功能时你可能只想打开部分文件，或者在写测试时你需要不同的布局，工作空间的存在就是为了解决这个问题。

工作空间的操作和项目非常类似，创建：**Project → New Workspace for Project**，保存：**Project → Save Workspace As**。

切换工作空间`Ctrl + Alt + P`。

工作空间的metadata存储在一个扩展名为`.sublime-workspace`的JSON文件中。

###面板
视图组，可以同时打开多个面板。

键盘快捷键对应关系：

| 打开新面板  | Ctrl+K, Ctrl+↑ |
| ------ | -------------- |
| 关闭当前面板 | Ctrl+K, Ctrl+↓ |

更多面板管理看菜单栏**View → Layout**。

[返回目录](#目录)

##定制化
###设置
Sublime Text把配置文件存放在* .sublime-settings*中。

小经验：总是把个人配置文件放到*Packages/User*下，保证它们会优先于其它任何有冲突的配置文件。

####格式
带有*.sublime-settings*扩展名的JSON文件。

####设置的类型
*.sublime-settings*文件的名字决定了它的目的，名字可以是具有描述性的或是和它们所控制的内容相关的。例如，文件类型设置需要携带*.tmLanguage*定义文件类型的名字。因此，*.py*类型文件的语法定义就必须包含在`Python.tmLanguage`文件中，相应的设置文件被成为`Python.sublime-settings`。

然而，一些设置文件只在特殊的平台上生效，这可以通过文件名来推断。例如，`Preferences (platform).sublime-settings`。平台的有效名称是`Windows`、`Linux`、`OSX`。

这一点**非常重要**：`Packages/User`下面基于平台的设置文件会被忽略，这种情况下，你可以确定一个单独的文件可以覆盖其它设置。

设置的改变是时时的，但是你也许需要重启Sublime Text来加载新的设置文件。

####如何访问和编辑基本设置文件
可以通过菜单栏的**Preferences | Settings - User**和**Preferences | Settings - More**来访问主要的配置文件（除非你需要设置非常细粒度的控制，否则还是不要修改这个）。不鼓励修改**Preferences | Settings - Default **，因为每次更新软件这个文件都会恢复。然而，你可以把它当作一个参考文档：它包含了所有可用的全局和文件类型设置的解释。

####`.sublime-settings`文件优先级顺序
相同的设置文件（例如`Python.sublime-settings`）可以出现在多个地方，在具有相同名称文件中定义的所有设置将根据预定义的规则进行合并和覆盖。到[这里](#包)查看详细。

`Packages/User`下的设置文件最终都会覆盖其它同名文件的设置内容。

除了设置文件之外，Sublime Text维护*会话*数据——为当前正在被编辑的特定文件集进行设置。当你工作在一些文件时，会话数据会被更新，因此如果你以任何形式（主要是通过API调用）调整特殊文件的设置，它将会被记录在会话中，这将优先于任何可适用*.sublime-setting*文件。

要检查一个正在被编辑的特定文件的设置，在控制台输入`view.settings().get("setting_name")`。

最后，值得注意的是一些设置会自动为你进行调整。如果你对一些设置的值有困惑时，请牢记这一点。例如，这是一个有关空白设置和`syntax`设置的例子。

下面，你可以看到在Windows下Sublime Text对Python文件进行处理的一个假想层级设置的顺序。

- Packages/Default/Preferences.sublime-settings
- Packages/Default/Preferences (Windows).sublime-settings
- Packages/User/Preferences.sublime-settings
- Packages/Python/Python.sublime-settings
- Packages/User/Python.sublime-settings
- 当前文件的会话数据
- 自动调整设置

[设置的层次结构](#设置的层次结构)查看完整示例。

####全局编辑器设置和全局文件设置
这些设置被存放在`Preferences.sublime-settings`和`Preferences (platform).sublime-settings`文件中，默认设置在`Packages/Default`下。

平台的有效名称是`Windows`、`Linux`、`OSX`。

####文件类型设置
以语法定义来命名`.sublime-settings`文件，例如，语法定义为`Python.tmLanguage`，设置文件命名为*Python.sublime-settings*。

和全局设置一样，你也可以对文件类型创建指定平台的设置，例如，`Python (Linux).sublime-settings`只会作用于Linux。

此外，我们强调`Pakages/User`下只有`Python.sublime-settings`会被读到。

无论它的位置在哪里，特殊设置都会有一个较高的优先级，高于全局设置。

####设置的层次结构
下面，你可以看到在Windows下Sublime Text对Python文件进行处理的一个假想层级设置的顺序。

- `Packages/Default/Preferences.sublime-settings`
- `Packages/Default/Preferences (Windows).sublime-settings`
- `Packages/AnyOtherPackage/Preferences.sublime-settings`
- `Packages/AnyOtherPackage/Preferences (Windows).sublime-settings`
- `Packages/User/Preferences.sublime-settings`
- 项目中的设置
- `Packages/Python/Python.sublime-settings`
- `Packages/Python/Python (Windows).sublime-settings`
- `Packages/User/Python.sublime-settings`
- 当前文件的会话数据
- 自动调整设置

####存放用户设置
当你想在软件更新时保留你的设置，把对应的*.sublime-settings*文件放到`Packages/User`下。

###缩进
> [官方文档](http://www.sublimetext.com/docs/2/indentation.html)

###按键绑定
####文件格式
`.sublime-keymap`为扩展名的JSON文件中。

例如：
```
[
   { "keys": ["ctrl+shift+n"], "command": "new_window" },
   { "keys": ["ctrl+o"], "command": "prompt_open_file" }
]
```

####定义和重写按键绑定
默认：`Packages/Default/Default (Windows).sublime-keymap)`。如果你想覆盖的话，需要新建一个具有更高优先级的设置文件，例如：`Packages/User/Default (Windows).sublime-keymap`。

####高级按键绑定
简单按键绑定包括映射到一个命令的一个或多个键的序列，然而还有更加复杂的语法，例如给命令传递一些参数，限制特定上下文的按键绑定。

#####传递参数
使用`args`指定参数：

```
{ "keys": ["shift+enter"], "command": "insert", "args": {"characters": "\n"} }
```
这里，当按下`Shift+Enter`时，`insert`命令会加上`\n`参数。

#####上下文
上下文决定了一个给定的按键绑定是否生效。

```
{ "keys": ["escape"], "command": "clear_fields", "context":
   [
      { "key": "has_next_field", "operator": "equal", "operand": true }
   ]
}
```

同样的按键可能会被映射到其它上下文中，所以同样的按键可能产生不一样的结果。

#####Key Chords（同时按两个键）
你可以用多个按键组合创建一个按键绑定。

```
{ "keys": ["ctrl+k", "ctrl+v"], "command": "paste_from_history" }
```

这里，触发`paste_from_history`命令，必须先按下`Ctrl + K`，然后松开`K`，按下`V`。

注：这是一个默认的按键行为，你可以随时尝试。

###菜单
无

###色彩主题
Sublime Text默认的Python高亮配色主题：
![](./assets/color_schemes_main.png '')

> [配色方案](#配色方案)参考。

[返回目录](#目录)

##扩展性和自动化
下面的章节展示了Sublime Text各种各样被扩展的附加功能。

###指令
Sublime Text中指令是无处不在的：按键绑定、菜单项、宏等都可以通过指令来工作。
有些指令是在Sublime Text编辑器的核心实现的，但是他们当中的很多都是作为Python插件，每一个指令都可以由一个通过Python插件来调用。

####指令调度
通常情况，指令是被绑定到应用程序对象、一个窗口对象或是一个视图对象中。但是，窗口对象会根据输入的焦点来调度指令，所以你可以从一个窗口对象发送一个视图指令，它会为你找到正确的视图实例。

####指令解析
指令都是以`_`分隔的名称，如：`hot_key`，它可以跟一个字典参数（key是string类型，value是JSON类型）。下面是几个从Python控制台运行的指令：
```
view.run_command("goto_line", {"line": 10})
view.run_command('insert_snippet', {"contents": "<$SELECTION>"})
view.window().run_command("prompt_select_project")
```
> [指令](#指令)参考。

###宏
宏是包含一个指令队列的自动化工具，可以用它来完成一些重复性工作。

宏文件是以`.sublime-macro`为扩展名的JSON文件，Sublime Text自带了几个提供核心功能的宏命令，如行和词的删除。你可以在**工具 | Macros**或是`Packages/Default`中找到它们。

####如何录制宏
按下`Ctrl+q`，然后依次执行所需的命令。当操作完成时，再次按下`Ctrl+q`结束宏的录制。新创建的宏不会保存成一个文件，只会保留在宏缓冲区中。现在你可以通过按下`Ctrl+Shift+q`来运行这个宏，或者执行**工具 | 保存宏**把它保存到一个文件中。

注意：宏缓冲区只会保留最新记录的宏，宏只会记录发送到缓冲区的命令：窗口级别的指令将会被忽视，如创建文件。

####如何编辑宏
录制宏的另外一个选择就是手动编辑它，在`Packages/User`下创建一个以`.sublime-macro`为扩展名的文件，这个文件中写入操作指令。宏文件格式如下：
```
[
    {"command": "move_to", "args": {"to": "hardeol"}},
    {"command": "insert", "args": {"characters": "\n"}}
]
```
手动编辑宏时，需要对引号、空格和反斜杠前添加`\`进行转义。

####宏存储到位置
宏文件可以被存到任意包文件夹下，可以在**工具 | 宏 | <PackageName>**处看到。

####宏的按键绑定
可以通过组合键的形式运行宏，把宏文件的路径替换下面的`run_macro_file`。
```
{"keys": ["super+alt+l"], "command": "run_macro_file", "args": {"file": "res://Packages/User/Example.sublime-macro"}}
```

###Snippets
我们在编写代码的时候，总会遇到一些需要反复使用的代码片段。这时候就需要反复的复制和黏贴，大大影响效率。用snippet功能可以使自己免于这种繁琐的操作。片段是能为你加入一些文字并使他们适应上下文的只能模板。

####文件格式
以*.sublime-snippet*为后缀的XML文件，例如，你可以把一个`greeting.sublime-snippet`放到一个`Email`的包里。

一个典型的snippet如下所示：
```
<snippet>
    <content><![CDATA[Type your snippet here]]></content>
    <!-- Optional: Tab trigger to activate the snippet -->
    <tabTrigger>xyzzy</tabTrigger>
    <!-- Optional: Scope the tab trigger will be active in -->
    <scope>source.python</scope>
    <!-- Optional: Description to show in the menu -->
    <description>My Fancy Snippet</description>
</snippet>
```
`snippet`元素包含了Sublime Text所需的一切信息从而判断应该插入什么内容、什么时候插入、是否需要插入。我们依次来看看这些组成部分。

**`content`**
真正的片段内容，片段可以是很简单的，也可以是非常复杂的。稍后会有各种示例。
如果你要写自己的代码片段，请牢记下面的内容：
- `$`，你必须通过`\$`的形式。
- 始终用Tab来表示缩进，当代码片段被插入后，如果`translateTabsToSpaces`被设置为`true`，Tab键会被转化成空格符。
- `content`必须包含在`<![CDATA[…]]>`块中，否则代码片段是无法生效的。
- 代码片段的内容不能包含`]]>`，否则会提前结束`<![CDATA[…]]>`，抛出一个XML的错误信息。你可以通过插入一个未定义的变量来避免这类问题，如：`]]$NOT_DEFINED>`。Sublime Text在插入代码段到文件之前会把`$NOT_DEFINED`替换成一个空字符串。

**`tabTrigger`**
定义必须被按下以插入此片断的键的顺序。输入此序列后按下Tab键，代码片段将会立即插入。
Tab键是一个隐士的按键绑定。

**`scope`**
Scope决定代码片段被激活的上下文，参考[作用域](####作用域)获得更多内容。

**`description`**
当在Snippets菜单显示snippet时会用到，如果不存在，Sublime Text将会默认线回收代码段的文件名。

有了这些信息后，你就可以参照下节的描述写自己的代码段了。

####Snippet特征
#####环境变量
代码片段可以访问环境形式的上下文信息，下面列出的变量的值由Sublime Text自动设置。

你可以添加自己的变量来增加额外的信息，这些额外的变量是在`.sublime-options`文件中定义的。

| **$PARAM1 .. $PARAMn** | 传递给`insert_snippet`命令的参数                 |
| ---------------------- | ---------------------------------------- |
| **$SELECTION**         | 代码段被触发时所选中的文本                            |
| **$TM_CURRENT_LINE**   | 代码段被触发时鼠标所在行                             |
| **$TM_CURRENT_WORD**   | 代码段被触发时鼠标所在位置的单词                         |
| **$TM_FILENAME**       | 被编辑的文件的名称，包括扩展名                          |
| **$TM_FILEPATH**       | 被编辑的文件的路径                                |
| **$TM_FULLNAME**       | 用户的用户名                                   |
| **$TM_LINE_INDEX**     | 代码段被插入的列，从0开始                            |
| **$TM_LINE_NUMBER**    | 代码段被插入的行，从1开始                            |
| **$TM_SELECTED_TEXT**  | **$SELECTION**的别名                        |
| **$TM_SOFT_TABS**      | `translate_tabs_to_spaces`值为true时是true，否则为false |
| **$TM_TAB_SIZE**       | 每个Tab表示的空格数（由`tab_size`选项控制）             |

看一个简单的例子：

```

=================================
​USER NAME:          $TM_FULLNAME
​FILE NAME:          $TM_FILENAME
​TAB SIZE:          $TM_TAB_SIZE
SOFT TABS:          $TM_SOFT_TABS
=================================

# Output:
=============================
USER NAME:          guillermo
FILE NAME:          test.txt
 TAB SIZE:          4
SOFT TABS:          YES
=============================
```


#####字段
在字段标记的帮助下，你可以通过按Tab键在代码段中的位置进行跳转。字段被插入后，将会引导你完成一个代码段的定制。

```
First Name: $1
Second Name: $2
Address: $3
```

上面的例子中，当你按一次`Tab`键光标将会调到`$1`处，再次按`Tab`键时会跳到`$2`处，依次类推。你可以按下`Shift+Tab`回到上一个位置，如果你按下了最多的`Tab`，光标将会被定位到代码段的最后面，从而恢复到正常的编辑状态。

如果你想控制什么时候退出，使用`$0`标记，默认情况这是代码段的结尾。

按下`Esc`键随时终止字段周期。

#####镜像字段

相同的字段标识互为镜像：当你编辑第一个时，其余的将会被实时填充为相同的值。

```
First Name: $1
Second Name: $2
Address: $3
User name: $1
```

示例中，“User name”将会被填充为和“First Name”相同的值。

#####Placeholder

对字段的语法扩展一点点就可以给字段添加默认值了。

```
First Name: ${1:Guillermo}
Second Name: ${2:López}
Address: ${3:Main Street 1234}
User name: $1
```

变量也可以被用来当做占位：

```
First Name: ${1:Guillermo}
Second Name: ${2:López}
Address: ${3:Main Street 1234}
User name: ${4:$TM_FULLNAME}
```

也可以使用嵌套的占位：

```
Test: {1:Nested {2:Placeholder}}
```

#####置换

除了占位语法外，制表符也可以通过置换指定更复杂的操作。

置换的语法如下：

- `${var_name/regex/format_string/}`

- `${var_name/regex/format_string/options}`

**var_name**

**regex**

  Perl风格的正则表达式：[Boost library documentation for regular expressions](http://www.boost.org/doc/libs/1_56_0/libs/regex/doc/html/boost_regex/syntax/perl_syntax.html).

**format_string**

  [Boost library documentation for format strings](http://www.boost.org/doc/libs/1_56_0/libs/regex/doc/html/boost_regex/format/boost_format_syntax.html).

**options**

**可选的，可以是下列的任意一种**

- **i**

  不区分大小写。

- **g**

  全局替换。

- **m**

  允许多行匹配。

例如，可以毫不费力的给文字添加下划线：

```
      Original: ${1:Hey, Joe!}
Transformation: ${1/./=/g}

# Output:

      Original: Hey, Joe!
Transformation: =========
```

下面这个更复杂点的例子把下划线连接的词转化成首字母大写以空格分隔的词，基本上，它是结合了两个独立的表达式并且替换成一个。这也说明在Tab切换停止前替换就会发生。

```
Transformation: ${1/^(\w)|(?:_(\w))/(?1\u$1:)(?2 \u$2:)/g}
      Original: ${1:text_in_snail_case}

# Output:

Transformation: Text In Snail Case
      Original: text_in_snail_case
```

###补全
本着IDE的精神，Sublime Text通过捕获你所写的任何内容对汇总代码或内容进行提示，比如变量。

然而有多种方式扩展补全列表（例如，根据当前的语法）。

本文主题是如何使用补全？补全从何处来？
####如何使用补全
有两种方法使用补全功能，两种方式优先级一样，但是所产生的结果是不同的。

补全内容可以用下列两种方式插入：

-  通过补全列表（`Ctrl + Spacebar`），或
-  按下 `Tab`键

#####补全列表

使用补全列表的方法：

1. 按下`Ctrl + Spacebar`，或者随便输入点内容。
2. 你也可以再次按下`Ctrl + Spacebar`或使用上下箭头来选择下一个条目。
3. 按下`Enter`或`Tab`来验证选择（依赖于`auto_complete_commit_on_tab`的设置）。
4. 可选，重复按下`Tab`键以插入下一个可用的补全。

#####提示

此外，在补全列表的右侧可以看到一个提示，这是补全后的一个预览。

![提示](./assets/completions_hint.png "提示")

实际上上图中的结果将会展开成`$arrayName = array('' => , );`的代码段。

#####触发条件和内容

来源于非当前文件中文字的补全将会提供一个不同于他们将要插入的内容的触发器，这通常用于函数的补全。

例如：PHP中`array_map`的补全将会得到`array_map(callback, arr1)`的结果：

![补全内容](./assets/completions_contents.gif "补全内容")

图中可以看到鼠标自动选择了`callback`，这是因为补全提供了和代码段的字段和placeholder类似的功能。更多细节，请看[Snippet特征](####Snippet特征);

##### 多行补全

Sublime Text提供了同时进行多个补全的功能，但是每个光标当前位置及其前面的最后一个单词分隔符中的文本必须一致。

正确示例（`|`代表光标）：

```
l|
some text with l|
l| and.l|
```

错误示例：

```
l|
some text with la|
l| andl|
```

选择的内容实际上都是被忽视的，仅仅和光标所在位置有关。因此，`e|[-some selection] example`（`|`表示光标，`[...]`表示所选文本）的补全结果是`example|[-some selection] example`。

##### `Tab`-完成补全

如果你想使用Tab键补全功能，必须把`tab_completion`设置为`true`（默认值），Snippet补全不受此设置影响：它们始终依据自己的tab触发器来完成补全。

当`tab_completion`补全可用时，都是自动完成补全的。也就是说，和补全列表不一样，Sublime Text始终会帮你做一个决定。选择最佳补全规则如上所述，在有歧义的情况下，Sublime Text将会使用它认为最合适的条目。你可以多次按下`Tab`键在其余选项中来回切换。

##### 插入一个Tab占位符

当`tab_completion`功能开启时，如果想要插入一个Tab占位符，可以按下`Shift + Tab`。

####补全及其优先级的相关资源

这些都是用户可控的补全来源，按优先级排序：

1. [Snippets](###Snippets)
2. 通过[`on_query_completions()`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime_plugin.EventListener.on_query_completions)的API-注入式补全
3. [*补全文件*](http://docs.sublimetext.info/en/latest/reference/completions.html)
4. 在缓冲区的词

###指令面板
####概述
*命令面板*是一个以执行命令为目的的可交互式的列表。

![命令面板](./assets/command-palette-0001.png "命令面板")

默认情况下，命令面板包含了许多有用的命令，并且提供了非常方便的个人设置和设置文件。

如何使用命令面板：

1. 按下`Ctrl+Shift+P`
2. 选择一个命令面板
3. 按下`Enter`

命令面板通过上下文过滤条目，这就是说无论何时打开文件，你不会永远都看到定义在`.sublime-commands`中的所有命令。

#### 示例文件`.sublime-commands`

这是从`Packages/Default/Default.sublime-commands`中的一段摘录：

```
[
    { "caption": "Project: Save As", "command": "save_project_as" },
    { "caption": "Project: Close", "command": "close_project" },
    { "caption": "Project: Add Folder", "command": "prompt_add_folder" },

    { "caption": "Preferences: Default File Settings", "command": "open_file", "args": {"file": "${packages}/Default/Base File.sublime-settings"} },
    { "caption": "Preferences: User File Settings", "command": "open_file", "args": {"file": "${packages}/User/Base File.sublime-settings"} },
    { "caption": "Preferences: Default Global Settings", "command": "open_file", "args": {"file": "${packages}/Default/Global.sublime-settings"} },
    { "caption": "Preferences: User Global Settings", "command": "open_file", "args": {"file": "${packages}/User/Global.sublime-settings"} },
    { "caption": "Preferences: Browse Packages", "command": "open_dir", "args": {"dir": "$packages"} }
]
```



###语法定义
####先决条件
####文件格式
####作用域
####语法定义是如何工作的
####着手语法定义
####分析模式

###插件
####先决条件
####插件存储位置
####着手插件
####分析你的插件
####指令的类型
####学习API

###包
####概述
####包的位置（和缩写）
####包的内容
####包的类型
####管理包
####定制化或改写包
####合并与优先顺序
####还原到Sublime Text默认配置
[返回目录](#目录)

##命令行
[返回目录](#目录)

##参考
###语法定义
###配色方案
###构建系统
###按键绑定
###设置
###符号
###注释
###补全文件
###Metadata文件
###命令面板
###插件
###Python API
###指令
###Windows键盘快捷键
###OSX键盘快捷键
[返回目录](#目录)

##词汇表
[返回目录](#目录)
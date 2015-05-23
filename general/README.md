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

| 选择块  | 右击+`⇧`   |
|---|---|
| 添加到选择     | `Ctrl`+右击+`⇧` |
| 从选择中移除   | `Alt`+右击+`⇧`  |

Linux

| 选择块  | 右击+`⇧`   |
|---|---|
| 添加到选择     | `Ctrl`+右击+`⇧` |
| 从选择中移除   | `Alt`+右击+`⇧`  |

OSX

| 选择块  | 右击+`⌥`   |
|---|---|
| 添加到选择     | `⌘`+右击+`⇧` |
| 从选择中移除   | `⌘`+`⇧`+右击+`⇧`  |

####使用键盘
| Windows | Ctrl + Alt + Up/Down |
|--------:|----------------------|
| Linux   | Alt + `⇧` + Up/Down  |
| OS X    | `⌃` + `⇧` + Up/Down  |

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
|--------------|---------------|
| 正则表达式   | Alt + R       |
| 大小写匹配   | Alt + C       |
| 精确匹配     | Alt + W       |
| 下一个       | Enter         |
| 上一个       | Shift + Enter |
| 所有         | Alt + Enter   |

####增量搜索
键盘快捷键与增量搜索面板对应关系：

| 打开增量搜索面板 | Ctrl + I      |
|--------------|---------------|
| 正则表达式   | Alt + R       |
| 大小写匹配   | Alt + C       |
| 精确匹配     | Alt + W       |
| 下一个       | Enter         |
| 上一个       | Shift + Enter |
| 所有         | Alt + Enter   |

增量搜索面板和普通搜索面板的唯一区别就在于`Enter`键的行为不同，增量搜索中，按下`Enter`键后会选中下一个匹配项并直接关闭搜索面板，到底用哪一种搜索形式见仁见智。

####替换文本
键盘快捷键与替换面板对应关系：

| 打开替换面板 | Ctrl + H      |
|--------------|---------------|
| 下一个     | Ctrl + Shift + H   |
| 所有       | Ctrl + Alt + Enter |

####小技巧
#####其它搜索方式
[跳转到任何位置](#跳转到任何位置)提供了`#`操作符在当前文件中进行搜索。

#####其它和搜索有关的按键
下面这些按键只有在搜索面板隐藏时才有用

| 向前搜索最近匹配的搜索项 | F3    |
|--------------|---------------|
| 向后搜索最近匹配的搜索项 | Shift + F3 |
| 选择所有匹配项 | Alt + F3 |

你还可以基于当前的选择进行搜索

| 搜索当前选中内容 | Ctrl + E |
|--------------|---------------|
| 替换当前选中内容 | Ctrl + Shift + E |

#####多行搜索
你可以在搜索面板输入多行匹配式，`Ctrl+Enter`换行。

![多行搜索](./assets/search-and-replace-multiline.png "多行搜索")

注：搜索面板是可以调整大小的。

###多文件搜索
####搜索
键盘快捷键与搜索文件对应关系：

| 打开搜索面板 | Ctrl + Shift + F |
|--------------|---------------|
| 正则表达式   | Alt + R       |
| 大小写匹配   | Alt + C       |
| 精确匹配     | Alt + W       |
| 下一个       | Enter         |

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

| 下一个 | F4 |
|--------------|---------------|
| 上一个 | Shift + F4  |


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
###侧边栏
###项目
###侧边栏和项目的其它设置
###工作空间
###面板
[返回目录](#目录)

##定制化
###设置
###缩进
###按键绑定
###菜单
###色彩主题
[返回目录](#目录)

##扩展性和自动化
###命令
###宏
###Snippets
###补全
###命令面板
###语法定义
###插件
###包
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
###命令
###Windows键盘快捷键
###OSX键盘快捷键
[返回目录](#目录)

##词汇表
[返回目录](#目录)

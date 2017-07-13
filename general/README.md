# Sublime Text非官方文档
## 目录
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
  - [Windows/Linux键盘快捷键](#windows/linux键盘快捷键)
  - [OSX键盘快捷键](#osx键盘快捷键)
- [词汇表](#词汇表)

## 关于文档
欢迎来到Sublime Text编辑器的非官方文档。

Sublime Text是一个可以运行在OS X、Windows和Linux上的多功能编辑器，你可以用它来写代码或是写散文.

如果你刚开始使用Sublime Text，可以先看看[基本概念](#基本概念)这部分内容。

### 完善文档
如果你想帮助完善此文档，先去[GitHub](https://github.com/guillermooo/sublime-undocs)上fork仓库，本文档是用[Sphinx](http://sphinx-doc.org/)创建的。

[返回目录](#目录)

## 安装
请务必阅读官网的[使用条件](http://www.sublimetext.com/buy)，它是一款收费软件。

不同平台上安装Sublime Text的方法不一样。

### 32位和64位
#### OS X
Sublime Text在OS X上只有一个版本，所以你可以忽略这部分。

#### Windows
如果你的windows系统比较新的话就用64位的版本，运行64位出错的话就试试32位的。

#### Linux
执行下面的命令查看的的操作系统类型。

```shell
uname -m
```
### Windows
#### 便捷版还是普通版
Sublime Text在Windows上有普通和便捷两个版本。除非你知道你是需要使用便捷版本，否则还是建议你安装普通版本。

**安装普通版本**会把数据存放到两个目录中：安装目录和*数据目录*（用户特定的目录，后面会解释的）。普通版本的Sublime Text也集成了文件管理器。

**安装便捷版本**会把所有文件都存放到一个目录中，即使这个文件夹被移动了位置，编辑器仍然可以正常使用。

#### 如何安装普通版本的Sublime Text？
1. 下载安装包
2. 双击安装包

#### 如何安装便捷版本的Sublime Text？
1. 下载压缩文件
2. 解压到一个文件夹
   文件夹中可以看到一个可执行的*sublime_text.exe*文件。


### OS X
1. 下载.dmg文件
2. 打开.dmg文件
3. 把Sublime Text拖动到*应用程序*文件夹中

使用下面的命令创建一个快捷方式。

```shell
ln -s  "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl
```
### Linux
下载安装包并且手动解压，或者你也可以使用命令解压。
#### Ubuntu
##### i386

```shell
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime-text_build-3047_i386.deb
```
##### x64

```shell
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime-text_build-3047_amd64.deb
```
#### 其它版本Linux
##### i386

```shell
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime_text_3_build_3047_x32.tar.bz2
tar vxjf sublime_text_3_build_3047_x32.tar.bz2
```
##### x64

```shell
cd ~
wget http://c758482.r82.cf2.rackcdn.com/sublime_text_3_build_3047_x64.tar.bz2
tar vxjf sublime_text_3_build_3047_x64.tar.bz2
```
现在我们应该把解压的文件移动到合适的位置。

```shell
sudo mv Sublime\ Text\ 3 /opt/
```
最后，用下面的命令创建一个快捷方式。

```shell
sudo ln -s /opt/Sublime\ Text\ 3/sublime_text /usr/bin/sublime
```
在Ubuntu下，如果你想把Sublime Text添加到统一的启动器中，那么你需要继续往下看。
首先，创建一个新文件。

```shell
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

```shell
sudo chown -R username:username /home/username/.config /sublime-text-3
```
*username*替换为你的账户名，这将修复授权错误的问题。

### 发布渠道
写这个文档的时候，Sublime Text已经有了Sublime Text2和Sublime Text3两个版本，通常来说，Sublime Text3是更好的选择。尽管3还是测试版本，但是它和2一样稳定并且有更多的功能。

如果使用3遇到了问题或者你需要的一些插件或包不支持3，那么就去用2。

#### 获取Sublime Text3
Sublime Text3现在提供了2个发布渠道。

- [测试版](http://www.sublimetext.com/3)(默认的，推荐)
- [开发版](http://www.sublimetext.com/3dev)

比起开发版，**测试**版经过了更好的测试，在日常使用中更加可靠。**大多数用户都应该用测试版。**

*开发版*不太稳定：开发版可能会有bug，并且可能不能正常运行，更新频次也更高。

**开发版本仅供注册用户下载。**

#### 获取Sublime Text2
[Sublime Text2](http://www.sublimetext.com/2)

[返回目录](#目录)

## 基本概念
### 概述
为了充分理解本指南的余下内容，你必须非常熟悉本节内容提出的一些概念。

### 通用惯例
本指南是以Windows用户的角度写的，大多数指令只需稍作变化就可以在其它平台上运行了。

如果没做其它说明，相对路径（例如，`Packages/User`）从[Data目录](#Data目录)开始。

假设键盘快捷键是默认的，如果你用的不是美式英语键盘，那么一些快捷键可能会不起作用。这是由Sublime Text内部处理按键所决定的。

### 需要花时间来掌握Sublime Text
掌握Sublime Text需要时间和实践，幸运的是，它是建立在少数概念之上的，当所有部分聚集到一起形成一个统一的系统时。

本指南将教会你如何使用和配置Sublime Text。

对于程序员来说Sublime Text是一个多功能编辑器，但是你却不一定要以程序员的身份使用它，你也不必进行广泛地配置来使它进行工作。

接下来的章节中，我们将做一些概述，当你花一定的时间使用这款编辑器你就会对对它变得熟悉起来。

### Data目录
*Data目录*几乎存放了用户的所有有趣的配置文件，数据目录是基于平台定位的。

- Windows： `%APPDATA%\Sublime Text 3`
- OS X： `~/Library/Application Support/Sublime Text 3`
- Linux： `~/.config/sublime-text-3`
  如果你使用的是**便捷版本**（Windows才有），查看`Sublime Text 3/Data`。

注意`Data`目录仅仅存在于便捷版本中，正常版本的Data目录如上面说的。

### Packages目录
这是位于Data目录下的一个重要目录，所有被支持的编程和标记语言的资源都存放在这里。

你可以从主菜单访问包目录**（Preferences → Browse Packages...）**。

本指南中，我们指的packages folder是*Packages*， *packages path*，*packages folder*或*packages directory*。

#### 用户包
`Packages/User`包含了用户自定义的插件、片段、宏等等，可以把它理解为包目录下你的私人空间，更新Sublime Text并不会覆盖`Packages/User`。

### Sublime Text是可编程的
这个消息对程序员非常有用，其它用户只需要知道Sublime Text允许用户通过编程来给Sublime Text添加他们自己的功能。

Sublime Text通过一个应用程序编程接口（API）把它的内部暴露出来了，所以用户可以通过Python进行编程。编辑器中包含了一个嵌入式Python解释器，这个解释器对于检查编辑器的设置和开发插件时进行API测试非常有用。

Sublime Text和插件输出信息到*控制台*中，按住`Ctrl+～`或者从主菜单选择**View → Show Console**来打开控制台。

这里是Sublime Text中Python的控制台。

![控制台](./assets/basic-concepts-console.png "控制台")

#### 系统Python VS Sublime Text 3内嵌Python
Sublime Text 3内嵌Python解释器和你的系统中的Python解释器是独立的。

内嵌Python解释器仅仅可以用来和插件API进行交互，不能用于其它开发。

### 包、插件、资源和其它项
Sublime Text中几乎所有的东西都可以被扩展和自定义，你可以编辑编辑器的行为，添加宏或是代码片段，扩展菜单栏及其它更多的操作，你甚至可以通过编辑器的API开发一个全新的功能作为插件。

Sublime Text夸张的灵活性导致你必须学习很多的配置文件。

Sublime Text的配置文件必须是符合特定结构或格式的文本文件：主要是JSON文件，但是你也可以看到XML文件，对于更高级的扩展选项则是用Python文件。

本指南中，为了简便，把所有的配置文件统称为*资源文件*。

Sublime Text会在包目录下找资源文件，

### Textmate兼容性
这部分内容对从Textmate（Mac下的一款编辑器）切换到Sublime Text的用户来说很有用。

除了命令之外，Sublime Text和Textmate有着良好的兼容性。此外，Sublime Text要求所有的语法定义有一个*.tmLanguage*扩展，所有的偏好文件有*.tmPreferences extension*扩展。特别地，*.plist*文件将被忽略，即使它处于*Syntaxes*或*Preferences*子目录下。

### vi/Vim模式
这部分内容对从Vim切换到Sublime Text的用户来说很有用。

vi是一个古老的模态编辑器，允许户只能通过键盘进行所有的操作。Vim是一个现代版的vi，仍然被广泛地使用着。

Sublime Text提供了一个*Vintage*包来模拟vi，*Vintage*包默认是被忽略的，官网了解更多[Vintage](http://www.sublimetext.com/docs/3/vintage.html)的内容。

[Vintageous](http://guillermooo.bitbucket.org/Vintageous)（一个开源项目）是Vintage演化而来的，提供了更好的vi/Vim体验，更新也比Vintage更快。

### emacs模式
这部分内容对从emacs切换到Sublime Text的用户来说很有用。

emacs是程序员的另一款编辑器。

Sublime Text不提供模拟emacs的包，但是你可以用其它用户开发的第三方包。

[返回目录](#目录)

## 编辑
### 概述
Sublime Text有非常多的编辑功能，这里只能介绍一点皮毛。

### 多文本选择
多文本选择让你高效地修改文本，任何的赞美都无法形容它了，原因：

选择一些文本，按下`Ctrl+D`进行**多选**，如果想跳过当前项，按下`Ctrl+K,Ctrl+D`。

误选了按`Ctrl+U`撤销最后一次选中项。

### 多行选择合并成一行
`Ctrl+L`选中单行文本，`Ctrl+Shift+L`把多行选择变成单行选择的编辑状态。

### 列选择
你可以选择文件中的一个矩形区域，这会用到多文本选择。

#### 使用鼠标
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

#### 使用键盘
| Windows | Ctrl + Alt + Up/Down |
| ------: | -------------------- |
|   Linux | Alt + `⇧` + Up/Down  |
|    OS X | `⌃` + `⇧` + Up/Down  |

### 选择文本的其它方式
所有的选项都可以在**Selection**菜单处找到，列出一部分：

- 选择单词（`Alt + Shift + <arrow>`）
- 选择到括号（`Ctrl + Shift + M`）
- 选择到缩进（`Ctrl + Shift + J`）
- 选择到作用域（`Ctrl + Shift + Space`）

### 置换
`Ctrl+T`用来置换选中的两块内容。

### 更多...
**Edit、Selection、Find和Goto**菜单里面有很多编辑功能，大多数时候你只会用到其中的一部分，其它部分只会在你有需要的时候才会用到。

[返回目录](#目录)

## 搜索和替换
Sublime Text提供两种主要搜索方式：

- 单文件搜索
- 多文件搜索

两种方式都支持正则表达式。

### 单文件搜索
#### 搜索
键盘快捷键与搜索面板对应关系：

| 打开搜索面板 | Ctrl + F      |
| ------ | ------------- |
| 正则表达式  | Alt + R       |
| 大小写匹配  | Alt + C       |
| 精确匹配   | Alt + W       |
| 下一个    | Enter         |
| 上一个    | Shift + Enter |
| 所有     | Alt + Enter   |

#### 增量搜索
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

#### 替换文本
键盘快捷键与替换面板对应关系：

| 打开替换面板 | Ctrl + H           |
| ------ | ------------------ |
| 下一个    | Ctrl + Shift + H   |
| 所有     | Ctrl + Alt + Enter |

#### 小技巧
##### 其它搜索方式
[跳转到任何位置](#跳转到任何位置)提供了`#`操作符在当前文件中进行搜索。

##### 其它和搜索有关的按键
下面这些按键只有在搜索面板隐藏时才有用

| 向前搜索最近匹配的搜索项 | F3         |
| ------------ | ---------- |
| 向后搜索最近匹配的搜索项 | Shift + F3 |
| 选择所有匹配项      | Alt + F3   |

你还可以基于当前的选择进行搜索

| 搜索当前选中内容 | Ctrl + E         |
| -------- | ---------------- |
| 替换当前选中内容 | Ctrl + Shift + E |

##### 多行搜索
你可以在搜索面板输入多行匹配式，`Ctrl+Enter`换行。

![多行搜索](./assets/search-and-replace-multiline.png "多行搜索")

注：搜索面板是可以调整大小的。

### 多文件搜索
#### 搜索
键盘快捷键与搜索文件对应关系：

| 打开搜索面板 | Ctrl + Shift + F |
| ------ | ---------------- |
| 正则表达式  | Alt + R          |
| 大小写匹配  | Alt + C          |
| 精确匹配   | Alt + W          |
| 下一个    | Enter            |

#### 搜索作用域
**where**限制了搜索的范围，你可以通过下面的一些方法来定义范围：

- 添加单个目录（即使在windows上，也使用Unix风格的路径）
- 使用通配符添加/排除文件
- 点击右侧选择按钮（`<open folders>`，`<open files>`...）

可以用逗号分隔多个过滤条件，例如：

![""](./assets/search-in-files-with-filters.png "")

#### 结果格式
你可以自定义搜索结果的展示形式，这里有一些可选项：

- 在单独的视图中展示
- 显示上下文

![""](./assets/search-and-replace-search-results.png "")

#### 导航结果
如果搜索到匹配项，可以用下面的按键来切换搜索结果。

| 下一个  | F4         |
| ---- | ---------- |
| 上一个  | Shift + F4 |


### 正则表达式
正则表达式不做介绍了，直接看图：

!["正则表达式"](./assets/search-and-replace-regex-sample.png "正则表达式")

[返回目录](#目录)

## 构建系统（批量处理）
> [构建系统的参考](#构建系统)，这里包含了可选参数、变量等的完整参考文档。



> 注意：构建系统目前正处于开发版本重做状态，以下的信息可能过时。
> 到[论坛](http://www.sublimetext.com/forum/viewtopic.php?f=2&t=17471&sid=81fd17a6c886e151a3f69c0eaa87272d)查看更多信息。

构建系统让你可以通过外部程序运行你的文件，如整理、翻译等等。

可执行的构建系统必须处于*PATH*下。

### 文件格式
带有`.sublime-build`扩展名的JSON文件。

#### 示例

```json
{
    "cmd": ["python", "-u", "$file"],
    "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
    "selector": "source.python"
}
```
**cmd**

必须，这里包含了真正需要执行的命令：

```shell
python -u /path/to/current/file.ext
```
​	
**file_regex**

一个Perl风格的正则表达式捕获从外部程序的输出的错误信息。

**selector**

如果设置了**Tools | Build System | Automatic** ，Sublime Text会通过匹配的`selector`自动为当前文件找到编译系统。

除了配置选项，你也可以用一些变量，例如上面用到的`$file`。

### 构建系统存放位置
必须存储在Packages文件夹下（例如*Packages/User*），很多的包都包含它们独自的构建系统。

### 运行构建系统
按下`F7`键或**Tools | Build**。

[返回目录](#目录)

## 文件导航和文件管理
### 跳转到任何位置
这个功能可以非常便捷地对你的项目文件进行导航。
![](./assets/file-management-goto-anything.png)

键盘快捷键对应关系：

| 打开功能                | Ctrl + P |
| ------------------- | -------- |
| 选择当前项并关闭Go Anything | Enter    |
| 选择当前项               | →        |
| 关闭Go Anything       | Esc      |

当你在Go Anything输入框中输入文字时，Sublime Text就会在当前项目中进行搜索，最匹配的结果会有一个预览。这个预览只是*短暂*的，除非你对这个预览文件进行了一些操作。其它情况你也会获取一个短暂的预览视图，比如点击了左侧文件。

#### 运算符
你也可以使用一些操作符，注：这些操作符都可以单独使用，也可以跟在搜索项后面。例：

```
models:100
```
先搜索models，然后跳转到第100行。

##### 支持的操作符
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


### 侧边栏
不论项目是展开还是收起状态，侧边栏总是会有一个激活项目，这样就可以进行项目内检索了。

键盘快捷键对应关系：

| 切换侧边栏          | Ctrl + K, Ctrl + B |
| -------------- | ------------------ |
| 聚焦侧边栏          | Ctrl + 0           |
| 导航侧边栏          | 箭头                 |
| 退出聚焦侧边栏，重新聚焦视图 | Esc                |

### 项目
项目组会让你的工作更有组织，总是会有一个激活项目存在，如果没有的话，Sublime Text会默认创建一个隐式的项目。

切换项目快捷键`Ctrl + Alt + P`。

项目的metadata存储在一个扩展名为`.sublime-project`的JSON文件中，不管有没有`.sublime-project`文件，你都可以看到`.sublime-workspace`文件（Sublime Text会用到，你无法编辑它）。

有关项目的[官方文档](http://www.sublimetext.com/docs/2/projects.html)。

#### `.sublime-project`格式

```json
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

### 侧边栏和项目的其它设置
**binary_file_patterns**

通配符组成的列表，匹配到的文件会被展示到侧边栏，但是会被排除在Go Aythings之外。

### 工作空间
工作空间可以看作是在同一个项目中不同的视图，例如，在做某些功能时你可能只想打开部分文件，或者在写测试时你需要不同的布局，工作空间的存在就是为了解决这个问题。

工作空间的操作和项目非常类似，创建：**Project → New Workspace for Project**，保存：**Project → Save Workspace As**。

切换工作空间`Ctrl + Alt + P`。

工作空间的metadata存储在一个扩展名为`.sublime-workspace`的JSON文件中。

### 面板
视图组，可以同时打开多个面板。

键盘快捷键对应关系：

| 打开新面板  | Ctrl+K, Ctrl+↑ |
| ------ | -------------- |
| 关闭当前面板 | Ctrl+K, Ctrl+↓ |

更多面板管理看菜单栏**View → Layout**。

[返回目录](#目录)

## 定制化
### 设置
Sublime Text把配置文件存放在* .sublime-settings*中。

小经验：总是把个人配置文件放到*Packages/User*下，保证它们会优先于其它任何有冲突的配置文件。

#### 格式
带有*.sublime-settings*扩展名的JSON文件。

#### 设置的类型
*.sublime-settings*文件的名字决定了它的目的，名字可以是具有描述性的或是和它们所控制的内容相关的。例如，文件类型设置需要携带*.tmLanguage*定义文件类型的名字。因此，*.py*类型文件的语法定义就必须包含在`Python.tmLanguage`文件中，相应的设置文件被成为`Python.sublime-settings`。

然而，一些设置文件只在特殊的平台上生效，这可以通过文件名来推断。例如，`Preferences (platform).sublime-settings`。平台的有效名称是`Windows`、`Linux`、`OSX`。

这一点**非常重要**：`Packages/User`下面基于平台的设置文件会被忽略，这种情况下，你可以确定一个单独的文件可以覆盖其它设置。

设置的改变是时时的，但是你也许需要重启Sublime Text来加载新的设置文件。

#### 如何访问和编辑基本设置文件
可以通过菜单栏的**Preferences | Settings - User**和**Preferences | Settings - More**来访问主要的配置文件（除非你需要设置非常细粒度的控制，否则还是不要修改这个）。不鼓励修改**Preferences | Settings - Default **，因为每次更新软件这个文件都会恢复。然而，你可以把它当作一个参考文档：它包含了所有可用的全局和文件类型设置的解释。

#### `.sublime-settings`文件优先级顺序
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

#### 全局编辑器设置和全局文件设置
这些设置被存放在`Preferences.sublime-settings`和`Preferences (platform).sublime-settings`文件中，默认设置在`Packages/Default`下。

平台的有效名称是`Windows`、`Linux`、`OSX`。

#### 文件类型设置
以语法定义来命名`.sublime-settings`文件，例如，语法定义为`Python.tmLanguage`，设置文件命名为*Python.sublime-settings*。

和全局设置一样，你也可以对文件类型创建指定平台的设置，例如，`Python (Linux).sublime-settings`只会作用于Linux。

此外，我们强调`Pakages/User`下只有`Python.sublime-settings`会被读到。

无论它的位置在哪里，特殊设置都会有一个较高的优先级，高于全局设置。

#### 设置的层次结构
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

#### 存放用户设置
当你想在软件更新时保留你的设置，把对应的*.sublime-settings*文件放到`Packages/User`下。

### 缩进
> [官方文档](http://www.sublimetext.com/docs/2/indentation.html)

### 按键绑定
#### 文件格式
`.sublime-keymap`为扩展名的JSON文件中。

例如：
```
[
   { "keys": ["ctrl+shift+n"], "command": "new_window" },
   { "keys": ["ctrl+o"], "command": "prompt_open_file" }
]
```
#### 定义和重写按键绑定
默认：`Packages/Default/Default (Windows).sublime-keymap)`。如果你想覆盖的话，需要新建一个具有更高优先级的设置文件，例如：`Packages/User/Default (Windows).sublime-keymap`。

#### 高级按键绑定
简单按键绑定包括映射到一个命令的一个或多个键的序列，然而还有更加复杂的语法，例如给命令传递一些参数，限制特定上下文的按键绑定。

##### 传递参数
使用`args`指定参数：

```json
{ "keys": ["shift+enter"], "command": "insert", "args": {"characters": "\n"} }
```
这里，当按下`Shift+Enter`时，`insert`命令会加上`\n`参数。

##### 上下文
上下文决定了一个给定的按键绑定是否生效。

```json
{ "keys": ["escape"], "command": "clear_fields", "context":
   [
      { "key": "has_next_field", "operator": "equal", "operand": true }
   ]
}
```
同样的按键可能会被映射到其它上下文中，所以同样的按键可能产生不一样的结果。

##### Key Chords（同时按两个键）
你可以用多个按键组合创建一个按键绑定。

```json
{ "keys": ["ctrl+k", "ctrl+v"], "command": "paste_from_history" }
```
这里，触发`paste_from_history`命令，必须先按下`Ctrl + K`，然后松开`K`，按下`V`。

注：这是一个默认的按键行为，你可以随时尝试。

### 菜单
#### 文件格式

| **Format**    | JSON （带注释）                               |
| ------------- | ---------------------------------------- |
| **Extension** | `.sublime-menu`                          |
| **Name**      | 可用菜单项的列表，查看[Available Menus](http://docs.sublimetext.info/en/latest/customization/menus.html#menu-types) |
| **Location**  | *`Packages`*下的任意位置                       |
| **Content**   | [“Menu Item” 对象](http://docs.sublimetext.info/en/latest/reference/menus.html#menu-item-objects)的列表 |

**例子**

下面的内容是 `Main.sublime-menu` 文件中的一个摘要：

```son
[
    {
        "caption": "Edit",
        "mnemonic": "E",
        "id": "edit",
        "children":
        [
            { "command": "undo", "mnemonic": "U" },
            { "command": "redo_or_repeat", "mnemonic": "R" },
            {
                "caption": "Undo Selection",
                "children":
                [
                    { "command": "soft_undo" },
                    { "command": "soft_redo" }
                ]
            },
            { "caption": "-", "id": "clipboard" },
            { "command": "copy", "mnemonic": "C" },
            { "command": "cut", "mnemonic": "t" },
            { "command": "paste", "mnemonic": "P" },
            { "command": "paste_and_indent", "mnemonic": "I" },
            { "command": "paste_from_history", "caption": "Paste from History" }
        ]
    }
]
```
**图片**

![](./assets/context_menu_default.png '')编辑区域的默认的右键菜单

![](./assets/context_menu_modified.png '')编辑区域的编辑后的右键菜单

#### 可用菜单

| 文件/菜单名                   | 描述                                    |
| ------------------------ | ------------------------------------- |
| **Main**                 | 主菜单                                   |
| **Context**              | 编辑区域的右键菜单                             |
| **Find in Files**        | 点击*在文件中查找*面板中的“…”按钮（查找范围）时出现。         |
| **Side Bar**             | 侧边栏每个节点的右键菜单                          |
| **Side Bar Mount Point** | 侧边栏最外层文件夹额额外右键菜单项                     |
| **Tab Context**          | 标签栏的右键菜单                              |
| **Widget Context**       | 各组件输入框的右键菜单，包括命令面板，跳转到，查找面板和各插件打开的面板。 |

此外，当你点击状态栏中下面四项时会显示各自的列表：

- **Encoding**
- **Line Endings**
- **Indentation**
- **Syntax**

![](./assets/statusbar_menu.gif '')
*状态栏菜单的演示*

#### 菜单项

选中一个菜单项时，会执行一个命令或者打开一个子菜单列表。

可用属性：

- 指令名
- 命令的参数
- 一个ID
- 一个标题
- 快捷键
- 子菜单

一个可正常工作的菜单至少包含：

- 指令名
- 标题和子菜单
- 只有标题
- 一个ID

解析一个菜单将遵循以下规则：

1. 包含子菜单的菜单无法调用指令，如果使用了分隔符标题，则它将被渲染成连字符。
2. 如果没有提供标题，则会从指令的描述信息中抽取出一个标题，如果及没有标题也没有指令，则标题为空字符串。
3. 快捷键必须包含在caption中，且是大小写敏感的。
4. 引用了不存在的指令的菜单将被禁用。
5. 菜单项可以通过其引用的指令进行隐藏或禁用。

**分隔符**

分隔符是菜单项标题有 `-` 且无子菜单的，通常用于给有相同目的的菜单项进行分组。分隔符不能调用指令。

多个分隔符会缩减成一个，菜单的开头和结尾的分隔符不显示。

#### 菜单合并

`.sublime-menu` 文件的加载顺序和包加载的顺序一样，具有相同名称的菜单文件将被拼接起来，除非指定了特定的ID。

同一个包中的菜单文件将从根目录开始按字典的顺序加载，子菜单也是类似。

作为一种特殊情况，*User Packages*中声明的无ID的菜单项总是在其他包中的标准项之后才插入。

**菜单项ID**

ID决定了该部分的名称，如果菜单项的ID匹配到了则将会出现在该部分的第一个，其他项将会在追加到其后面，直到下一个菜单项ID被匹配到。

如果不同 `.sublime-menu` 文件中的两个菜单项通过ID引用了同样的菜单项，Sublime Text 将用新的参数覆盖之前的参数。

把ID分配给分隔符或有子菜单的项是一种常见的做法，这样可以很方便的对菜单栏进行定制。

#### 子菜单

每个菜单项都可以有一个子菜单，鼠标悬停在菜单项就可以看到子菜单，子菜单是有其自己的ID层次的独立菜单。

为了从一个不同的菜单文件扩展子菜单，两个地方必须都指定ID以定位正确的菜单项。

#### 主菜单

和其它菜单不一样，主菜单的根菜单表示菜单栏上的菜单项。

#### 命令的接口

一个菜单项可以动态地被：

- 隐藏
- 禁用
- 调用
- 安排一个不同的标题

为此，指令必须实现这些必须的方法，每个实现了的方法，都将通过相应的菜单项中指定的参数来调用。如果调用失败，该方法将马上被再次通过无参数的形式调用。

- `is_visible`
- `is_enabled`
- `is_checked`
- `description`

其中的一些方法也会对命令面板有一定的影响。

### 色彩主题
Sublime Text默认的Python高亮配色主题：
![](./assets/color_schemes_main.png '')

> [配色方案](#配色方案)参考。

[返回目录](#目录)

## 扩展性和自动化
下面的章节展示了Sublime Text各种各样被扩展的附加功能。

### 指令
Sublime Text中指令是无处不在的：按键绑定、菜单项、宏等都可以通过指令来工作。
有些指令是在Sublime Text编辑器的核心实现的，但是他们当中的很多都是作为Python插件，每一个指令都可以由一个通过Python插件来调用。

#### 指令调度
通常情况，指令是被绑定到应用程序对象、一个窗口对象或是一个视图对象中。但是，窗口对象会根据输入的焦点来调度指令，所以你可以从一个窗口对象发送一个视图指令，它会为你找到正确的视图实例。

#### 指令解析
指令都是以`_`分隔的名称，如：`hot_key`，它可以跟一个字典参数（key是string类型，value是JSON类型）。下面是几个从Python控制台运行的指令：
```shell
view.run_command("goto_line", {"line": 10})
view.run_command('insert_snippet', {"contents": "<$SELECTION>"})
view.window().run_command("prompt_select_project")
```
> [指令](#指令)参考。

### 宏
宏是包含一个指令队列的自动化工具，可以用它来完成一些重复性工作。

宏文件是以`.sublime-macro`为扩展名的JSON文件，Sublime Text自带了几个提供核心功能的宏命令，如行和词的删除。你可以在**工具 | Macros**或是`Packages/Default`中找到它们。

#### 如何录制宏
按下`Ctrl+q`，然后依次执行所需的命令。当操作完成时，再次按下`Ctrl+q`结束宏的录制。新创建的宏不会保存成一个文件，只会保留在宏缓冲区中。现在你可以通过按下`Ctrl+Shift+q`来运行这个宏，或者执行**工具 | 保存宏**把它保存到一个文件中。

注意：宏缓冲区只会保留最新记录的宏，宏只会记录发送到缓冲区的命令：窗口级别的指令将会被忽视，如创建文件。

#### 如何编辑宏
录制宏的另外一个选择就是手动编辑它，在`Packages/User`下创建一个以`.sublime-macro`为扩展名的文件，这个文件中写入操作指令。宏文件格式如下：
```json
[
    {"command": "move_to", "args": {"to": "hardeol"}},
    {"command": "insert", "args": {"characters": "\n"}}
]
```
手动编辑宏时，需要对引号、空格和反斜杠前添加`\`进行转义。

#### 宏存储到位置
宏文件可以被存到任意包文件夹下，可以在**工具 | 宏 | <PackageName>**处看到。

#### 宏的按键绑定
可以通过组合键的形式运行宏，把宏文件的路径替换下面的`run_macro_file`。
```json
{"keys": ["super+alt+l"], "command": "run_macro_file", "args": {"file": "res://Packages/User/Example.sublime-macro"}}
```
### Snippets
我们在编写代码的时候，总会遇到一些需要反复使用的代码片段。这时候就需要反复的复制和黏贴，大大影响效率。用snippet功能可以使自己免于这种繁琐的操作。片段是能为你加入一些文字并使他们适应上下文的只能模板。

#### 文件格式
以*.sublime-snippet*为后缀的XML文件，例如，你可以把一个`greeting.sublime-snippet`放到一个`Email`的包里。

一个典型的snippet如下所示：
```xml
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
Tab键是一个隐式的按键绑定。

**`scope`**
Scope决定代码片段被激活的上下文，参考[作用域](####作用域)获得更多内容。

**`description`**
当在Snippets菜单显示snippet时会用到，如果不存在，Sublime Text将会默认显示代码段的文件名。

有了这些信息后，你就可以参照下节的描述写自己的代码段了。

#### Snippet特征
##### 环境变量
代码片段可以访问环境形式的上下文信息，下面列出的变量的值由Sublime Text自动设置。

你可以添加自己的变量来增加额外的信息，这些额外的变量是在`.sublime-options`文件中定义的。

| **PARAM1 .. PARAMn**  | 传递给`insert_snippet`命令的参数                 |
| --------------------- | ---------------------------------------- |
| **$SELECTION**        | 代码段被触发时所选中的文本                            |
| **$TM_CURRENT_LINE**  | 代码段被触发时鼠标所在行                             |
| **$TM_CURRENT_WORD**  | 代码段被触发时鼠标所在位置的单词                         |
| **$TM_FILENAME**      | 被编辑的文件的名称，包括扩展名                          |
| **$TM_FILEPATH**      | 被编辑的文件的路径                                |
| **$TM_FULLNAME**      | 用户的用户名                                   |
| **$TM_LINE_INDEX**    | 代码段被插入的列，从0开始                            |
| **$TM_LINE_NUMBER**   | 代码段被插入的行，从1开始                            |
| **$TM_SELECTED_TEXT** | **$SELECTION**的别名                        |
| **$TM_SOFT_TABS**     | `translate_tabs_to_spaces`值为true时是true，否则为false |
| **$TM_TAB_SIZE**      | 每个Tab表示的空格数（由`tab_size`选项控制）             |

看一个简单的例子：

```
USER NAME:          $TM_FULLNAME
FILE NAME:          $TM_FILENAME
TAB SIZE:          $TM_TAB_SIZE
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

##### 字段（还是翻译成域？）
在字段标记的帮助下，你可以通过按Tab键在代码段中的位置进行跳转。字段被插入后，将会引导你完成一个代码段的定制。

```
First Name: $1
Second Name: $2
Address: $3
```
上面的例子中，当你按一次`Tab`键光标将会调到`$1`处，再次按`Tab`键时会跳到`$2`处，依次类推。你可以按下`Shift+Tab`回到上一个位置，如果你按下了最多的`Tab`，光标将会被定位到代码段的最后面，从而恢复到正常的编辑状态。

如果你想控制什么时候退出，使用`$0`标记，默认情况这是代码段的结尾。

按下`Esc`键随时终止字段周期。

##### 镜像字段

相同的字段标识互为镜像：当你编辑第一个时，其余的将会被实时填充为相同的值。

```
First Name: $1
Second Name: $2
Address: $3
User name: $1
```
示例中，“User name”将会被填充为和“First Name”相同的值。

##### Placeholder

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
##### 置换

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
### 补全
本着IDE的精神，Sublime Text通过捕获你所写的任何内容对汇总代码或内容进行提示，比如变量。

然而有多种方式扩展补全列表（例如，根据当前的语法）。

本文主题是如何使用补全？补全从何处来？
#### 如何使用补全
有两种方法使用补全功能，两种方式优先级一样，但是所产生的结果是不同的。

补全内容可以用下列两种方式插入：

-  通过补全列表（`Ctrl + Spacebar`），或
-  按下 `Tab`键

##### 补全列表

使用补全列表的方法：

1. 按下`Ctrl + Spacebar`，或者随便输入点内容。
2. 你也可以再次按下`Ctrl + Spacebar`或使用上下箭头来选择下一个条目。
3. 按下`Enter`或`Tab`来验证选择（依赖于`auto_complete_commit_on_tab`的设置）。
4. 可选，重复按下`Tab`键以插入下一个可用的补全。

##### 提示

此外，在补全列表的右侧可以看到一个提示，这是补全后的一个预览。

![提示](./assets/completions_hint.png "提示")

实际上上图中的结果将会展开成`$arrayName = array('' => , );`的代码段。

##### 触发条件和内容

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

#### 补全及其优先级的相关资源

这些都是用户可控的补全来源，按优先级排序：

1. [Snippets](###Snippets)
2. 通过[`on_query_completions()`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime_plugin.EventListener.on_query_completions)的API-注入式补全
3. [*补全文件*](http://docs.sublimetext.info/en/latest/reference/completions.html)
4. 在缓冲区的词

### 指令面板
#### 概述
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

```json
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
### 语法定义
语法定义使得Sublime Text可以感知变成语言和标记语言。最明显的是它可以通过颜色来进行语法高亮。
#### 先决条件
学习本章节，你必须安装Sublime Text的一个包[PackageDev](https://github.com/SublimeText/PackageDev)，这个包可以方便的进行新语法定义的创建。
#### 文件格式
Sublime Text使用[属性列表](http://en.wikipedia.org/wiki/Property_list)（Plist）文件来存储语法定义，然而，由于编辑XML文件是一个繁重的工作，我们将使用YAML代替，之后把它转成Plist格式。这就是上面提到的PackageDev包的用武之地。

注意：如果在本节内容的操作发生什么错误的话，很可能是PackageDev或是YAML有问题，不要马上认为是你的操作造成的错误，这也许只是Sublime Text的一个bug。😄

如果你习惯了XML，那么就手动编辑Plist文件，但是请一定注意有关于转义序列和XML标签等等时的不同需求。
#### 作用域
作用域是Sublime Text中的核心概念，本质上讲，它是在缓冲区中有名字的文本区域。

例如，当你触发一个代码片段，Sublime Text会检测绑定到代码段上的作用域并寻找插入符在文件中的位置。如果插入符当前的位置和代码段作用域匹配，则触发，否则无反应。

作用域可嵌套，从而可以支持高粒度作用域。你可以像CSS选择器一样进行深层次的钻取。例如，由于作用域选择器的存在，在Python源码中的单引号字符串中可以有一个按键绑定被激活，其他语言中则不会。

Sublime Text借鉴了TextMeat（Mac下的一款文本编辑器）中有关作用域的想法，TextMate的在线手册中包含很多有关作用域选择器的详细信息，这些内容对Sublime Text用户也是有很大帮助的。对于色彩的运用尤其明显。

作用域和作用域选择器还是略有区别的：作用域是在语法定义中定义的名称，而作用域选择器的作用是在使用类似代码片段和按键绑定时触发作用域。创建一个新的语法定义的时候你关心的是作用域，当你想限制一个代码段到一定的作用域范围时，你考虑的是作用域选择器。
#### 语法定义是如何工作的
语法定义是和作用域名称配对的正则表达式的数组。Sublime Text试图在一个缓冲区的文本中匹配这些模式，并为所有找到的附上相应作用域名称。这些正则表达式和作用域名称的配对被称为规则。

规则是按以下顺序应用：

1. 规则在一行中的第一个位置被匹配上
2. 数组当中第一条规则

每个规则都会占用被匹配的文字的区域，因此下一条规则尝试匹配时就会跳过这些已匹配上的（极少数情况例外）。

单独文件中的语法定义可以被组合，并且也可以将它们递归地应用。

#### 着手语法定义
我们通过一个示例的方式来给 Sublime Text 代码段创建一个语法定义。我们只写真正的代码段内容，不会列出所有的`.sublime-snippet`文件内容。

注意：由于语法定义主要用于语法高亮，我们将使用短语来划分源文件中的作用域。但是请牢记颜色和语法定义还不是一回事儿，作用域除了语法高亮外还有很多用处。

下面是我们想在一个代码片段中设计的元素：

- 变量 （`$PARAM1`, `$USER_NAME`…）
- 简单的field（`$0`, `$1`…）
- 带有placeholder的复杂的field（`${1:Hello}`）
- 嵌套的field`${1:Hello ${2:World}!}`)
- 转移序列（`\\$`, `\\<`…）
- 非法序列（`$`, `<`…）

下面这些对于本例来说太复杂所以我们不想放进去：

- 变量替换（`${1/Hello/Hi/g}`）

##### 创建一个新的语法定义

按以下步骤执行：

- **Tools | Packages | Package Development | New Syntax Definition**
- 把文件保存成`.YAML-tmLanguage`文件放到 `Packages/User` 文件夹下。

现在你可以看到一个如下的文件：

```
# [PackageDev] target_format: plist, ext: tmLanguage
---
name: Syntax Name
scopeName: source.syntax_name
fileTypes: []
uuid: 0da65be4-5aac-4b6f-8071-1aadb970b8d9

patterns:
-
...
```
分别解释key的含义：

- `name`
  Sublime Text将会展示在语法定义下拉列表中的名称，使用一个简短的带有描述性的名称。

- `scopeName`
  本语法定义最顶层的作用域，格式为`source.<lang_name>` 或`text.<lang_name>`。编程语言使用`source`，标记语言或其他使用`text`。

- `fileTypes`
  这是文件拓展名列表（不包含前面的点）。当打开这些扩展名文件时，将会自动激活语法定义。

- `uuid`
  语法定义的唯一识别码，每个新的语法定义都会有其uuid，尽管Sublime Text会忽略它，千万不要编辑uuid的值。

- `patterns`
  你的匹配模式的容器。

对于我们的例子，用下面的信息填充模板：

```
# [PackageDev] target_format: plist, ext: tmLanguage
---
name: Sublime Snippet (Raw)
scopeName: source.ssraw
fileTypes: [ssraw]
uuid: 0da65be4-5aac-4b6f-8071-1aadb970b8d9

patterns:
-
...
```
注意：YAML并不是一个严格的格式，然而不了解它的约定仍然会使你感到头痛。YAML支持单引号和双引号，但是如果你在其中没有创建其他的YAML字面量时就可以忽略引号。如果这些约定对于Plist失败的话，在输出面板查看一下有关出错的信息。稍后我们将解释如何把YAML中的语法定义转成Plist，这也会出现在模板中的第一行注释中。

`---` 和 `...` 是可选的。

#### 分析模式

`patterns`可以包含多种类型的元素，接下来的章节中我们会了解其中的一部分，如果你想了解更多，去查看Textmate的在线手册。

##### 匹配项

匹配项的形式：

```
match: (?i:m)y \s+[Rr]egex
name: string.format
comment: This comment is optional.
```
- `match`
  Sublime Text寻找匹配的正则表达式。

- `name`
  任何`match`被匹配到时的作用域名称。

- `comment`
  可选的注释。

回到例子中，现在是这样的：

```
# [PackageDev] target_format: plist, ext: tmLanguage
---
name: Sublime Snippet (Raw)
scopeName: source.ssraw
fileTypes: [ssraw]
uuid: 0da65be4-5aac-4b6f-8071-1aadb970b8d9

patterns:
-
...
```
确保`patterns`是空的。

现在开始添加代码段的规则，先从简单的正则开始：

```
\$[0-9]+
# or...
\$\d+
```
我们可以建立如下的模式：

```
name: keyword.other.ssraw
match: \$\d+
comment: Tab stops like $1, $2...
```
也可以把它加到语法定义中：

```
# [PackageDev] target_format: plist, ext: tmLanguage
---
name: Sublime Snippet (Raw)
scopeName: source.ssraw
fileTypes: [ssraw]
uuid: 0da65be4-5aac-4b6f-8071-1aadb970b8d9

patterns:
- comment: Tab stops like $1, $2...
  name: keyword.other.ssraw
  match: \$\d+
  ...
```
注意：对于YAML和上述例子中推荐用2个空格作为缩进。

现在，我们准备把文件转化成`.tmLanguage`。处于兼容性考虑，语法定义使用了Textmate的`.tmLanguage`作为扩展名。上面已经解释过，它是Plist XML文件。

请按照下列步骤来执行转换：

- 确保 **Tools | Build System**中的`Automatic`是勾选状态，或者选择`Convert to …`
- 按下`F7`
- 将会在在相同的文件夹中生成一个新的`.tmLanguage` 文件
- Sublime Text将会刷新这些改动

如果你想知道为什么PackageDev知道你将要把文件转化成什么：请看第一行注释。

现在你已经创建了一个语法定义，下一步，创建一个`.ssraw`文件，语法名将会自动切换成“Sublime Snippet (Raw)”，如果你输入`$1`或是其他代码段字段就可以看到代码高亮效果了。

让我们继续创建环境变量的其他规则。

```
comment: Variables like $PARAM1, $TM_SELECTION...
name: keyword.other.ssraw
match: \$[A-Za-z][A-Za-z0-9_]+
```
重复以上步骤来更新`.tmLanguage`文件。

##### Fine Tuning Matches

你可能已经注意到了，`$PARAM1`中的所有文本有着相同的样式。你个人可能更倾向于让$变得明显，这就是`captures`存在的意义，使用`captures`，你就可以单独对它细分出一个匹配模式。

我们用`captures`来修改一下上面的文件内容：

```
comment: Variables like $PARAM1, $TM_SELECTION...
name: keyword.other.ssraw
match: \$([A-Za-z][A-Za-z0-9_]+)
captures:
  '1': {name: constant.numeric.ssraw}
```
capture给你的规则带来了复杂性，但是它又是很简单的。需要注意数字是如何引用从左到右的带括号的分组。当然，捕获组你想写多少写多少。

注意：多亏了PackageDev，在新的一行中输入`1`按下tab键就会自动填充`'1': {name: }`。

注：和正则表达式于置换一样，捕获中的`0`应用于整个匹配。

##### 开始-结束规则

现在，我们已经在使用一个简单的规则了。尽管我们已经见识过如何把规则模式分解成一个个小组件，但有时候你仍然想对那些源码中由明显的开始和结束标记分隔的大部分代码去应用规则。

用引号或其他划定结构的封闭文本字符串可以更好地处理开始-结束规则。

下面是这样的规则的一个框架：

```
name:
begin:
end:
```
下面是一个包含所有可选项的效果：

```
name:
contentName:
begin:
beginCaptures:
  '0': {name: }
  # ...
end:
endCaptures:
  '0': {name: }
  # ...
patterns:
- name:
  match:
# ...
```
有些元素看起来很眼熟，但是它们组合起来就会让人望而生畏。我们来一个个看：

- `name`
  可选。整个匹配的作用域名称。实际上，这会给规则总定义的`beginCaptures`，`endCaptures`和`patterns`创建嵌套作用域。

- `contentName`
  可选，和`name`不同，`contentName`只会给闭合的文本添加一个作用域。

- `begin`
  正则表达式，作用域开始的标识。

- `end`
  正则表达式，作用域结束的标识。

- `beginCaptures`
  可选，`begin`标识的捕获，和简单匹配的捕获类似使用方法。

- `endCaptures`
  可选，`end`标识的捕获。

- `patterns`
  可选，**仅仅**匹配始末的内容的一个匹配模式的数组，不匹配`begin`和`end`本身的文本。

段中定义复杂的领域：

```
name: variable.complex.ssraw
contentName: string.other.ssraw
begin: '(\$)(\{)([0-9]+):'
beginCaptures:
  '1': {name: keyword.other.ssraw}
  '3': {name: constant.numeric.ssraw}
end: \}
patterns:
- include: $self
- name: support.other.ssraw
  match: .
```
这将是本教程中最复杂的模式，`begin`和`end`就不必解释了：他们定义了一个从`${<NUMBER>:` 到`}`之间的区域。`begin`的值必须用引号包起来，否则解析器发现有`:`，又会识别成另外一个key。`beginCaptures`把开始标记分割成更小的作用域。

最有意思的部分显然是`partterns`。

上面已经看到了作用域是可嵌套的，为了解决这个问题，我们需要已递归风格进行作用域的嵌套。这就是它的价值：它对我们的开始-结束规则捕获的所有文字递归地应用整个语法定义。

注意：我们使用`contentName: string.other.ssraw`代替上次的匹配模式，这种方式我们也提到过排序的重要性和已匹配上的将不会再次进行匹配等内容。

##### 最后的完善

最后，来设置转义序列和非法序列的样式，然后就可以收工了。

```
- comment: Sequences like \$, \> and \<
  name: constant.character.escape.ssraw
  match: \\[$<>]

- comment: Unescaped and unmatched magic characters
  name: invalid.illegal.ssraw
  match: '[$<>]'
```
唯一的难点是`[]`是在YAML中括起来的数组，需要放到引号中。除此之外，如果你熟悉正则表达式的话这些规则将会非常简单。

然而，在其他匹配到`$` 字符的规则后面，你必须非常小心地放置第二条规则，否则，由于前面被匹配到了导致后面的表达式都不会被匹配。

此外，即使添加了这两条额外规则，也要注意，上面我们的递归的开始-结束规则也会按预期继续工作。

这是最终的语法定义：

```
# [PackageDev] target_format: plist, ext: tmLanguage
---
name: Sublime Snippet (Raw)
scopeName: source.ssraw
fileTypes: [ssraw]
uuid: 0da65be4-5aac-4b6f-8071-1aadb970b8d9

patterns:
- comment: Tab stops like $1, $2...
  name: keyword.other.ssraw
  match: \$(\d+)
  captures:
    '1': {name: constant.numeric.ssraw}

- comment: Variables like $PARAM1, $TM_SELECTION...
  name: keyword.other.ssraw
  match: \$([A-Za-z][A-Za-z0-9_]+)
  captures:
    '1': {name: constant.numeric.ssraw}

- name: variable.complex.ssraw
  begin: '(\$)(\{)([0-9]+):'
  beginCaptures:
    '1': {name: keyword.other.ssraw}
    '3': {name: constant.numeric.ssraw}
  end: \}
  patterns:
  - include: $self
  - name: support.other.ssraw
    match: .

- comment: Sequences like \$, \> and \<
  name: constant.character.escape.ssraw
  match: \\[$<>]

- comment: Unescaped and unmatched magic characters
  name: invalid.illegal.ssraw
  match: '[$<>]'
...
```
还有更多的使用“repository”进行结构和代码的重用的技术，但上述的解释只是让你着手于语法定义。

注意：由于PackageDev是向后兼容的，所以如果你以前使用JSON语法定义，现在仍然可以做到这一点。

### 插件
本部分适用于有编程能力的用户。

Sublime Text可以通过Python插件进行扩展，插件通过重用现有命令或创建新命令来构建功能。插件是逻辑实体而非物理实体。
#### 先决条件
你必须掌握Python编程才能进行插件的开发。
#### 插件存储位置
Sublime Text只会在下列位置寻找插件：

- `Installed Packages` (只有 *.sublime-package*文件)
- `Packages`
- `Packages/<pkg_name>/`
  因此，任何嵌套在更深层次的包都不会被加载。

不提倡直接把插件放到 `Packages` 下，Sublime Text在加载它们之前会以一个预先定义好的规则对其进行排序，所以如果直接放到 `Packages` 下可能会得到令你困惑的结果。
#### 第一个插件
给Sublime Text写一个“Hello, World!”插件：

1. 在菜单栏中选择 **Tools | New Plugin…**。
2. 保存为 `Packages/User/hello_world.py`.

你已经写了你的第一个插件，
1. 创建一个新的缓冲区（`Ctrl+n`）。
2. 打开Python控制台（`Ctrl+``）。
3. 输入 `view.run_command("example")` 然后按下回车。

新的缓冲区（其实就是未保存的新文件）中将会看到“Hello, World!”。
#### 分析你的插件
上面的插件看起来就是这样的：
```python
import sublime, sublime_plugin

class ExampleCommand(sublime_plugin.TextCommand):
    def run(self, edit):
        self.view.insert(edit, 0, "Hello, World!")
```
Sublime Text提供了 `sublime`和 `sublime_plugin` 模块；它们不是Python的标准库。

前面已经说过，插件创建或是重用*命令*，命令是Sublime Text的重要组成部分，它只是可以被Sublime Text中不同的方式如插件API、菜单文件、宏等等调用的Python类。

Sublime Text命令是从定义在`sublime_plugin`中的 `*Command` 类派生出来的（后面会作介绍）。

例子中余下部分的代码涉及到`TextCommand` 或是API的，在后面的章节再讲。

在接着讲之前，我们来看看如何调用一个新的命令：首先打开Python控制台，然后下发一个命令调用`view.run_command()`。这种调用命令的方式相当的不方便，但是对于开发阶段开始很有用的。现在请记住，你的命令可以像其他命令一样通过快捷键或是其他方式呗调用。

##### 命令名称的约定

你也许已经注意到我们的命令命名为 `ExampleCommand`，但是我们却是通过传递字符串`example`给API进行调用。Sublime Text标准的命令命名方式就是把类名的`Command`后缀剥离，然后把 `PhrasesLikeThis` 这样的用下划线进行连接，就像：`phrases_like_this`。

新的命令也应该遵循这种命名方式。


#### 指令的类型

你可以创建下列类型的命令：

- 窗口命令（`sublime_plugin.WindowCommand`）
- 文本命令（`sublime_plugin.TextCommand`）


根据你的目的选择合适的命令类型。

##### 命令的共同点

所有的命令都需要实现一个`.run()`函数才能正常运行，此外，它们可以接收任意多的关键字参数。

注意：命令的参数必须是有效的JSON值。

##### 窗口命令

窗口命令是在窗口级别进行操作，这并不是说你不能从窗口命令处理视图，而是说你使用窗口命令时无需视图。如，正在开发的 `new_file` 是一个窗口命令，所以你不打开任何视图就可以调用这个命令。

窗口命令实例中有`.window`属性指向创建它们的窗口实例。

窗口命令的 `.run()` 函数不需要任何位置参数。

##### 文本命令

文本命令是在视图级别进行操作，所以调用时必须得有一个视图。

文本命令实例中有`.view`属性指向创建它们的视图实例。

文本命令的`.run()`函数需要一个`edit`实例作为其第一个参数。

##### 文本命令和`edit`对象

`edit`对象把视图的编辑尽心分组以便撤销和宏可以正常工作。

注意：和老版本不同，Sublime Text3不允许对编辑对象进行编程控制。API是负责管理其生命周期的。插件的作者必须确保新的文本命令中的所有的编辑都在`.run()`中。要调用现有命令，你可以使用`view.run_command（<cmd_name>,<args>）`或类似的API调用。

##### 事件的响应

任何从`EventListener`派生的命令都能够对事件作出响应。

##### 另一个插件实例：

让我们创建一个从谷歌的自动填充服务获取数据的插件，然后将其送至Sublime Text补全列表。

```python
import sublime, sublime_plugin

from xml.etree import ElementTree as ET
import urllib

GOOGLE_AC = r"http://google.com/complete/search?output=toolbar&q=%s"

class GoogleAutocomplete(sublime_plugin.EventListener):
    def on_query_completions(self, view, prefix, locations):
        elements = ET.parse(
            urllib.request.urlopen(GOOGLE_AC % prefix)
        ).getroot().findall("./CompleteSuggestion/suggestion")

        sugs = [(x.attrib["data"],) * 2 for x in elements]

        return sugs
```
注意：请确保学习后把这个示例插件删掉，否则它会影响到系统默认的自动补全。

#### 学习API

想创建插件，你需要熟悉Sublime Text的API和命令，在写这个教程时有关这两个的文档还很少，但你可以通过现有代码来学习。

Packages/Default包含很多无文档的命令和API调用的例子。如果你想看它的代码，必须先把其内容提取到一个文件夹中。作为练习，你可以创建一个构建系统来按需做那样的操作，才能够方便的查看项目的示例代码。

### 包
#### 概述
包是资源的容器。
#### 包的位置（和缩写）
有三个位置存储包，每个地方都有不同的作用：

- 包可以是 *`Data/Packages`* 下的**文件夹**（简写成`Packages`）
- 位于 *`Data/Installed Packages`*（简写成*`Installed Packages`*）或其任意子目录下的以 `.sublime-package` 为后缀名的 **zip压缩包** 。
- *`Application/Packages`*（简写成：*`Shipped Packages`*）下有一些默认的 **zip压缩包**，`Application`是Sublime Text可执行文件所在的目录。

注：为了简洁，我们把以上所有的路径统称为Packages，任何文件夹下（不管是不是`.sublime-package`）的包称之为 *`Packages/PackageName`*。因此，包中的文件会被称为 `PackageName/a_file.extension`。

##### `.sublime-package`包

作为 `.sublime-package` 压缩文件应该是只读的，永远不能被手动修改。这是由于它通常是作为一个整体被更新的，任何手动修改的内容都将在更新过程丢失。

如果你想修改它们，查看[定制化或覆盖包](####定制化或覆盖包)。

##### 同名包的相互影响

如果*`Installed Packages`*和*`Shipped Packages`*中存在两个同名包，将会用*`Installed Packages`*中的这个，*自带包*将会被忽略。

*`Packages/PackageName`*中所有的文件都优先于`Installed Packages/PackageName.sublime-package`和`Shipped Packages/PackageName.sublime-package`中的同名文件。

参看[定制化或覆盖包](####定制化或覆盖包)。

#### 包的内容
包中的典型资源有：

- 构建系统（`.sublime-build`）
- 颜色主题（`.tmTheme`）
- key maps (`.sublime-keymap`)
- 宏（`.sublime-macro`）
- 菜单（`.sublime-menu`）
- 元数据（`.tmPreferences`）
- mouse maps (`.sublime-mousemap`)
- 插件（`.py`）
- 设置（`.sublime-settings`）
- 代码段（`.sublime-snippet`）
- 语法定义（`.tmLanguage`）
- 主题`.sublime-theme`）

一些包是用来支持其他包或核心功能的，如，英文字典拼写检查器使用` Installed Packages/Language - English.sublime-package `作为数据存储。
#### 包的类型
本指南中，讨论这个主题时为了方便我们把包进行了分类，但是Sublime Text不适用这些术语，所以你不必了解它。

**默认包**

  Sublime Text自带的包，一些是核心包，其他的则是对Sublime Text进行增强的包。

  例如：Default, Python, Java, C++, Markdown.

  位于 *`Shipped Packages`*下。

**核心包**

  Sublime Text正常工作的必需包。

  完整的清单：Default, Theme - Default, Color Scheme - Default, Text, Language - English。

  这是自带包的一部分，位于位于 *`Shipped Packages`*下。

**用户包**

  用户安装的包，这通常是用户自己或是第三方开发的包。

**已安装的包**

  *用户包*的一个分支，是由包管理者进行维护的 `.sublime-package` 压缩文件。位于*`Installed Packages`*。

  注：由于Sublime Text中这个文件夹的名称有点不合适，所以当我们说到*安装*包时可能会令人感到困惑。

  在本指南中，有时候说*安装*是给Sublime Text添加一个第三方包，有时候是指复制一个`.sublime-package` 文件到`Installed Packages`下。

**覆盖包**

  *用户包*的一种特殊类型。它是对发布成`.sublime-package`文件尽心定制化后的包。位于 *`Packages`*下。
#### 管理包
##### 安装包

注：由于有自动包管理器，所以普通用户几乎不需要去了解如何手动安装包。

 Sublime Text的包管理器是 [Package Control](https://packagecontrol.io/)。

包的安装通常采用以下两种主要方式：

- 复制Sublime Text资源到 *`Packages`*
- 复制`.sublime-package`文件到*`Installed Packages`*。

##### 禁用包

把包名加入到`Packages/User/Preferences.sublime-settings`中的`ignored_packages`以临时禁用包。

##### 启用包

从`Packages/User/Preferences.sublime-settings`中的`ignored_packages`中删除要启用的包名即可。

##### 删除包

如果你是通过包管理器安装的，那么使用包管理器的默认卸载方法。

如果你是手动安装的包，那么按一下步骤来安全删除一个包：

1. Sublime Text打开时先禁用包。
2. 关闭Sublime Text。
3. 从硬盘中删除包的资源。
4. 从 `ignored_packages` 中移除包名。

除了最开始位于 *`Packages`*和*`Installed Packages`*中的资源，插件还会创建其他文件（例如`.sublime-settings`文件）来存储有关包的相关信息。 通常情况下，你可以在*User* package下找到这些文件。因此，如果你想彻底卸载包，还需要找到这些额外的文件一并删除。

⚠️Sublime Text更新时会把所有自带的包复原，所以自带包是无法彻底删除的，如果你想停止使用自带包，直接禁用就行。

#### 定制化或覆盖包
 `.sublime-package` 是只读的，所以你无法直接编辑它。但是，Sublime Text允许你创建覆盖包，这无需修改原始存档就可以有效注入到原始存档中。

创建覆盖包：在*`Packages`*下创建一个新的文件夹，以你要修改的`.sublime-package` 文件的名称命名，不带后缀。在此包中创建的任何文件，将优先于原包中的同名文件。

⚠️覆盖包中的文件是全部替换原始文件，所以相应的`.sublime-package`中的文件更新是你可能注意不到。
#### 合并与优先顺序
包的优先级对于合并某些资源来说非常重要。

如果存在一个 `.sublime-package` 的覆盖包，它将和`.sublime-package`同时加载。

Sublime Text加载包的顺序如下：

1. `Packages/Default`；
2. 默认包，按字典顺序；
3. 已安装的包，按字典顺序；
4. 除 `Packages/User`外所有用户包，按字典顺序；
5. `Packages/User`


### 还原Sublime Text为默认配置

把Sublime Text恢复到初始状态可以解决Sublime Text的一些错误（然而这些错误通常是由于插件造成的）。

把Sublime Text恢复到默认状态并删除所有的个人配置，删除packages目录并重启编辑器。`Installed Packages` 会被一并删除，所以你安装的插件都宣告拜拜了。

在做这种操作之前务必备份数据。

[返回目录](#目录)

## 命令行
请参看[OS X命令行](../miscellaneous/README.md#os-x命令行)

[返回目录](#目录)

## 参考
本节包含Sublime Text的一些简要的技术，它的目的是给想要更改Sublime Text默认行文的高级用户提供快速参考。
### 语法定义
Sublime Text 3084版本加入了一种新的语法定义格式，扩展名为`.sublime-syntax`。目前只在 [开发版](http://www.sublimetext.com/3dev) 可用。
#### 和Textmate兼容

通常情况，Sublime Text语法定义和Textmate语言文件是相兼容的。

#### 文件格式

Textmate语法定义是扩展名为 `tmLanguage` 的Plist文件。然而为了方便，本参考中用YAML来代替。

此外，Sublime Text也识别`hidden-tmLanguage` 为扩展名的文件，“文件内查找”会用到这个东西。缺点是不能被其它语言的import语句引入。

	---
	name: Sublime Snippet (Raw)
	scopeName: source.ssraw
	fileTypes: [ssraw]
	uuid: 0da65be4-5aac-4b6f-8071-1aadb970b8d9
	
	patterns:
	- comment: Tab stops like $1, $2...
	  name: keyword.other.ssraw
	  match: \$\d+
	
	- comment: Variables like $PARAM1, $TM_SELECTION...
	  name: keyword.other.ssraw
	  match: \$([A-Za-z][A-Za-z0-9_]+)
	  captures:
	    '1': {name: constant.numeric.ssraw}
	
	- name: variable.complex.ssraw
	  begin: '(\$)(\{)([0-9]+):'
	  beginCaptures:
	    '1': {name: keyword.other.ssraw}
	    '3': {name: constant.numeric.ssraw}
	  end: \}
	  patterns:
	  - include: $self
	  - name: support.other.ssraw
	    match: .
	
	- name: constant.character.escape.ssraw
	  match: \\[$<>]
	
	- name: invalid.illegal.ssraw
	  match: '[$<>]'
	  ...

- `name`
  语法定义的描述性名称。显示在Sublime Text界面语法定义菜单右下角的下拉列表中。

- `scopeName`
  此语法定义最顶层作用域的名称，不管是`source.<lang>`还是`text.<lang>`。用`source`来表示编程语言，用`text`表示标记性语言或其它东西。

- `fileTypes`
  可选。这是一个文件扩展名（不带前面的点）的列表。当打开这些类型的文件时，Sublime Text将自动激活其语法定义。

- `uuid`
  语法定义的唯一识别码。

- `patterns`
  你的匹配模式的容器，数组格式。

- `repository`
  可选。从 `patterns` 中抽象出来的模式数组。对于保持语法定义的整洁或是对于复用模式、递归调用等一些特殊用途来说很有用。

#### 匹配模式的数组

 `patterns` 数组中的元素。

- `match`
  包含以下元素：

  | `match`    | 搜索的匹配项                     |
  | ---------- | :------------------------- |
  | `name`     | 可选，安排给`match`匹配到的内容的作用域名称。 |
  | `comment`  | 可选，注释。                     |
  | `captures` | 可选，让`match`更加细致。           |

  `captures`可以包含下列元素项的*n*（`0`表示全部匹配）：

  | `0..n` | 引用分组的名称，必须是字符串。 |
  | ------ | --------------- |
  | `name` | 组的作用域           |

  例如：

  ```
  # Simple

  - comment: Sequences like \$, \> and \<
    name: constant.character.escape.ssraw
    match: \\[$<>]

  # With captures

  - comment: Tab stops like $1, $2...
    name: keyword.other.ssraw
    match: \$(\d+)
    captures:
      '1': {name: constant.numeric.ssraw}
  ```
- `include`
  包含repository中的条目、其它语法定义或是当前这个。

  参考：

  | $self     | 当前语法定义               |
  | --------- | -------------------- |
  | #itemName | repository中的itemName |
  | source.js | 外部语法定义               |

  例如：

  ```
  # Requires presence of DoubleQuotedStrings element in the repository.
  - include: '#DoubleQuotedStrings'

  # Recursively includes the complete current syntax definition.
  - include: $self

  # Includes and external syntax definition.
  - include: source.js
  ```
- `begin..end`
  定义多行文本的作用域。

  包含下列元素（只有`begin`和`end`是必选的）：

  | `name`          | 包含标记的内容的作用域名称  |
  | --------------- | -------------- |
  | `contentName`   | 不包含标记的内容的作用域名称 |
  | `begin`         | 匹配的开始标识        |
  | `end`           | 匹配的结束标识        |
  | `name`          | 全部区域的作用域       |
  | `beginCaptures` | 参看 `captures`  |
  | `endCaptures`   | 参看 `captures`  |
  | `patterns`      | 匹配项列表，用来匹配内容   |

  例如：

  ```
  name: variable.complex.ssraw
  begin: '(\$)(\{)([0-9]+):'
  beginCaptures:
    '1': {name: keyword.other.ssraw}
    '3': {name: constant.numeric.ssraw}
  end: \}
  patterns:
  - include: $self
  - name: support.other.ssraw
    match: .
  ```

#### Repository
可以从 `patterns` 或其自身的 `include` 元素中被引用。

repository可以包含下列元素：

```
repository:

  # Simple elements
  elementName:
    match: some regexp
    name:  some.scope.somelang

  # Complex elements
  otherElementName:
    patterns:
    - match: some regexp
      name:  some.scope.somelang
    - match: other regexp
      name:  some.other.scope.somelang
```
例子：

	repository:
	  numericConstant:
	    patterns:
	    - name: constant.numeric.double.powershell
	      match: \d*(?<!\.)(\.)\d+(d)?(mb|kb|gb)?
	      captures:
	        '1': {name: support.constant.powershell}
	        '2': {name: support.constant.powershell}
	        '3': {name: keyword.other.powershell}
	    - name: constant.numeric.powershell
	      match: (?<!\w)\d+(d)?(mb|kb|gb)?(?!\w)
	      captures:
	        '1': {name: support.constant.powershell}
	        '2': {name: keyword.other.powershell}
	
	  scriptblock:
	    name: meta.scriptblock.powershell
	    begin: \{
	    end: \}
	    patterns:
	    - include: $self

#### 转义序列

在需要的时候确保对 JSON/XML进行转义。

对于YAML，请确保你没有使用一个不带引号的字符串作为开始。

示例将**无法**按预期生效。

```
match: [aeiou]

include: #this-is-actually-a-comment

match: "#"\w+""
```
### 配色方案
#### 概述

用来对代码进行颜色高亮。例如：背景色、前景色...

#### 文件格式

扩展名为`.tmTheme`的文件，文件格式继承自Textmate。

注：Sublime Text使用`.tmTheme`作为扩展名来保持与Textamte相兼容。有一个容易混淆的地方是，Sublime Text还有一个用户界面（UI）主题的概念。UI主题是用来改变编辑器外观的。一定要记住这两个不是一个东西。一般来说，创建一个UI主题要比创建一个配色方案要复杂的多。

#### 存储位置

你可以把配色方案文件放到Packages下的任何地方（甚至是深层次的嵌套）。

约定配色方案都用 *Color Scheme*作为前缀，如：*Color Scheme - Default*。

可选配色方案在菜单栏中的 **Preferences → Color Scheme**

#### 文件结构

配色方案文件是基于Property List格式的。所有配色方案最外层的结构都是一致的。

颜色的写法支持： `#RRGGBB`， `#RGB`。

大多数控制颜色的元素都支持alpha通道：`#RRGGBBAA`。

##### 配色方案文件最外层元素

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   <key>name</key>
   <string>Monokai</string>
   <key>settings</key>
   <array>
   ... INSERT AWESOME COLORS HERE ...
   </array>
   <key>uuid</key>
   <string>D8D5E82E-3D5B-46B5-B38E-8C841C21347D</string>
</dict>
</plist>
```
`name`
可选，配色方案的名称，Sublime Text会忽视。

`uuid`
可选，唯一的标识符，Sublime Text会忽视。

##### 设置的子元素

Sublime Text支持以下几种配色方案的设置：

- 全局设置

  此处的设置会影响全局，在 `<array>`中的`<dict>`中设置。

  ```xml
  <array>
     <dict>
        <key>settings</key>
        <dict>
           <key>background</key>
           <string>#272822</string>
           <key>caret</key>
           <string>#F8F8F0</string>
           ...
        </dict>
     </dict>
  ...
  </array>
  ```
- 按类型排序的全局设置

  - 普通

    `foreground`
    视图的前景色。

    `background`
    视图的背景色。

    `invisibles`
    忽略。

    `caret`
    插入符的颜色。

    `lineHighlight`
    插入符所在行的颜色，只有 `higlight_line` 设置成`true`才有效。

  - 括号

    `bracketContentsForeground`
    插入符在括号中时，括号中文字的颜色。需要设置`match_brackets`为`true`。

    `bracketContentsOptions`
    当光标在括号时控制某些选项，需要设置`match_brackets`为`true`。

    选项： `underline`，`stippled_underline`，`squiggly_underline`。*underline*表示文字应该用指定颜色绘制，而不仅仅是下划线。

    `bracketsForeground`
    插入符挨着括号时括号的颜色。需要设置`match_brackets`为`true`。

    `bracketsOptions`
    当光标挨着括号时控制某些选项，需要设置`match_brackets`为`true`。

    选项： `underline`，`stippled_underline`，`squiggly_underline`。*underline*表示文字应该用指定颜色绘制，而不仅仅是下划线。

  - 标签

    `tagsForeground`
    插入符挨着标签时标签的颜色。需要设置`match_tags`为`true`。

    `tagsOptions`
    当光标挨着标签时控制某些选项，需要设置`match_tags`为`true`。

    选项： `underline`，`stippled_underline`，`squiggly_underline`。*underline*表示文字应该用指定颜色绘制，而不仅仅是下划线。

  - 查找

    `findHighlight`
    匹配结果的背景色。

    `findHighlightForeground`
    匹配结果的前景色。

  - Gutter（指显示行号那个区域）

    `gutter`
    gutter背景色。

    `gutterForeground`
    gutter前景色。

  - 选择块

    `selection`
    选中区域文字颜色。

    `selectionBackground`
    选中区域背景色。

    `selectionBorder`
    选中区域的边框颜色。

    `inactiveSelection`
    非活动部分的颜色。

  - 引导

    `guide`
    引导的颜色。

    `activeGuide`
    有插入符的行的引导颜色。`indent_guide_options`需设置为`draw_active`。

    `stackGuide`
    当前引导的父级引导颜色。

    `indent_guide_options`需设置为`draw_active`。

  - 高亮区域

    `highlight`
    带有`sublime.DRAW_OUTLINED`标签时通过 `sublime.add_regions()` 添加的区域的背景色。

    `highlightForeground`
    带有`sublime.DRAW_OUTLINED`标签时通过 `sublime.add_regions()` 添加的区域的前景色。

  - 阴影

    `shadow`
    滚动时阴影的颜色。

    `shadowWidth`
    滚动时阴影的宽度。

- 范围设置

  特殊作用域的设置。

  ```xml
  <array>
     ...
     <dict>
        <key>name</key>
        <string>Comment</string>
        <key>scope</key>
        <string>comment</string>
        <key>settings</key>
        <dict>
           <key>foreground</key>
           <string>#75715E</string>
        </dict>
     </dict>
     ...
  </array>
  ```
  `name`
  名称。

  `scope`
  作用域名称。

  `settings`
  设置的容器。合法的设置：

  `fontStyle`
  字体样式，选项：`bold`， `italic`。

  `foreground`
  前景色。

  `background`
  背景色。

#### Sublime Text中有关配色的设置

`color_scheme`
配色方案文件的路径（如：`Packages/Color Scheme - Default/Monokai.tmTheme`）。

### 构建系统
利用构建系统，你无需离开Sublime Text就可以通过运行外部程序来查看文件的效果。
#### 基本信息

构建系统只需要一个 `.sublime-build` 文件，更高级的构建系统最多也只会包含下列三部分：

- 一个`.sublime-build` 文件（JSON格式的配置文件）
- 可选，一个驱动构建进程的自定义Sublime Text命令（Python代码）
- 可选，一个外部可执行文件（脚本或是二进制代码）

**`.sublime-build` 文件**

`.sublime-build` 文件包含了JSON对象、各种选项和环境配置数据作为配置数据。每个 `.sublime-build` 文件通常和特定作用域中相应文件类型相关联（如`source.python`）。

文件名就代表了构建系统，每当你可以选择构建系统时它就会展示出来。

**例子**

```json
{
    "cmd": ["python", "-u", "$file"],
    "file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
    "selector": "source.python"
}
```

**构建系统中使用的Sublime Text命令**

当你运行Sublime Text中默认的构建任务（`Ctrl+B`）时，一个Sublime Text命令就会接收到 `.sublime-build` 中指定的配置数据，然后就会*构建*文件，通常情况，它会调用一个外部程序。构建系统中默认使用的命令是 `exec`，这个命令也可以被重写。

**重写构建系统默认执行命令**

 构建系统默认是通过`Packages/Default/exec.py`执行一个`exec`命令，这个命令只需要把配置数据转发到外部程序即可异步运行了。

在 `.build-system` 文件中使用`target`选项就可以重写 `exec` 命令了。详细查看下节配置。

**调用外部程序**

构建系统可以调用外部程序来处理文件，这个外部程序可以是shell脚本、标准化的utility（如`make`或`tidy`）等等。通常情况，外部程序在接收配置数据的同时也会接收文件或目录的路径。

注意：构建系统可以但是没必要调用一个外部程序，一个构建系统可以被完全地实现成一个Sublime Text命令。

#### 配置

⚠️开发版本中构建系统章节正在被重新调整，所以下面的内容可能已经过时了。

##### 概述

Sublime Text中的构建系统框架足够灵活所以它可以容纳大量的构建场景。
如果默认配置满足不了你的需求，你可以通过以下两种主要方式实现你自己的构建系统：

- 自定义的`target` 命令（仍然使用默认的构建系统框架）
- 新的插件（与默认构建系统无关）

##### 构建系统中的Meta选项
这是所有构建系统都能够理解的标准选项，这些选项由Sublime Text内部使用。 `target` 选项不接收任何选项。

`target`（可选）
一个 Sublime Text `WindowCommand`，默认为 `exec` （`Packages/Default/exec.py`）。此命令接收所有在 `.sublime-build` 文件中指定的目标命令参数。
用来覆盖构建系统的默认命令，注意，如果你选择了覆盖构建系统的默认命令，你可以把任意数量的额外选项添加到`.sublime-build`中。

`selector`（可选）
**Tools | Build System | Automatic**设置为 `true`，Sublime Text使用这个范围选择器来为当前活动视图找到合适的构建系统。

`windows`, `osx` and `linux`（可选）
用于操作系统有选择性的应用选项，特定的操作系统的值将覆盖默认值，列出的项中每一个都接受一个字典选项。

`variants`（可选）
选项中的一个字典列表，如果构建系统的选择器匹配了当前活动的文件，出现在命令面板的Variant的名称就可以方便地进行调用。
可以在同一个 `.sublime-build` 文件中指定多个构建系统任务。

`name` （可选）
**只有在variant中才合法**。标识构建系统任务，如果`name`是“Run”，variant将会显示在 **Tools | Build System**下。Sublime Text自动绑定“Run”任务到 `Ctrl+Shift+B`。

**特定平台选项**
`windows`、 `osx`和`linux` 使你可以在构建系统中添加指定平台的数据。例如：

```json
{
    "cmd": ["ant"],
    "file_regex": "^ *\\[javac\\] (.+):([0-9]+):() (.*)$",
    "working_dir": "${project_path:${folder}}",
    "selector": "source.java",

    "windows": {
        "cmd": ["ant.bat"]
    }
}
```

这个例子中，除Windows外的其他平台将执行`ant`命令，而Windows将执行`ant.bat`。

**Variants**

例子：

```json
{
    "selector": "source.python",
    "cmd": ["date"],

    "variants": [

        { "name": "List Python Files",
          "cmd": ["ls -l *.py"],
          "shell": true
        },

        { "name": "Word Count (current file)",
          "cmd": ["wc", "$file"]
        },

        { "name": "Run",
          "cmd": ["python", "-u", "$file"]
        }
    ]
}
```

 `Ctrl+B` 将执行*date*命令，`Crtl+Shift+B`将会运行Python解析器，其余的将会在构建系统被激活时已`Build: name`的形式出现在命令面板中。

##### 捕获构建系统的结果

当构建系统输入文本到结果视图中时，你可以捕获*结果数据*以便启用结果导航。
注：*结果*也被称作*错误*。

参照下面的**视图设置**：
`result_file_regex`
一个Perl风格的正则表达式，捕获结果视图中错误信息中的资格字段，分别是：文件名、行数、列数、错误信息。

`result_line_regex`
 `result_file_regex` 不匹配，而`result_line_regex`存在且匹配当前行，在缓存中向后查找知道匹配了`result_file_regex`，这两个综合起来来确定将要跳转到哪个文件中的哪一行。

`result_base_dir`
用来寻找出错的文件。

##### 构建系统变量

 `.sublime-build` 文件中有以下变量：

| `$file_path`         | 当前文件的路径，如：*C:\Files*                 |
| -------------------- | ------------------------------------ |
| `$file`              | 当前文件的绝对路径，如：*C:\Files\Chapter1.txt*。 |
| `$file_name`         | 当前文件的文件名， 如：*Chapter1.txt*。          |
| `$file_extension`    | 当前文件的扩展名，如：*txt*。                    |
| `$file_base_name`    | 当前文件的名字部分，如：*Document*。              |
| `$folder`            | 当前项目中被打开的第一个文件夹路径。                   |
| `$project`           | 当前项目的绝对路径。                           |
| `$project_path`      | 当前项目的路径。                             |
| `$project_name`      | 当前项目的名字。                             |
| `$project_extension` | 当前项目的扩展名部分，                          |
| `$project_base_name` | 当前项目的名字部分。                           |
| `$packages`          | *Packages*文件夹的绝对路径。                  |

##### 运行构建系统

 从**Tools | Build System**选择构建系统，然后选择**Tools | Build**。另外，你也可以用下列快捷方式：

| `Ctrl+B`       | 运行默认构建任务      |
| -------------- | ------------- |
| `F7`           | 运行默认构建任务      |
| `Ctrl+Shift+B` | 运行 “Run” 构建任务 |
| `Ctrl+Break`   | 取消当前的构建任务     |

#### `exec`命令的参数

`cmd`
`shell_cmd`为空时则必需。否则将会被 `shell_cmd`覆盖。
包含将运行的命令及其参数的数组。如果不指定一个绝对路径，将会在`PATH`中搜索外部的程序。最终将会调用`subprocess.Popen(cmd)`。

`shell_cmd`
`cmd`为空时则必需。否则将会被 `cmd`覆盖。
一个指定将运行的命令及其参数的字符串，最终将会调用`subprocess.Popen(shell_cmd, shell=True)`。

`working_dir`
可选。运行`cmd`之前改变当前目录的指向目录，当前目录的原始值将会在之后恢复。

`encoding`
可选。输出`cmd`的编码，必须是合法的Python编码格式，默认是`UTF-8`。

`env`
可选。传递给`cmd`之前将与当前进程进行合并的环境变量的字典。使用这个参数你就可以在不改变系统设置的情况编辑环境变量。

`shell`
可选。值为*true*时，`cmd`将通过shell（`cmd.exe`，`bash`等等）运行。如果使用了`shell_cmd`，则此选项无效。

`path`
可选。`cmd`子进程使用的`PATH`。使用这个参数就可以在不改变系统设置的情况添加字典到`PATH`中。

`file_regex`
可选。给结果视图设置 `result_file_regex` 。

`line_regex`
可选。给结果视图设置 `result_line_regex` 。

`syntax`
可选。如果设置了，就会使构建系统的输入有色彩。

#### 故障诊断

构建系统将会在 `PATH`中寻找可执行程序，所以你的 `PATH`必须设置正确。在一些操作系统中，终端和图形化的应用程序中的`PATH`可能不一样，因此，Sublime Text能否正常工作取决于你如何打开它。为了解决这个问题，确保你设置了 `PATH` 以便应用程序可以找到它。另外，你也可以在 `.sublime-build` 文件中使用 `path` 选项覆盖可执行程序的 `cmd`中指定的`PATH`。

### 按键绑定

按键绑定把按键映射到命令。

#### 文件格式

 `.sublime-keymap` 文件，JSON格式。可以防止package中的任何位置。

##### 给Keymap文件命名

命名为 `Default.sublime-keymap` 的文件会对所有平台生效。每个平台还可以设置独立的keymap：

- `Default (Windows).sublime-keymap`
- `Default (OSX).sublime-keymap`
- `Default (Linux).sublime-keymap`

其他与上述提到的文件名不相符的将被Sublime Text忽略。

##### 按键绑定的结构

- `keys`
  区分大小写的一个数组。

- `command`
  将执行的命名名称。

- `args`
  传递给`command`的参数形成的字典。关键字必须是`command`的参数名。

- `context`
  决定一个特定*上下文*的条件数组，所有条件需同时满足才算是符合条件。

例子：

```json
{ 
"keys": ["shift+enter"], 
"command": "insert_snippet", 
"args": {"contents": "\n\t$0\n"}, 
"context":
   [
      { "key": "setting.auto_indent", "operator": "equal", "operand": true },
      { "key": "selection_empty", "operator": "equal", "operand": true, "match_all": true },
      { "key": "preceding_text", "operator": "regex_contains", "operand": "\\{$", "match_all": true },
      { "key": "following_text", "operator": "regex_contains", "operand": "^\\}", "match_all": true }
   ]
}
```

##### Context的结构

`key`
上下文的名称。

`operator`
针对 `key`的值要进行的操作符，默认为`equal`。

`operand`
通过`key`返回的结果用这个值进行测试。

`match_all`
需要测试对所有选择都生效，默认为`false`。

**Context Operands**

`auto_complete_visible`
自动填充列表显示时返回`true`。

`has_next_field`
下一个代码段域可用时返回`true`。

`has_prev_field`
上一个代码段域可用时返回`true`。

`num_selections`
返回选择的数量。

`overlay_visible`
遮罩层可见时返回`true`。

`panel_visible`
面板可见时返回`true`。

`following_text`
限制测试插入符之后的文本。

`preceding_text`
限制测试为插入符之前的文本。

`selection_empty`
选择区域是空时返回`true`。

`setting.x`
返回`x`的值，setting.x可以是任意字符串。

`text`
限制测试为选中文本。

`selector`
返回当前作用域的名称。

`panel_has_focus`
如果面板中有输入框是focus时返回`true`。

`panel`
如果面板中指定的`operand`可见时返回`true`。

**Context Operators**

`equal`、`not_equal`
测试是否相等。

`regex_match`、`not_regex_match`
通过正则表达式匹配（全匹配）。

`regex_contains`、`not_regex_contains`
通过正则表达式匹配（部分匹配）。

#### 命令模式

Sublime Text提供了一个 `command_mode` 设置防止按键事件被发送到缓冲区。这还是很有用的，例如，模拟VIM的模态行为。

不适用于命令模式的按键绑定应该包含类似下面的内容：

```json
{"key": "setting.command_mode", "operand": false}
```

通过这种方式，使用了命令模式的插件将能够无干扰地定义合适的键绑定。

#### 可绑定的按键

按键绑定中的key必须是指定的字面量或名称，如果使用名称不生效，换成字面量试试。合法名称列表如下：

- `up`
- `down`
- `right`
- `left`
- `insert`
- `home`
- `end`
- `pageup`
- `pagedown`
- `backspace`
- `delete`
- `tab`
- `enter`
- `pause`
- `escape`
- `space`
- `keypad0`
- `keypad1`
- `keypad2`
- `keypad3`
- `keypad4`
- `keypad5`
- `keypad6`
- `keypad7`
- `keypad8`
- `keypad9`
- `keypad_period`
- `keypad_divide`
- `keypad_multiply`
- `keypad_minus`
- `keypad_plus`
- `keypad_enter`
- `clear`
- `f1`
- `f2`
- `f3`
- `f4`
- `f5`
- `f6`
- `f7`
- `f8`
- `f9`
- `f10`
- `f11`
- `f12`
- `f13`
- `f14`
- `f15`
- `f16`
- `f17`
- `f18`
- `f19`
- `f20`
- `sysreq`
- `break`
- `context_menu`
- `browser_back`
- `browser_forward`
- `browser_refresh`
- `browser_stop`
- `browser_search`
- `browser_favorites`
- `browser_home`

##### 修饰符

- `shift`
- `ctrl`
- `alt`
- `super` （Windows键, Command键…）

##### 警告

如果你在开发一个包，请注意：

- `Ctrl+Alt+<alphanum>` 不应该在任何Windows按键绑定中使用。
- `Option+<alphanum>` 不应该在任何OS X按键绑定中使用。

这两种情况，用户插入非ASCII字符将会有其他风险。

#### 保持Keymap有组织性

Sublime Text默认的按键映射位于 `Packages/Default`下。其他包也许会包含其自己的按键映射文件。

推荐把个人的按键映射文件放到`Packages/User`下。

#### 国际化键盘

由于Sublime Text映射名称到按键的方式，按键名可能和US英语以外的键盘布局中的按键不对应。

#### 故障诊断

启用按键绑定相关的日志，参考：

- [sublime.log_commands(flag)](http://www.sublimetext.com/docs/3/api_reference.html).
- [sublime.log_input(flag)](http://www.sublimetext.com/docs/3/api_reference.html).

这将帮助你调试按键绑定。

### 菜单

#### 文件格式

| **Format**    | JSON （带注释）                               |
| ------------- | ---------------------------------------- |
| **Extension** | `.sublime-menu`                          |
| **Name**      | 可用菜单项的列表，查看[Available Menus](http://docs.sublimetext.info/en/latest/customization/menus.html#menu-types) |
| **Location**  | *`Packages`*下的任意位置                       |
| **Content**   | [“Menu Item” 对象](http://docs.sublimetext.info/en/latest/reference/menus.html#menu-item-objects)的列表 |

**例子**

下面的内容是 `Main.sublime-menu` 文件中的一个摘要：

```json
[
    {
        "caption": "Edit",
        "mnemonic": "E",
        "id": "edit",
        "children":
        [
            { "command": "undo", "mnemonic": "U" },
            { "command": "redo_or_repeat", "mnemonic": "R" },
            {
                "caption": "Undo Selection",
                "children":
                [
                    { "command": "soft_undo" },
                    { "command": "soft_redo" }
                ]
            },
            { "caption": "-", "id": "clipboard" },
            { "command": "copy", "mnemonic": "C" },
            { "command": "cut", "mnemonic": "t" },
            { "command": "paste", "mnemonic": "P" },
            { "command": "paste_and_indent", "mnemonic": "I" },
            { "command": "paste_from_history", "caption": "Paste from History" }
        ]
    }
]
```

#### “Menu Item”对象

除非你通过一个ID来引用已有项目，否则每个菜单项必须定义其 `children`或`command`或`caption`。

菜单项包含下列属性：

`command`
菜单项选中时将调用的命令的名称。

`args`
命令的参数，是一个对象。对于**Side Bar** 和 **Side Bar Mount Point** 菜单，这是一个由侧边栏包含所有选中项的列表的文件参数所扩展的。

`caption`
菜单栏上展示的文字。

`children`
鼠标滑过菜单项时显示的列表，覆盖已存在的`command`属性。

`mnemonic`
菜单的快捷键，区分大小写的单个字符，必须包含在caption中。

`id`
菜单项的唯一字符串标识符。这可以用来扩展菜单或是子菜单，甚至完全改写菜单。

### 设置

⚠️本节内容也许包含过时的和未完成的信息，你可以在默认的设置文件（**Preferences → Settings - Default** or`Default/Preferences.sublime-settings`）中查看可用的设置。

#### 全局设置

这些设置只能从 `Preferences.sublime-settings` and`Preferences (*platform*).sublime-settings`进行编辑。

`theme`
使用的主题，如：`Default.sublime-theme`。

`scroll_speed`
设置为0禁用滚动，设置0到1之间缓慢滚动，设置超过1快速滚动。

`hot_exit`
 `hot_exit` 启用时，无需提示就可以立即关闭应用程序或窗口，未保存的编辑和已打开的文件在下次启动时将被恢复。

`remember_open_files`
决定是否重新打开Sublime Text上次关闭时打开的文件。

`open_files_in_new_window`
只在OS X有效，控制是否创建了一个新窗口。

`close_windows_when_empty`
最后一个文件关闭时直接关闭窗口。

`show_full_path`
在标题栏显示文件的绝对路径。

`preview_on_click`
值为`true`时，点击侧边栏的文件时将预览其内容。双击将会在新标签打开这个文件。

`folder_exclude_patterns`
排除匹配的文件夹。

`file_exclude_patterns`
排除匹配的文件。

`binary_file_patterns`
从跳转、查找文件中排除匹配到的文件，但不从侧边栏排除。

`show_tab_close_buttons`
值为`false`时将隐藏标签上的关闭按钮知道鼠标悬停在tab上。

`mouse_wheel_switches_tabs`
值为`true`时，如果鼠标停在tab区域，滚动鼠标的滚轮将会切换标签。

`ignored_packages`
被忽略的（不加载）包的列表。

#### 文件设置

##### 空格和缩进

`auto_indent`
切换自动缩进。

`tab_size`
`Tab`键等价于几个空格。

`translate_tabs_to_spaces`
决定按下`Tab`键时是否把tab符转化成`tab_size`规定的空格数。

`use_tab_stops`
如果`translate_tabs_to_spaces`值为`true`，每一次按下`Tab`键和`Backspace`键都将插入或删除 `tab_size`规定的空格数。

`trim_automatic_white_space`
切换是否删除由 `auto_indent`添加的空格。

`detect_indentation`
值为`false`时，文件加载后将禁用tab和空格。如果值为`true`，将自动编辑`translate_tabs_to_spaces`和`tab_size`。

`draw_white_space`
合法的值：`none`， `selection`， `all`。

`trim_trailing_white_space_on_save`
值为`true`时保存文件时将删除空格。

##### 视觉设置

`always_show_minimap_viewport`
设置为`true`时，将会在始终在缩略图区域高亮显示当前文件位置；默认值是`false`，这种情况只有鼠标移到缩略图区域才能看到当前文件所在位置。这里说的缩略图就是右侧整个文件的缩略。

`color_scheme`
设置文本高亮的颜色。如：`Packages/Color Scheme - Default/Monokai Bright.tmTheme`。

`font_face`
可编辑的文字字体。

`font_size`
可编辑的文字字号。

`font_options`
合法值：`bold`，`italic`，`no_antialias`，`gray_antialias`，`subpixel_antialias`，`directwrite`（Windows）。

`gutter`
切换gutter。

`rulers`
显示垂直规则的列，接收一个包含数值的数组（如`[79,89,99]`）或者一个单一的数值（如`79`）。

`draw_minimap_border`
是否对缩略图区域当前视图可见文本区域画边框，颜色主题中的`minimapBorder`控制边框的颜色。

`highlight_line`
设置为`false`禁用高亮当前行。

`line_padding_top`
每行顶部额外的空白，像素单位。

`line_padding_bottom`
每行底部额外的空白，像素单位。

`scroll_past_end`
设置为`false`时禁用滚动到文件的底部，设置为`true`时Sublime Text将会在最后一行和窗体底部留下一个大的边距。

`line_numbers`
切换是否显示行号。

`word_wrap`
设置为`false`时，长文本将不会换行，需要横向滚动以看全其它文本。

`wrap_width`
如果比`0`大，长行的换行将依据指定列而不是窗口的宽度。只有`word_wrap`设置为`true`时这个设置才会生效。

`indent_subsequent_lines`
设置为`false`时，换行的行将不会有缩进。只有`word_wrap`设置为`true`时这个设置才会生效。

`draw_centered`
是否居中对齐。

`match_brackets`
设置为`false`时禁用给光标周围的括号添加下划线。

`match_brackets_content`
当光标靠近一个括号时如果你仅仅想高亮显示括号，将其值设置为`false`。

`match_brackets_square`
设置为`false`禁用高亮方括号。`match_brackets`为`true`时才会生效。

`match_bracktets_braces`
设置为`false`禁用高亮花括号。`match_brackets`为`true`时才会生效。

`match_bracktets_angle`
设置为`false`禁用高亮尖括号。`match_brackets`为`true`时才会生效。

##### 自动行为

`auto_match_enabled`
切换自动匹配引号、括号等。

`save_on_focus_lost`
值为`ture`时，切换到其他文件或应用程序将自动保存文件。

`find_selected_text`
值为`true`时，当打开查找面板，选中的文字会自动被复制到面板中。

`word_separators`
单词分隔符。

`ensure_newline_at_eof_on_save`
保存时始终在文件末尾加新的一行。

##### 系统和其它设置

`is_widget`
相对于一个常规文件，如果文件是对话框中的输入字段，返回`true`。

`spell_check`
切换拼写检查。

`dictionary`
拼写检查的单词列表，接收一个数据目录的路径，如：`Packages/Language - English/en_US.dic`。

`fallback_encoding`
当不能自动决定编码时使用的编码格式，ASCII、UTF-8和UTF-16编码格式将会被自动检测。

`default_line_ending`
决定用来指定新行的字符，合法的值：`system` （OS-dependant），`windows` （`CRLF`）和 `unix`（`LF`）。 

`tab_completion`
决定按下`Tab`键是否进行补全操作。

##### 构建和错误导航设置

`result_file_regex` and `result_line_regex`
用来提取打印到视图或是输出面板的错误信息的正则表达式。

`result_base_dir`
开始查找基于用`result_file_regex`和`result_line_regex`进行信息提取问题的文件的文件夹

`build_env`
默认添加到构建系统的路径列表。

##### 文件和目录设置

`default_dir`
设置视图的默认保存文件夹。

##### 输入设置

`command_mode`
值为`true`时，文件将会忽略按键的点击，在模拟VIM模态行为时很有用。

### 补全文件

注意补全并不限制于补全文件，因为其他来源也会对补全做出补充，参考补全章节的内容。然而，Sublime Text中提供给你用来完善补全功能的最明显的方法就是通过 `.sublime-completions` 文件。

补全文件是带有 `.sublime-completions` 后缀的JSON文件。

#### 例子

```json
{
   "scope": "text.html - source - meta.tag, punctuation.definition.tag.begin",

   "completions":
   [
      { "trigger": "a", "contents": "<a href=\"$1\">$0</a>" },
      { "trigger": "abbr\t<abbr>", "contents": "<abbr>$0</abbr>" },
      { "trigger": "acronym", "contents": "<acronym>$0</acronym>" }
   ]
}
```

**scope**

确定补全列表何时被填充。

**completions**

*补全*的数组。

#### 补全的类型

##### 纯字符串

纯字符串等价于`trigger` 和`contents`一致的条目。

```
"foo"
// is equivalent to:
{ "trigger": "foo", "contents": "foo" }

```

##### 基于Trigger的补全

```
{ "trigger": "foo", "contents": "foobar" },
{ "trigger": "foo\ttest", "contents": "foobar" }

```

**trigger**

展示到补全列表中的文字，选中时将会插入`contents`中的内容。

你可以使用`\t`添加一个*提示*，提示是右对齐的、略微有点灰色，不影响当前的触发器。

**contents**

插入到文件中的文本。

注意：如果你想要一个字面量`$`，你需要进行转义`\\$`（由于是在一个JSON字符串中，所以需要双斜杠）。

### 符号

#### 概述

Sublime Text对符号导航提供了基本的支持（跳转到类和函数的定义），任何文件都可启用文件导航。

#### 格式

符号使用元数据文件定义。

和常规元数据文件一样，符号定义文件有 `.tmPreferences` 后缀，且使用Property List格式。文件名会被Sublime Text忽略。

#### 定义符号

Sublime Text有两种符号列表：局部符号列表（当前文件）和全局符号列表（项目范围）。

符号定义文件使用作用域选择器在源代码中捕获符号。

同一个包中可以共存多个符号定义文件，例如，两个符号定义文件可以串联工作：一个将定义所有符号，和第二个可以选择性地隐藏其中的一些。

符号定义文件示例：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   <key>name</key>
   <string>Symbol List</string>
   <key>scope</key>
   <string>source.python meta.function.python, source.python meta.class.python</string>
   <key>settings</key>
   <dict>
      <key>showInSymbolList</key>
      <integer>1</integer>
   </dict>
</dict>
</plist>
```

上述文件，Sublime Text将会用`source.python meta.function.python`和`source.python meta.class.python`去查找源文件，找到的将被作为符号。 `showInSymbolList` 的设置告诉Sublime Text使用局部符号列表。

#### 文本转换

符号显示给用户时可以对它们进行转换，符号转换包含了使用 [Oniguruma](http://www.geocities.jp/kosako3/oniguruma/)语法定义的文本替换正则表达式。

文本替换的例子：

```
s/class\s+([A-Za-z_][A-Za-z0-9_]*.+?\)?)(\:|$)/$1/g;
```

这个例子中， `class FooBar(object)` 在符号列表中将显示为 `FooBar(object)` 。

使用符号转换来扩展一下上面的例子：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   <key>name</key>
   <string>Symbol List</string>
   <key>scope</key>
   <string>source.python meta.function.python, source.python meta.class.python</string>
   <key>settings</key>
   <dict>
      <key>showInSymbolList</key>
      <integer>1</integer>
      <key>symbolTransformation</key>
      <string>
         s/class\s+([A-Za-z_][A-Za-z0-9_]*.+?\)?)(\:|$)/$1/g;
         s/def\s+([A-Za-z_][A-Za-z0-9_]*\()(?:(.{0,40}?\))|((.{40}).+?\)))(\:)/$1(?2:$2)(?3:$4…\))/g;
      </string>
   </dict>
</dict>
</plist>
```

#### 符号定义文件的结构

所有源文件的外部结构都是一样的，继承自Property List格式。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   ...
</dict>
</plist>
```

下面这些是符号定义文件中合法的元素：

`name`
可选，符号定义的名称，Sublime Text会忽略。

```xml
<key>name</key>
<string>Some arbitrary name goes here</string>
```

`scope`
以逗号分隔的作用域名称列表。

```xml
<key>scope</key>
<string>source.python meta.function.python, source.python meta.class.python</string>
```

`settings`
必需，设置的容器。

```xml
<key>settings</key>
<dict>
   ...
</dict>
```

`uuid`
可选，文件的唯一标识符，Sublime Text会忽略。

```xml
<key>uuid</key>
<string>BC062860-3346-4D3B-8421-C5543F83D11F</string>
```

#### `settings`子元素

`showInSymbolList`

可选，把符号和局部符号列表关联起来。合法值是`0`和`1`，`0`表示对应的符号不展示。

```xml
<key>showInSymbolList</key>
<integer>1</integer>
```

`showInIndexedSymbolList`

可选，把符号和全局符号列表关联起来。合法值是`0`和`1`，`0`表示对应的符号不展示。

```xml
<key>showInIndexedSymbolList</key>
<integer>1</integer>
```

`symbolTransformation`

可选，目标是局部符号列表。分号分隔的正则表达式列表。

```xml
<key>symbolTransformation</key>
<string>
   s/class\s+([A-Za-z_][A-Za-z0-9_]*.+?\)?)(\:|$)/$1/g;
   s/def\s+([A-Za-z_][A-Za-z0-9_]*\()(?:(.{0,40}?\))|((.{40}).+?\)))(\:)/$1(?2:$2)(?3:$4…\))/g;
</string>
```

`symbolIndexTransformation`

可选，目标是全局符号列表。

```xml
<key>symbolIndexTransformation</key>
<string>
   s/class\s+([A-Za-z_][A-Za-z0-9_]*.+?\)?)(\:|$)/$1/g;
   s/def\s+([A-Za-z_][A-Za-z0-9_]*\()(?:(.{0,40}?\))|((.{40}).+?\)))(\:)/$1(?2:$2)(?3:$4…\))/g;
</string>
```

#### 导航符号

一旦符号定义了，你就可以通过标准的快捷键来调用它们：

| `F12`          | 跳转到定义    |
| -------------- | -------- |
| `Ctrl+R`       | 显示局部符号列表 |
| `Ctrl+Shift+R` | 显示全局符号列表 |

### 注释

#### 概述

Sublime Text提供了一个默认的命令来注释和取消注释，支持任何类型使用了元数据文件的文件。

#### 文件格式

使用元数据文件定义注释标记。和普通元文件一样，注释元数据文件扩展名为 `.tmPreferences` ，使用 Property List 格式。查看[*Metadata Files*](http://docs.sublimetext.info/en/latest/reference/metadata.html)的官方介绍。

**示例**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   <key>name</key>
   <string>Miscellaneous</string>
   <key>scope</key>
   <string>source.python</string>
   <key>settings</key>
   <dict>
      <string></string>
      <key>shellVariables</key>
      <array>
         <dict>
            <key>name</key>
            <string>TM_COMMENT_START</string>
            <key>value</key>
            <string># </string>
         </dict>
      </array>
   </dict>
</dict>
</plist>
```

#### 元文件结构

所有源文件的外部结构都是一样的，继承自Property List格式。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   ...
</dict>
</plist>
```

下面这些是合法的元素：

`name`
可选，符号定义的名称，Sublime Text会忽略。

```xml
<key>name</key>
<string>Shell Variables</string>
```

`scope`
必需，以逗号分隔的作用域名称列表。

```xml
<key>scope</key>
<string>source.python</string>
```

`settings`
必需，设置的容器。

```xml
<key>settings</key>
<dict>
   ...
</dict>
```

`uuid`
可选，文件的唯一标识符，Sublime Text会忽略。

```xml
<key>uuid</key>
<string>BC062860-3346-4D3B-8421-C5543F83D11F</string>
```

#### `setting`子元素

`shellVariables`

必需，注释标记的容器。

```xml
<key>shellVariables</key>
<array>
   ...
</array>
```

#### `shellVariables`子元素

注意：`shellVariables` 数组可以包含任意的子元素，这里我们只关注和注释有关的。

`TM_COMMENT_START`
定义默认的注释标记。如果想定义一个额外的注释标记，取名为`TM_COMMENT_START_2`、`TM_COMMENT_START_3`等等。

```xml
<dict>
   <key>name</key>
   <string>TM_COMMENT_START</string>
   <key>value</key>
   <string># </string>
</dict>
```

`TM_COMMENT_END`
可选，定义注释标记的结束。如果省略的话，`TM_COMMENT_START`将被视为一个行注释标记。
如果开始和结束标记都有的话，则这一组将视为块级注释标记。
如果想定义一个额外的注释结束标记，取名为`TM_COMMENT_END_2`、`TM_COMMENT_END_3`等等。

```xml
<dict>
   <key>name</key>
   <string>TM_COMMENT_END_2</string>
   <key>value</key>
   <string>*/</string>
</dict>
```

`TM_COMMENT_DISABLE_INDENT`
可选，合法值为`yes`和`no`。禁用`TM_COMMENT_START`标记的缩进。如果要指定其他组的标记，使用 `TM_COMMENT_DISABLE_INDENT_2`等。

```xml
<dict>
   <key>name</key>
   <string>TM_COMMENT_DISABLE_INDENT</string>
   <key>value</key>
   <string>yes</string>
</dict>
```

**示例**

这里有一个更加完整的示例，使用了刚才说到的内容：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
   <dict>
      <key>shellVariables</key>
      <array>
         <dict>
            <key>name</key>
            <string>TM_COMMENT_START</string>
            <key>value</key>
            <string>// </string>
         </dict>
         <dict>
            <key>name</key>
            <string>TM_COMMENT_START_2</string>
            <key>value</key>
            <string>/*</string>
         </dict>
         <dict>
            <key>name</key>
            <string>TM_COMMENT_END_2</string>
            <key>value</key>
            <string>*/</string>
         </dict>
      </array>
   </dict>
   <key>uuid</key>
   <string>BC062860-3346-4D3B-8421-C5543F83D11F</string>
</dict>
</plist>
```

#### 相关快捷键

| `Ctrl+/`       | 切换行的注释 |
| -------------- | ------ |
| `Ctrl+Shift+/` | 切换块的注释 |

### Metadata文件

#### 概述

元数据是可以被分配到使用作用域选择器特定文本段的参数。

这些参数可以有多种用途，如：

- 指定当前注释标记，即使是在嵌入的源代码中，因此你可以用任何语法来切换注释。
- 定义自动缩进的规则。
- 快速浏览。

#### 文件格式

扩展名为 `.tmPreferences` ，使用 Property List 格式。

**示例**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple Computer//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   <key>name</key>
   <string>JavaScript Metadata</string>
   <key>scope</key>
   <string>source.js</string>
   <key>settings</key>
   <dict>
      <key>decreaseIndentPattern</key>
      <string>^(.*\*/)?\s*\}.*$</string>
      <key>increaseIndentPattern</key>
      <string>^.*\{[^}"']*$</string>

      <key>bracketIndentNextLinePattern</key>
      <string>(?x)
      ^ \s* \b(if|while|else)\b [^;]* $
      | ^ \s* \b(for)\b .* $
      </string>
   </dict>
   <dict>
      <key>shellVariables</key>
      <array>
         <dict>
            <key>name</key>
            <string>TM_COMMENT_START</string>
            <key>value</key>
            <string>// </string>
         </dict>
         <dict>
            <key>name</key>
            <string>TM_COMMENT_START_2</string>
            <key>value</key>
            <string>/*</string>
         </dict>
         <dict>
            <key>name</key>
            <string>TM_COMMENT_END_2</string>
            <key>value</key>
            <string>*/</string>
         </dict>
      </array>
   </dict>
   <key>uuid</key>
   <string>BC062860-3346-4D3B-8421-C5543F83D11F</string>
</dict>
</plist>
```

示例文件结合了多种类型的元数据。

#### 元文件结构

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
   ...
</dict>
</plist>
```

下面这些是合法的元素：

`name`
可选，符号定义的名称，Sublime Text会忽略。

```xml
<key>name</key>
<string>Shell Variables</string>
```

`scope`
必需，以逗号分隔的作用域名称列表。

```xml
<key>scope</key>
<string>source.python</string>
```

`settings`
必需，设置的容器。

```xml
<key>settings</key>
<dict>
   ...
</dict>
```

`uuid`
可选，文件的唯一标识符，Sublime Text会忽略。

```xml
<key>uuid</key>
<string>BC062860-3346-4D3B-8421-C5543F83D11F</string>
```

#### `settings`子元素

 `settings` 元素可以包含有不同用途的子元素。

##### 缩进选项

`increaseIndentPattern`
正则表达式，如果匹配到当前行，则下一行将会有向下一级别的缩进。

```xml
<key>increaseIndentPattern</key>
<string>insert regex here</string>
```

`decreaseIndentPattern`
正则表达式，如果匹配到当前行，则下一行将会有向上一级别的缩进。

```xml
<key>decreaseIndentPattern</key>
<string>insert regex here</string>
```

`bracketIndentNextLinePattern`
正则表达式，如果匹配到当前行，则仅仅是下一行将会有下一级别的缩颈。

```xml
<key>bracketIndentNextLinePattern</key>
<string>insert regex here</string>
```

`disableIndentNextLinePattern`
正则表达式，如果匹配到当前行，下一行将不再缩进。

```xml
<key>disableIndentNextLinePattern</key>
<string>insert regex here</string>
```

`unIndentedLinePattern`
正则表达式，自动缩进计算下一行的缩进层级时将忽略当前匹配行。

```xml
<key>unIndentedLinePattern</key>
<string>insert regex here</string>
```

##### 补全选项

`cancelCompletion`
正则表达式，如果匹配到当前行，会禁止补全弹出层。

```xml
<key>cancelCompletion</key>
<string>insert regex here</string>
```

##### Shell变量

Shell变量有多种用途且可以从代码段中访问，注意Shell变量是定义在array中的字典，因此和`settings`的子元素有不同的格式。

`shellVariables`
“shell变量”的容器。

```xml
<key>shellVariables</key>
<array>
   ...
</array>
```

**`shellVariables`的子元素**

```xml
<dict>
   <key>name</key>
   <string>BOOK_OPENING</string>
   <key>value</key>
   <string>Once upon a time...</string>
</dict>
```

#### 相关API函数

用 `view.meta_info(key, point)` 从插件代码中提取元数据。

### 命令面板

#### 文件格式

| **Format**    | JSON （带注释）          |
| ------------- | ------------------- |
| **Extension** | `.sublime-commands` |
| **Name**      | 任意                  |
| **Location**  | *`Packages`*下任何位置   |
| **Content**   | 命令面板可选项列表           |

#### 示例

这里有一个`Packages/Default/Default.sublime-commands`的部分内容：

```json
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

#### 命令面板项

下面这些事可以包含在 `.sublime-commands` 中的项：

`caption`
显示在命令面板中的文字。

`command`
将要执行的命令。

`args`
传递给`command`的参数。需要注意的是你需要用类似代码段形式的变量：`${packages}` 或 `$packages`来定位包文件夹，这和其他地方有点区别。

#### 使用方法

1. 按下`Ctrl+Shift+P`
2. 选择命令

可选项会根据输入的文字过滤，并不会一次显示所有的项。

### 插件

插件是从`sublime_plugin`中实现`*Command`类的Python脚本。

#### 存放位置

Sublime Text在下列位置寻找插件：

- `Packages`
- `Packages/`
- `.sublime-package` 文件

 `Packages` 中嵌套目录中的插件不会被加载。所有插件都应该放到`Packages`目录下其自己的文件夹中，不能直接放到`Packages`下。

#### 指令命名约定

带有`Command`的后缀，如：`NamesLikeThisCommand`。然而，指令名称会自动被转化成`name_like_this`。因此 `ExampleCommand` 会变成`example`， `AnotherExampleCommand` 会变成`another_example`。

#### 指令的类型

- `sublime_plugin.WindowCommand`
- `sublime_plugin.TextCommand`
- `sublime_plugin.EventListener`

 `WindowCommand` 实例必须有一个 `.window` 属性指向创建他们的窗口实例，类似的， `TextCommand` 必须有一个 `.view` 属性。

##### 命令的共同点

所有的命令都需要实现一个`.run()`函数才能正常运行，此外，它们可以接收任意多的关键字参数。

注意：命令的参数必须是有效的JSON值。

#### 通过API调用指令

根据不同指令的类型，使用`View`或`Window`的引用并调用`<object>.run_command('command_name')`。除了命令的名称外，`.run_command`接收一个字典参数。

```shell
window.run_command("echo", {"Tempus": "Irreparabile", "Fugit": "."})
```

#### 指令参数

所有用户提供的参数都必须是合法的JSON类型。

#### 文本指令和`edit`对象

文本指令接收一个`edit`对象，所有 `edit` 中完成的操作都会被分组为一个撤销操作。编辑完成时 `on_modified()`和`on_selection_modified()` 等回调函数会被调用。

和老版本不同，Sublime Text3不允许对`edit`对象进行编程控制，`edit`对象的生命周期由编辑器单独管理。API是负责管理其生命周期的。插件的作者必须确保新的文本命令中的所有的编辑都在`.run()`中，以便宏和代码段可以正常工作。

用 `run_command()` 函数可以从你自己的指令中调用其他指令。

#### 事件响应

任何从`EventListener`派生的命令都能够对事件作出响应。

#### 标准库

Sublime Text自带一个缩减版的标准库。

#### 自动重载插件

插件有变动时Sublime Text将会重新加载Python模块，但是Python的子包不会被自动加载，这在你开发插件时会造成困惑。插件的文件有变化时最好还是重启Sublime Text为好。

#### 多线程

只有 `set_timeout()` 函数可以安全地从不同的线程调用。

### Python API

[官方文档](http://www.sublimetext.com/docs/3/api_reference.html)

#### 官方文档中缺失的

官方文档中有些缺失，本章节就是尝试解决这个问题的。

##### 索引

- module [`sublime`](http://docs.sublimetext.info/en/latest/reference/api.html#module-sublime)
  - class [`Window`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime.Window)[`set_layout()`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime.Window.set_layout)
    - class [`View`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime.View)[`match_selector()`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime.View.match_selector)


- module [`sublime_plugin`](http://docs.sublimetext.info/en/latest/reference/api.html#module-sublime_plugin)
  - class [`EventListener`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime_plugin.EventListener)
    - [`on_query_completions()`](http://docs.sublimetext.info/en/latest/reference/api.html#sublime_plugin.EventListener.on_query_completions)

##### `sublime` 模块

- *class* **sublime.Window**

  表示Sublime Text中的窗口，并提供了一些方法与窗口进行交互。

  - set_layout (*layout*)

    更改视图组基于区块的面板布局。

    | Parameters: | **layout** (*dict*) – 指定新的布局 |
    | ----------- | ---------------------------- |
    | Returns:    | None                         |

    期望的字典如下：

    ```json
    {"cols": [float], "rows": [float], "cells": [[int]]}
    ```

     `[type]` 代表*type*的列表：

    **cols**

    列分隔符的列表，从0（左）到1（右）。

    **rows**

    行分隔符的列表，从0（上）到1（下）。

    **cells**

    格子列表，每项值表示格子的边界。如下：

    ```
    [x1, y1, x2, y2]
    ```

    每个值分别表示行列的索引，因此， `[0, 0, 1, 2]` 表示把一个单元格从左上角平移到第一列第二行的位置。

    注意：**行**和**列**没有进行过边界测试，也不会进行自动调整。因此，你可以指定比0小或比1大的值，Sublime Text会有相应的处理。这意味着你可以裁剪视图或创建边框。目前还不清楚这些空白空间的背景色（默认是黑色）是否可以被修改，使用的话后果自负😈。

    行列的顺序也没有被检查，所以如果你使用了一个类似 `[1, 0.5, 0]` 这样的值，你将会看到两个黑色的面板，Sublime Text在这种状态将不可用。

    示例：

    ```
    # A 2-column layout with a separator in the middle
    window.set_layout({
        "cols": [0, 0.5, 1],
        "rows": [0, 1],
        "cells": [[0, 0, 1, 1], [1, 0, 2, 1]]
    })
    ```

    ```
    # A 2x2 grid layout with all separators in the middle
    window.set_layout({
        "cols": [0, 0.5, 1],
        "rows": [0, 0.5, 1],
        "cells": [[0, 0, 1, 1], [1, 0, 2, 1],
                  [0, 1, 1, 2], [1, 1, 2, 2]]
    })
    ```

    ```
    # A 2-column layout with the separator in the middle and the right
    # column being split in half
    window.set_layout({
        "cols": [0, 0.5, 1],
        "rows": [0, 0.5, 1],
        "cells": [[0, 0, 1, 2], [1, 0, 2, 1],
                                [1, 1, 2, 2]]
    })
    ```


- *class* **sublime.View**

  和`Window`类似，表示Sublime Text中的视图，并提供了一些方法与窗口进行交互。

  - match_selector(*point*, *selector*)

    匹配指定`selector`下的`point`作用域。

    | Parameters:   | **point** (*int*) – 一个作用域选择器 |
    | ------------- | ---------------------------- |
    | Returns bool: | 是否匹配到                        |

    等价于：

    ```
    view.score_selector(point, selector) != 0
    # or
    sublime.score_selector(view.scope_name(point), selector) != 0
    ```

##### `sublime_plugin` 模块

- class **sublime_plugin.EventListener**

  - on_query_completions(*view*, *prefix*, *locations*)

    请求补全列表时调用。

    - view

      补全到的`view`实例。

    - prefix

      到目前为止输入的文字。

    - locations

       `view` 中补全将要插入的作用域的选择器列表。

      如果你想处理依赖于单词分隔符的补全，你需要单独测试每一个location。

    - Return value

      - `[[trigger, contents], ...]`

        和“基于选择器补全”类似，但是没有keys.trigger的映射，可以使用`\\t`描述语法的**列表**。

        **注意**：Sublime Text 3中，补全还可以包含纯文本，而不是触发内容列表。

      - `([[trigger, contents], ...], flags)`

        基本上和上面一种相同，第二个元素*flag*可能是这些标记的按位或的组合：

        - `sublime.INHIBIT_WORD_COMPLETIONS`

          所有插件都被处理后，阻止Sublime Text把它的单词添加到补全列表。

        - `sublime.INHIBIT_EXPLICIT_COMPLETIONS`

          这个是做啥的？

        所有补全中的标记都是共享的，一旦被某种插件设置过就无法恢复了。

      - 其它（例如`None`）

        没作用。

#### 探索API

快速查看API的方法：

1. 把 `Packages/Default` (**Preferences | Browse Packages…**) 添加到你的项目中
2. `Ctrl + Shift + F`
3. 在输入框中输入 `*.py` 
4. 开启 `Use Buffer`选项
5. 搜索API名称
6. `F4`
7. 学习相关的源代码

### 指令
### Windows/Linux键盘快捷键

#### 编辑

⚠️本文只是一个草稿也许包含错误的信息。

| Keypress     | Command                |
| ------------ | ---------------------- |
| Ctrl + X     | 剪切当前行                  |
| Ctrl + ↩     | 在后面插入一行                |
| Ctrl + ⇧ + ↩ | 在前面插入一行                |
| Ctrl + ⇧ + ↑ | 向上移动行/区块               |
| Ctrl + ⇧ + ↓ | 向下移动行/区块               |
| Ctrl + L     | 选中行-重复按下以选择后面的行        |
| Ctrl + D     | 选择单词-重复按下以选择相同的单词      |
| Ctrl + M     | 跳转到括号的结尾，重复按下跳转到括号的开头。 |
| Ctrl + ⇧ + M | 选择当前括号中的所有内容           |
| Ctrl + ⇧ + K | 删除行                    |
| Ctrl + KK    | 删除光标到行尾的内容             |
| Ctrl + K + ⌫ | 删除光标到行首的内容             |
| Ctrl + ]     | 缩进当前行                  |
| Ctrl + [     | 向前缩进当前行                |
| Ctrl + ⇧ + D | 重复行                    |
| Ctrl + J     | 把当前行下面的一行追加到当前行尾       |
| Ctrl + /     | 添加/取消当前行的注释            |
| Ctrl + ⇧ + / | 块级注释                   |
| Ctrl + Y     | 重做，或重复上一次键盘快捷键         |
| Ctrl + ⇧ + V | 粘贴并正确地缩进               |
| Ctrl + Space | 选择下一个自动补全的建议           |
| Ctrl + U     | 撤销                     |
| Alt + ⇧ + W  | 把选择的块用html标签包起来        |
| Alt + .      | 关闭当前html标签             |

##### Window

| Ctrl + Alt + Up   | 向上选择行 |
| ----------------- | ----- |
| Ctrl + Alt + Down | 向下选择行 |

##### Linux

| Alt + ⇧ + Up   | 向上选择行 |
| -------------- | ----- |
| Alt + ⇧ + Down | 向下选择行 |

#### 导航

| Keypress | Command     |
| -------- | ----------- |
| Ctrl + P | 根据文件名快速打开文件 |
| Ctrl + R | 跳转到符号       |
| Ctrl + ; | 跳转到当前文件中的单词 |
| Ctrl + G | 跳转到当前文件中的行  |

#### 通用

| Keypress           | Command   |
| ------------------ | --------- |
| Ctrl + ⇧ + P       | 打开命令面板    |
| Ctrl + KB          | 切换侧边栏的显示  |
| Ctrl + ⇧ + Alt + P | 在状态栏显示作用域 |

#### 查找、替换

| Keypress     | Command |
| ------------ | ------- |
| Ctrl + F     | 查找      |
| Ctrl + H     | 替换      |
| Ctrl + ⇧ + F | 在文件中查找  |

#### Tab标签

| Keypress     | Command     |
| ------------ | ----------- |
| Ctrl + ⇧ + t | 打开上一次关闭的标签  |
| Ctrl + PgUp  | 在tab中向上循环   |
| Ctrl + PgDn  | 在tab中向下循环   |
| Ctrl + ⇆     | 在文件中查找      |
| Ctrl + W     | 关闭当前标签      |
| Alt + [NUM]  | 切换到第NUM个tab |

#### 分割窗口

| Keypress         | Command        |
| ---------------- | -------------- |
| Alt + ⇧ + 1      | 恢复视图为1列        |
| Alt + ⇧ + 2      | 将视图变成2列        |
| Alt + ⇧ + 3      | 将视图变成3列        |
| Alt + ⇧ + 4      | 将视图变成4列        |
| Alt + ⇧ + 5      | 把视图变成网格（4块）    |
| Alt + ⇧ + 8      | 把视图变成2行        |
| Ctrl + [NUM]     | 调到第1-4块区域      |
| Ctrl + ⇧ + [NUM] | 把文件移到指定第1-4块区域 |

#### 标记

| Keypress      | Command |
| ------------- | ------- |
| Ctrl + F2     | 切换标记的显示 |
| F2            | 下一个标记   |
| ⇧ + F2        | 上一个标记   |
| Ctrl + ⇧ + F2 | 清除标记    |

#### 文本操作

| Keypress  | Command |
| --------- | ------- |
| Ctrl + KU | 转换成大写   |
| Ctrl + KL | 转换成小写   |

### OSX键盘快捷键

#### 编辑

| Keypress         | Command                        |
| ---------------- | ------------------------------ |
| ⌘ + X            | 剪切行                            |
| ⌘ + ↩            | 在后面插入行                         |
| ⌘ + ⇧ + ↩        | 在之前插入行                         |
| ⌘ + ⌃ + ↑        | 向上移动行/区块                       |
| ⌘ + ⌃ + ↓        | 向下移动行/区块                       |
| ⌘ + L            | 选中行，重复按下可连续选择多行                |
| ⌘ + D            | 选中单词，连续按下可选择重复的单词              |
| ⌃ + ⌘ + G        | 在当前部分选中所有出现的                   |
| ⌃ + ⇧ + ↑        | Extra cursor on the line above |
| ⌃ + ⇧ + ↓        | Extra cursor on the line below |
| ⌃ + M            | 跳转到括号结束的地方，重复按下可跳转到括号开始的地方     |
| ⌃ + ⇧ + M        | 选择当前括号内的所有内容                   |
| ⌃ + A, ⌘ + Left  | 跳转到行首                          |
| ⌃ + E, ⌘ + Right | 跳转到行尾                          |
| ⌘ + K, ⌘ + K     | 删除光标到行尾的内容                     |
| ⌘ + K + ⌫        | 删除光标到行首的内容                     |
| ⌘ + ]            | 缩进                             |
| ⌘ + [            | 向前缩进                           |
| ⌘ + ⇧ + D        | 重复行                            |
| ⌘ + J            | 把当前行的下一行追加到行尾                  |
| ⌘ + /            | 单行注释                           |
| ⌘ + ⌥ + /        | 块级注释                           |
| ⌘ + Y            | 重做                             |
| ⌘ + ⇧ + V        | 粘贴并使用正确的缩进                     |
| ⌃ + Space        | 选择下一个自动补全的建议                   |
| ⌃ + U            | 撤销                             |
| ⌃ + ⇧ + Up       | 向上选择行                          |
| ⌃ + ⇧ + Down     | 向下选择行                          |
| ⌃ + ⇧ + W        | 把选中文字用HTML标签包起来                |
| ⌃ + ⇧ + K        | 删除光标所在行                        |

#### 导航

| Keypress       | Command     |
| -------------- | ----------- |
| ⌘ + P or ⌘ + T | 根据文件名快速打开文件 |
| ⌘ + R          | 跳转到符号       |
| ⌃ + G          | 跳转到当前文件的行   |

#### 通用

| Keypress      | Command   |
| ------------- | --------- |
| ⌘ + ⇧ + P     | 命令面板      |
| ⌃ + `         | Python控制台 |
| ⌃ + ⌘ + F     | 切换到全屏模式   |
| ⌃ + ⇧ + ⌘ + F | 切换到免打扰模式  |
| ⌘ + K, ⌘ + B  | 切换侧边栏     |
| ⌃ + ⇧ + P     | 在状态栏显示作用域 |

#### 查找、替换

| Keypress  | Command |
| --------- | ------- |
| ⌘ + F     | 查找      |
| ⌘ + ⌥ + F | 替换      |
| ⌘ + ⇧ + F | 在文件中查找  |

#### 滚动

| Keypress | Command     |
| -------- | ----------- |
| ⌃ + V    | 向下滚动一页      |
| ⌃ + L    | 把当前行定位到视图中间 |
| ⌘ + Down | 跳转到文件结尾     |
| ⌘ + Up   | 跳转到文件开始     |

#### Tab标签

| Keypress    | Command     |
| ----------- | ----------- |
| ⌘ + ⇧ + t   | 打开上一次关闭的标签  |
| ⌘ + ⇧ + [   | 在tab中向上循环   |
| ⌘ + ⇧ + ]   | 在tab中向下循环   |
| ^ + Tab     | 在最近tab中向上循环 |
| ⇧ + ^ + Tab | 在最近tab中向下循环 |
| ⌘ + [NUM]   | 切换到第NUM个tab |

#### 分割窗口

| Keypress      | Command        |
| ------------- | -------------- |
| ⌘ + ⌥ + 1     | 恢复视图为1列        |
| ⌘ + ⌥ + 2     | 将视图变成2列        |
| ⌘ + ⌥ + 3     | 将视图变成3列        |
| ⌘ + ⌥ + 4     | 将视图变成4列        |
| ⌘ + ⌥ + 5     | 把视图变成网格（4块）    |
| ⌘ + ⌥ + 8     | 把视图变成2行        |
| ⌃ + [NUM]     | 调到第1-4块区域      |
| ⌃ + ⇧ + [NUM] | 把文件移到指定第1-4块区域 |

#### 标记

| Keypress   | Command |
| ---------- | ------- |
| ⌘ + F2     | 切换标记的显示 |
| F2         | 下一个标记   |
| ⇧ + F2     | 上一个标记   |
| ⇧ + ⌘ + F2 | 清除标记    |

#### 文本操作

| Keypress                 | Command   |
| ------------------------ | --------- |
| ⌘ + K, ⌘ + U             | 转换成大写     |
| ⌘ + K, ⌘ + L             | 转换成小写     |
| ⌘ + ⌃ + up, ⌘ + ⌃ + down | 向上/向下剪辑文本 |

[返回目录](#目录)

## 词汇表

**buffer**

与一个或多个视图相关联的已加载文件的数据及其额外的元数据，*buffer*和*view*的区别在于技术性，大多数时候这两个何以互换使用。

**view**

一个*buffer*的图形显示，多个视图可以同时显示一个buffer。

**plugin**

用Python实现的一个可以包含单一指令或多个指令的功能，可以包含在一个*.py*或多个*.py*文件中。

**package**

这个术语在Sublime Text中有着不同的含义，它既可表示一个Python包，还可以表示`Packages`中的文件夹，或是一个*.sublime-package*文件。大多数时候表示`Packages`中的文件夹。

**panel**

一个输入/输出部件，如搜索面板和输出面板。

**overlay**

一种特殊的输入部件，如“跳转到”就是一个overlay。

**file type**

在Sublime Text中，*file type*指`.tmLanguage`中确定的语法定义的文件类型。然而，这也是有点歧义的，在某些情况下，也可以在技术文本中使用

[返回目录](#目录)
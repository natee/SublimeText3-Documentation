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

## 无干扰模式

## VI模式

## 项目




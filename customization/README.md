## 设置

### 概述

Sublime Text有很多设置可以定制化它的行为，通过编辑文件尽心设置的修改：这个和图形和界面不太一样，但由此你可以得到一个非常灵活的系统。

### 设置

通过菜单栏的**Preferences/Settings - Default**访问`Packages/Default/Preferences.sublime-settings`查看有哪些设置选项及其描述。

找到你想修改的项时，把它们添加到*用户设置*（Preferences/Settings - User）中，这样在软件升级时将会保留设置。

#### 设置文件

设置文件按以下顺序被调用：

1. Packages/Default/Preferences.sublime-settings
2. Packages/Default/Preferences (<platform>).sublime-settings
3. **Packages/User/Preferences.sublime-settings**
4. <Project Settings>
5. Packages/<syntax>/<syntax>.sublime-settings
6. **Packages/User/.sublime-settings**
7. <Buffer Specific Settings>

一般来说，你应该把设置放到`Packages/User/Preferences.sublime-settings`中，如果你想给特定文件类型指定一些设置，如Python，你应该把设置放到`Packages/User/Python.sublime-settings`中。

#### 示例

把下面的文件保存为`Packages/User/Preferences.sublime-settings`：

```json
{
    "tab_size": 4,
    "translate_tabs_to_spaces": false
}
```

#### Per-syntax设置

这种类型的设置是基于每一种语法来定的，常见的用途是不同的文件类型有不同的缩进和配色方案。

你可以通过菜单栏的**Preferences/Settings - More/Syntax Specific - User**编辑当前语法的设置。

#### Per-project设置

按项目进行设置。

#### 无干扰设置

无干扰模式有一个特殊的设置文件（`Distraction Free.sublime-settings`）。通过菜单栏的**Preferences/Settings - More/Distraction Free - User**进行修改。

#### 修改设置绑定到按键

`toggle_setting`指令用来切换一个设置项。如，把`word_wrap`绑定到一个按键，你可以使用（Preferences/Key Bindings - User）：

```json
{
    "keys": ["alt+w"],
    "command": "toggle_setting",
    "args":
    {
        "setting": "word_wrap"
    }
}
```

下面这个`set_setting`指令会设置`setting`为一个指定的值。如，当前的设置让当前文件使用Cobalt这种配色方案。

```json
{
    "keys": ["ctrl+k", "ctrl+c"],
    "command": "set_setting",
    "args":
    {
        "setting": "color_scheme",
        "value": "Packages/Color Scheme - Default/Cobalt.tmTheme"
    }
}
```

这里设置的文件都是针对特定文件的：它可以覆盖设置文件中的任何配置，但是仅对当前文件生效。

#### 故障诊断

由于可以在很多地方进行设置，有时候查看当前文件中实际在使用的设置是非常有帮助的，你可以通过控制台：

```shell
view.settings().get('font_face')
```



## 字体

### 概述

把下面这些内容加入到**Preferences/Settings - User**中即可改变字体

```
"font_face": "Courier New",
"font_size": 10
```

保存时设置即生效。



## 缩进

### 概述

缩进设置决定一个tab表示多少个空格，并控制tab键是控制输入tab还是空格。除了自动检测外，还可以全局定制、按文件类型定制或按单文件定制。

### 设置

| tab_size                 | 数值类型，一个tab等价于几个空格                        |
| ------------------------ | ---------------------------------------- |
| translate_tabs_to_spaces | 布尔类型，把tab转成空格，也就是说按下tab键会输入tab_size规定个数的空格。 |
| detect_indentation       | 布尔类型，默认为true，加载文件时会自动检测用tab还是空格对文件进行缩进。  |
| use_tab_stops            | 布尔类型，如果translate_tabs_to_spaces值为true，use_tab_stops将使按下tab或回退键时插入或删除直接到下一个tab位。 |

**设置文件**

设置文件按以下顺序被调用：

1. Packages/Default/Preferences.sublime-settings
2. Packages/Default/Preferences (<platform>).sublime-settings
3. **Packages/User/Preferences.sublime-settings**
4. Packages/<syntax>/<syntax>.sublime-settings
5. **Packages/User/.sublime-settings**

一般来说，你应该把设置放到`Packages/User/Preferences.sublime-settings`中，如果你想给特定文件类型指定一些设置，如Python，你应该把设置放到`Packages/User/Python.sublime-settings`中。

**示例**

```json
{
    "tab_size": 4,
    "translate_tabs_to_spaces": false
}
```

**Per-syntax设置**

这种类型的设置是基于每一种语法来定的，常见的用途是不同的文件类型有不同的缩进和配色方案。

你可以通过菜单栏的**Preferences/Settings - More/Syntax Specific - User**编辑当前语法的设置。

### 缩进检测

当一个文件加载时，它的内容就会被检测，`tab_size`和`translate_tabs_to_spaces`就会被设置。状态区域将显示这个何时发生，一般情况这都能正常工作，你可以通过设置`detect_indentation`来禁用它。

可以通过**View/Indentation/Guess Settings**手动运行缩进检测。

### Tab和空格的转换

菜单栏中**View/Indentation**有一些指令来进行各种转化，他们将运行`expand_tabs`和`unexpand_tabs`指令。

### 自动缩进

自动缩进将检测前面的缩进以便按下回车键时可以正常缩进，它由以下设置控制：

| auto_indent                | 布尔值，默认true，启用自动缩进。                       |
| -------------------------- | ---------------------------------------- |
| smart_indent               | 布尔值，默认true，使自动缩进更加智能。如：在C语言中的if语句下一行进行缩进。 |
| trim_automatic_white_space | 布尔值，默认true，删除自动缩进添加的空白符。                 |
| indent_to_bracket          | 布尔值，默认false，缩进时自动缩进到第一个开括号的位置，如下         |

```
use_indent_to_bracket(to_indent,
                      like_this);
```



## 拼写检查

### 概述

Sublime Text使用[Hunspell](http://hunspell.sourceforge.net/)来进行拼写检查，可以从[OpenOffice.org Extension List](http://extensions.services.openoffice.org/en/dictionaries)获取额外的字典。

Sublime Text可用字典：[https://github.com/SublimeText/Dictionaries](https://github.com/SublimeText/Dictionaries)

### 字典

Sublime Text目前只支持UTF-8编码格式的字典，大多数字典并没有使用UTF-8字典，而是使用了和其语言相关的编码格式，为了正常使用Sublime Text字典，首先得把编码格式转成UTF-8。

一旦你有了一个UTF-8编码格式的字典，把它放到一个package中就算是安装了，例如，放到*Packages/User*，可以通过菜单栏的**Preferences/Browse Packages**访问。文件放到位后，就可以从菜单栏的**View/Dictionary**选择这个字典。

### 设置

有两种影响拼写检查的设置，`spell_check`：控制是否启用拼写检查。`dictionary`：字典的路径。例：

```
"spell_check": true,
"dictionary": "Packages/Language - English/en_US.dic"
```

已添加的已忽略的单词分别存储在用户设置中的`added_words`和`ignored_words`中。

### 指令

- next_misspelling：选择下一个拼错
- prev_misspelling：选择上一个拼错
- add_word：把通过`word`参数指定的单词添加到add列表
- ignore_word：把通过`word`参数指定的单词添加到ignore列表

## 包

### 概述

包是Sublime Text中使用的资源文件的集合：插件、语法高亮定义、菜单、代码段及其他更多。Sublime Text自带了一些包，还有很多其他用户创建的包。

包存储在*.sublime-package*文件（一个不同的扩展名的*zip*文件）中，也可以存储为一个目录下的未压缩的文件，或是二者的混合形式：package下的任何未压缩的文件都会覆盖存储在*.sublime-package*文件中的文件。

### 位置

压缩的包可以存储在：
- `<executable_path>/Packages`
- `<data_path>/Installed Packages`

未压缩的包可以存储在：

- `<data_path>/Packages`

例如，`Python`包存储在`<executable_path>/Packages/Python.sublime-package`中，任何在`<data_path>/Packages/Python`中的文件都会覆盖存储在`.sublime-package`文件中的文件。

### 特殊包

有两种特殊的包：`Default`和`User.Default`永远会在第一位加载，`User`永远在最后被加载。包的顺序在进行包合并时会体现出来，如：`Main.sublime-menu`，任何包都可以包含一个`Main.sublime-menu`文件，然而这并不会覆盖主菜单，只会依据包的加载顺序进行合并。

除了`Default`和`User.Default`之外的包是按字母顺序进行排序的。

### 创建新的包

在`<data_path>/Installed Packages`下新建一个目录即可创建一个包，通过菜单栏的**Preferences/Browse Packages**可以访问这个目录。

### 覆盖Zipped Package中的文件

覆盖一个存在的包中的文件，在`Packages/<Package Name>`目录下创建一个同名文件。

为了覆盖Sublime Text自带的包` Python.sublime-package`中的`function.sublime-snippet`文件，在`<data_path>/Packages`目录下新建一个字典命名为`Python`，然后把你的`function.sublime-snippet`文件放到那里。


## 语法
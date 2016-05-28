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


# 语法

Sublime Text可以使用`.sublime-syntax`和`.tmLanguage`文件进行语法高亮，本文介绍`.sublime-syntax`文件。

### 概述

Sublime语法文件是 [YAML](http://yaml.org/)，此文件有一个小的头部，紧跟一个上下文列表。每个上下文都有一个匹配模式的列表，这个列表描述了在这个上下文中如何高亮文本、如何改变当前文本。

这里有一个高亮C语言语法的示例：

```
%YAML 1.2
---
name: C
file_extensions: [c, h]
scope: source.c

contexts:
  main:
    - match: \b(if|else|for|while)\b
      scope: keyword.control.c

```

核心是一个语法定义，把作用域安排给文本区域，这个作用域由配色方案使用来对文本进行高亮。

这个语法文件包含一个context，main，匹配到[if, else, for, while]等单词时，就会把它们放进`keyword.control.c`的作用域。每个语法都必须定义一个main上下文，这会最先被使用。

是正则表达式，使用了[Ruby](http://www.geocities.jp/kosako3/oniguruma/doc/RE.txt) 语法。上面的例子中，`\b`用来确保单词的边界被匹配上，其他位置的这些词不会被作为关键词。

注意：由于YAML语法，` .sublime-syntax`文件中不允许有tab字符。

## Header

header区域允许的key有：

- **name**. 菜单栏中语法的名称。可选，如果没有时将会从文件名中提取。
- **file_extensions**.一个字符串列表，定义使用这种语法高亮的文件的扩展名。
- **first_line_match**. 当打开一个未识别的文件时，文件的第一行内容将会通过这个正则表达式去识别，从而判断是否应该应用这个语法高亮。
- **scope**. 文件中全部文本的默认作用域。
- **hidden**. 菜单栏中不会显示隐藏的语法定义，但仍然可以被插件使用，或是包含在其它语法定义中。

## Contexts

对于大多数语言来说，你可能需要不止一种context。如，C语言中，我们不需要一个字符串中间被匹配到的单词有关键词的语法高亮。这里有个例子：

```
%YAML 1.2
---
name: C
file_extensions: [c, h]
scope: source.c

contexts:
  main:
    - match: \b(if|else|for|while)\b
      scope: keyword.control.c
    - match: '"'
      push: string

  string:
    - meta_scope: string.quoted.double.c
    - match: \\.
      scope: constant.character.escape.c
    - match: '"'
      pop: true

```

`main`上下文中第二个匹配项是一个双引号（注意"必须是'"'这样的，单独一个双引号会报YAL语法错误），添加一个字符串上下文到context的堆中。这就意味着这个文件的余下部分将使用`contexts`中的`string`来处理，而不是`main`，直到`string`从堆中被移除。

`string`上下文介绍了一个新的模式：`meta_scope`，档`string`上下文在堆中时，这会把`string.quoted.double.c`作用域分配给文本。

在Sublime Text中编辑时，你可以通过按下`ctrl+shift+p`（OS X）或`ctrl+alt+shift+p`（Windows和Linux）来查看光标选中的文本应用的作用域。

`string`有两个匹配项：第一个是反斜杠字符跟一个任意字符，第二个是一个双引号字符。注意最后一个匹配项指定了一个行为：当遇到转义引号时，`string`将被从context堆栈中移除，然后重新去使用`main`中的作用域。

当一个context有多个匹配项，最左边的一个将被发现。当同一位置匹配到多个模式时，将会应用第一个定义的模式。

### Meta模式

- **meta_scope**. 这把给定的作用域分配给这个上下文中的所有文本，包括把context添加到堆栈或从中移除的patterns。
- **meta_content_scope**. 和上面一样，但是不应用于触发此context的文本（如，上面的`string`例子中，当前作用域不会应用于引号字符）。
- **meta_include_prototype**. 用来阻止当前context自动包含原型context。

Meta模式必须放在contexts中的第一位。

### Match模式

match模式允许有如下key：

- **match**. 正则表达式。YAML允许很多字符串不带双引号，这可以使正则表达式更清晰，但你仍然需要知道何时把正则表达式用引号包起来。如果你的正则表达式包含了`#`、`:`、`-`、`{`、`[`或`>`等字符，这时你就需要用到引号了。正则表达式同一时间只能对单行文本生效。
- **scope**. 安排给匹配到的文本的作用域。
- **captures**. 一个数字到作用域的映射，给正则表达式匹配到的部分分配作用域。
- **push**. 追加到contexts堆栈中的context，这可以是一个context名称、context名称列表或是一个行内、匿名的context。
- **pop**. 把当前上下文从contexts堆栈中移除，这个key唯一可被接收的值是`true`。
- **set**. 和`push`接收同样的参数，但是首先会把这个context移除，然后才把给定的context添加到堆栈中。
- **syntax**. 看下面的[包含其它文件](##包含其它文件)。

注意：push、pop、set和syntax都是独立的，一个单独的匹配模式中只能使用其中的一个。

这个例子中，正则表达式包含了两个捕获，捕获的key用来给每一个分配不同的作用域。

```
- match: "^\\s*(#)\\s*\\b(include)\\b"
  captures:
    1: meta.preprocessor.c++
    2: keyword.control.include.c++

```

### Include模式

便于在一个context中包含另外一个。例如，你可以定义多种不同的context来解析C语言，它们几乎都可以包含`comments`。你可以包含他们，而不是在每个context中复制一份：

```
expr:
  - include: comments
  - match: \b[0-9]+\b
    scope: constant.numeric.c
  ...
```

这里，所有的match匹配项和include模式都将被拉取，它们将在include模式的位置被插入，因此你仍然可以控制模式的顺序。所有定义在comments上下文中的meta模式都将被忽视。

当有一个元素，如`comments`时，这个被包含简直太常见了，对每一个context自动包含这个是很简单的，只需要列出异常。你可以创建一个context明明的原型，这将会自动被包含到每一个其它context的顶部，除非context使用了`meta_include_prototype`meta模式。例如：

```
prototype:
  - include: comments

string:
  - meta_include_prototype: false
  ...

```

C语言中，字符串中的`/*`不会作为注释的开始，因此`string`context表明原型不应该被包含。

## 包含其它文件

Sublime语法文件支持在一个语法定义中嵌入另一个，如，HTML可以嵌入JavaScript。这里有一个HTML的基本语法定义的例子：

```
scope: text.html

contexts:
  main:
    - match: <script>
      push: Packages/JavaScript/JavaScript.sublime-syntax
      with_prototype:
        - match: (?=</script>)
          pop: true
    - match: "<"
      scope: punctuation.definition.tag.begin
    - match: ">"
      scope: punctuation.definition.tag.end

```

注意上面的第一条规则，它表明了当遇到`<script>`标签时，`JavaScript.sublime-syntax`将被push到context的堆栈中。它还定义了另外一个key`with_prototype`。包含了一个将被插入到每一个`JavaScript.sublime-syntax`中定义的context中的匹配项列表。注意`with_prototype`在概念上和`prototype`上下文类似，然而它将始终被插入到每一个被引用的上下文，无需考虑`meta_include_prototype`设置。

这个例子中，当下一个标签是`</script>`时，插入的patter会被从当前context中移除。注意这并不是真正匹配`</script>`标签，只是使用了一个在这里扮演了两个角色的预判：既允许HTML规则匹配结束标签，按照正常方式高亮，保证JavaScript上下文可以被移出。上下文堆栈也许在JavaScript字符串中间，例如，一旦遇到`</script>`标签，JavaScript字符和`main`context都将被移出。

注意：不能把`.tmLanguage`文件包含到` .sublime-syntax`文件中。

一种常见的情景是包含HTML的模板语言，这里有一个例子：

```
scope: text.jinja
contexts:
  main:
    - match: ""
      push: "Packages/HTML/HTML.sublime-syntax"
      with_prototype:
        - match: "{{"
          push: expr

  expr:
    - match: "}}"
      pop: true
    - match: \b(if|else)\b
      scope: keyword.control

```

这个和HTML嵌套JavaScript的例子大不一样，因为模板语言往往是从内到外进行操作：默认情况，它需要像HTML一样，只有转码成特定表达式的底层模板语言。

上面的例子，我们可以看到它默认以HTML模式运行：`main`上下文包含一个单独的永远被匹配到的模式，只包含了HTML语法。

## 变量

几个正则表达式有共同部分并不罕见，你可以使用变量来避免重复输入：

```
variables:
  ident: '[A-Za-z_][A-Za-z_0-9]*'
contexts:
  main:
    - match: '\b{{ident}}\b'
      scope: keyword.control

```

变量必须定义在`.sublime-syntax`文件的顶部，在正则表达式中通过`{{varname}}`的形式来引用，变量本身可以引用其它变量。注意任何不匹配`{{[A-Za-z0-9_]+}}`的文本将不会被认为是一个变量，因此正则表达式仍然可以包含常量`{{`字符。

## 示例

### 括号平衡

这个例子高亮没有对应的开括号的闭合括号：

```
name: C
scope: source.c

contexts:
  main:
    - match: \(
      push: brackets
    - match: \)
      scope: invalid.illegal.stray-bracket-end

  brackets:
    - match: \)
      pop: true
    - include: main

```

### 连续的context

这个例子将高亮包含很多分号的C语言风格的`for`语句：

```
for_stmt:
  - match: \(
    set: for_stmt_expr1
for_stmt_expr1:
  - match: ";"
    set: for_stmt_expr2
  - match: \)
    pop: true
  - include: expr
for_stmt_expr2:
  - match: ";"
    set: for_stmt_expr3
  - match: \)
    pop: true
  - include: expr
for_stmt_expr3:
  - match: \)
    pop: true
  - match: ";"
    scope: invalid.illegal.stray-semi-colon
  - include: expr

```

### 高级堆栈的使用

C语言中，符号通常是和一个`typedef`关键词一起定义的。符号有一个附加到它的`entity.name.typescope`。

这样做事带有一点取巧，因为虽然类型定义很简单，但你也可以把它玩的很复杂。

```
typedef int coordinate_t;

typedef struct
{
    int x;
    int y;
} point_t;

```

认识到这些，当匹配到`typoedef`关键词后，两个context会被添加到堆栈中：第一个将识别`typename`，然后移出；第二个将识别这个类型介绍的名称：

```
main:
  - match: \btypedef\b
    scope: keyword.control.c
    set: [typedef_after_typename, typename]

typename:
  - match: \bstruct\b
    set:
      - match: "{"
        set:
          - match: "}"
            pop: true
  - match: \b[A-Za-z_][A-Za-z_0-9]*\b
    pop: true

typedef_after_typename:
  - match: \b[A-Za-z_][A-Za-z_0-9]*\b
    scope: entity.name.type
    pop: true

```

上面的例子中，`typename`是一个可复用的context，它将在`typename`中读取然后在完成时从堆栈中移出。它可以在任意上下文中使用，如：typedef中，或作为一个函数的参数。

### PHP Heredocs

这个例子展示了如何匹配PHP中的[Heredocs](http://php.net/language.types.string#language.types.string.syntax.heredoc)。`main`context中的`match`捕获heredoc的识别符，`heredoc`context中相应的`pop`指的是捕获到的文本中有`\1`的。

```
name: PHP
scope: source.php

contexts:
  main:
    - match: <<<([A-Za-z][A-Za-z0-9_]*)
      push: heredoc

  heredoc:
    - meta_scope: string.unquoted.heredoc
    - match: ^\1;
        pop: true
```

## Testing

当构建了一个语法定义，你可以定义一个语法测试文件来帮你检测作用域，而不是手动通过`show_scope_name`指令进行检测。

```
// SYNTAX TEST "Packages/C/C.sublime-syntax"
#pragma once
// <- source.c meta.preprocessor.c++
 // <- keyword.control.import

// foo
// ^ source.c comment.line
// <- punctuation.definition.comment

/* foo */
// ^ source.c comment.block
// <- punctuation.definition.comment.begin
//     ^ punctuation.definition.comment.end

#include "stdio.h"
// <- meta.preprocessor.include.c++
//       ^ meta string punctuation.definition.string.begin
//               ^ meta string punctuation.definition.string.end
int square(int x)
// <- storage.type
//  ^ meta.function entity.name.function
//         ^ storage.type
{
    return x * x;
//  ^^^^^^ keyword.control
}

"Hello, World! // not a comment";
// ^ string.quoted.double
//                  ^ string.quoted.double - comment
```

遵循以下规则：

1. 确保文件名以"syntax_test"开头。
2. 确保文件存储在`Packages`目录下的某个地方：推荐和相应的`.sublime-syntax`文件放在一起。
3. 确保文件第一行以` <comment_token> SYNTAX TEST "<syntax_file>"`开头。注意语法文件可以是` .sublime-syntax`或`.tmLanguage`文件。

一但上述要求都满足了，运行build指令就可以在输出面板看到结果。*下一个结果*（F4）可以用来导航到第一个失败的测试。

语法测试文件中的每一个测试必须首先以注释标记开头，然后才是`^`或`<-`标记。

这两种类型的测试分别是：

- 尖号：`^`将测试针对最近一次的非测试行的作用域选择器，它将测试和`^`所在列。连续的`^`将测试选择器对应的每一列。
- 箭头：`<-` 将测试针对最近一次的非测试行的作用域选择器，它将测试注释字符所在的列。


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

### Meta Patterns

- **meta_scope**. This assigns the given scope to all text within this context, including the patterns that push the context onto the stack and pop it off.
- **meta_content_scope**. As above, but does not apply to the text that triggers the context (e.g., in the above string example, the content scope would not get applied to the quote characters).
- **meta_include_prototype**. Used to stop the current context from automatically including the prototype context.

Meta patterns must be listed first in the context, before any match or include patterns.

### Match Patterns

A match pattern can include the following keys:

- **match**. The [regex](http://www.geocities.jp/kosako3/oniguruma/doc/RE.txt) used to match against the text. YAML allows many strings to be written without quotes, which can help make the regex clearer, but it's important to understand when you need to quote the regex. If your regex includes the characters #, :, -, {, [ or > then you likely need to quote it. Regexes are only ever run against a single line of text at a time.
- **scope**. The scope assigned to the matched text.
- **captures**. A mapping of numbers to scope, assigning scopes to captured portions of the match regex. See below for an example.
- **push**. The contexts to push onto the stack. This may be either a single context name, a list of context names, or an inline, anonymous context.
- **pop**. Pops the current context off the stack. The only accepted value for this key is true.
- **set**. Accepts the same arguments as push, but will first pop this context off, and then push the given context(s) onto the stack.
- **syntax**. See [Including Other Files](https://www.sublimetext.com/docs/3/syntax.html#include-syntax), below

Note that the actions: push, pop, set, and syntax are exclusive, and only one of them may be used within a single match pattern.

In this example, the regex includes two captures, and the captures key is used to assign each one a different scope:

```
- match: "^\\s*(#)\\s*\\b(include)\\b"
  captures:
    1: meta.preprocessor.c++
    2: keyword.control.include.c++

```

### Include Patterns

Frequently it's convenient to include the contents of one context within another. For example, you may define several different contexts for parsing the C language, and almost all of them can include comments. Rather than copying the relevant match patterns into each of these contexts, you can include them:

```
expr:
  - include: comments
  - match: \b[0-9]+\b
    scope: constant.numeric.c
  ...

```

Here, all the match patterns and include patterns defined in the comments context will be pulled in. They'll be inserted at the position of the include pattern, so you can still control the pattern order. Any meta patterns defined in the comments context will be ignored.

With elements such as comments, it's so common to include them that it's simpler to make them included automatically in every context, and just list the exceptions instead. You can do this by creating a context named prototype, it will be included automatically at the top of every other context, unless the context uses the meta_include_prototype meta pattern. For example:

```
prototype:
  - include: comments

string:
  - meta_include_prototype: false
  ...

```

In C, a /* inside a string does not start a comment, so the string context indicates that the prototype should not be included.

## Including Other Files

Sublime Syntax files support the notion of one syntax definition embedding another. For example, HTML can contain embedded JavaScript. Here's an example of a basic syntax defintion for HTML that does so:

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

Note the first rule above. It indicates that when we encounter a <script> tag, the main context within JavaScript.sublime-syntax should be pushed onto the context stack. It also defines another key, with_prototype. This contains a list of patterns that will be inserted into every context defined within JavaScript.sublime-syntax. Note that with_prototype is conceptually similar to the prototype context, however it will be always be inserted into every referenced context irrespective of their meta_include_prototype setting.

In this case, the pattern that's inserted will pop off the current context while the next text is a </script> tag. Note that it doesn't actually match the </script> tag, it's just using a lookahead assertion, which plays two key roles here: It both allows the HTML rules to match against the end tag, highlighting it as-per normal, and it will ensure that all the JavaScript contexts will get poped off. The context stack may be in the middle of a JavaScript string, for example, but when the </script> is encoutered, both the JavaScript string and main contexts will get poped off.

Note that while Sublime Text supports both .sublime-syntax and .tmLanguage files, it's not possible to include a .tmLanguage file within a .sublime-syntax one.

Another common scenario is a templating language including HTML. Here's an example of that, this time with a subset of [Jinja](http://jinja.pocoo.org/):

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

This is quite different from the HTML-embedding-JavaScript example, because templating languages tend to operate from the inside out: by default, it needs to act as HTML, only escaping to the underlying templating language on certain expressions.

In the example above, we can see it operates in HTML mode by default: the main context includes a single pattern that always matches, consuming no text, just including the HTML syntax.

Where the HTML syntax is included, the Jinja syntax directives ("{{ ... }}" ) are included via the with_prototype key, and thus get injected into every context in the HTML syntax (and JavaScript, by transitivity).

## Variables

It's not uncommon for several regexes to have parts in common. To avoid repetitious typing, you can use variables:

```
variables:
  ident: '[A-Za-z_][A-Za-z_0-9]*'
contexts:
  main:
    - match: '\b{{ident}}\b'
      scope: keyword.control

```

Variables must be defined at the top level of the .sublime-syntax file, and are referenced within regxes via {{varname}}. Variables may themselves include other variables. Note that any text that doesn't match {{[A-Za-z0-9_]+}} won't be considered as a variable, so regexes can still include literal{{ characers, for example.

## Selected Examples

### Bracket Balancing

This example highlights closing brackets without a corresponding open bracket:

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

### Sequential Contexts

This example will highlight a C style for statement containing too many semicolons:

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

### Advanced Stack Usage

In C, symbols are often defined with the typedef keyword. So that *Goto Definition* can pick these up, the symbols should have the entity.name.typescope attached to them.

Doing this can be a little tricky, as while typedefs are sometimes simple, they can get quite complex:

```
typedef int coordinate_t;

typedef struct
{
    int x;
    int y;
} point_t;

```

To recognise these, after matching the typedef keyword, two contexts will be pushed onto the stack: the first will recognise a typename, and then pop off, while the second will recognise the introduced name for the type:

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

In the above example, typename is a reusable context, that will read in a typename and pop itself off the stack when it's done. It can be used in any context where a type needs to be consumed, such as within a typedef, or as a function argument.

The main context uses a match pattern that pushes two contexts on the stack, with the rightmost context in the list becoming the topmost context on the stack. Once the typename context has poped itself off, the typedef_after_typename context will be at the top of the stack.

Also note above the use of anonymous contexts for brevity within the typename context.

### PHP Heredocs

This example shows how to match against [Heredocs](http://php.net/language.types.string#language.types.string.syntax.heredoc) in PHP. The match pattern in the main context captures the heredoc identifier, and the corresponding pop pattern in the heredoc context refers to this captured text with the \1 symbol:

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

When building a syntax definition, rather than manually checking scopes with the show_scope_name command, you can define a syntax test file that will do the checking for you:

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

To make one, follow these rules

1. Ensure the file name starts with "syntax_test".
2. Ensure the file is saved somewhere within the Packages directory: next to the corresponding .sublime-syntax file is a good choice.
3. Ensure the first line of the file starts with: <comment_token> SYNTAX TEST "<syntax_file>". Note that the syntax file can either be a .sublime-syntax or .tmLanguage file.

Once the above conditions are met, running the build command with a syntax test or syntax definition file selected will run all the Syntax Tests, and show the results in an output panel. *Next Result* (F4) can be used to navigate to the first failing test.

Each test in the syntax test file must first start the comment token (established on the first line, it doesn't actually have to be a comment according to the syntax), and then either a ^ or <- token.

The two types of tests are:

- Caret: ^ this will test the following selector against the scope on the most recent non-test line. It will test it at the same column the ^ is in. Consecutive ^s will test each column against the selector.
- Arrow: <- this will test the following selector against the scope on the most recent non-test line. It will test it at the same column as the comment character is in.


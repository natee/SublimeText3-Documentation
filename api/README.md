# API参考

### Sublime API

- [View](#sublime.View)
- [Selection](#sublime.Selection)
- [Region](#sublime.Region)
- [Edit](#sublime.Edit)
- [Window](#sublime.Window)
- [Settings](#sublime.Settings)

### 基类

- [EventListener](#sublime_plugin.EventListener)
- [ApplicationCommand](#sublime_plugin.ApplicationCommand)
- [WindowCommand](#sublime_plugin.WindowCommand)
- [TextCommand](#sublime_plugin.TextCommand)

## 示例插件

Sublime Text预置了几个插件，你可以在`Default`包中找到它们：

- `Packages/Default/delete_word.py`删除光标左边或右边的一个单词。
- `Packages/Default/duplicate_line.py` 重复当前行。
- `Packages/Default/goto_line.py` 给用户的输入增加提示，然后更新可选列表。
- `Packages/Default/font.py` 展示了如何使用设置工作。
- `Packages/Default/mark.py` 用`add_regions()`给gutter添加一个icon。
- `Packages/Default/trim_trailing_whitespace.py`在保存之前修改缓冲区。

## 插件生命周期

在导入的时候，插件不能调用任何API函数，除了`sublime.version()`，`sublime.platform()`，`sublime.architecture()`和 `sublime.channel()`。

如果一个插件定义了一个模块层级的函数`plugin_loaded()`，当API准备被使用时将调用这个函数。插件也可以定义一个`plugin_unloaded()`在写在插件前得到一个通知。

## 线程

所有的函数都是线程安全的，但是要记住，从以一个新的线程运行代码（异步运行）的角度来看，在代码运行时，应用程序的状态会发生变化。

## Module sublime

| 方法                                       | 返回值      | 描述                                       |
| ---------------------------------------- | -------- | ---------------------------------------- |
| set_timeout(callback, delay)             | None     | 在给定延时（ms）之后在主线程中执行回调函数。相同延时的回调函数将按其添加顺序执行。 |
| set_async_timeout(callback, delay)       | None     | 在给定延时后以一个新的线程运行回调函数。                     |
| status_message(string)                   | None     | 设置显示在状态栏的信息。                             |
| error_message(string)                    | None     | 给用户显示错误对话框。                              |
| message_dialog(string)                   | None     | 给用户显示一个消息提示框。                            |
| ok_cancel_dialog(string, <ok_title>)     | bool     | 展示一个`ok / cancel`对话框，如果提供了`ok_title`，这个文字将展示在`ok`按钮上。当用户按下ok按钮时，返回true。 |
| yes_no_cancel_dialog(string, <yes_title>, <no_title>) | Int      | 展示一个`yes / no / cancel`对话框，`yes_title`和`no_title`分别对应于相应按钮的文字。返回`sublime.DIALOG_YES`、`sublime.DIALOG_NO`、`sublime.DIALOG_CANCEL`。 |
| load_resource(name)                      | String   | 加载指定的资源，name必须采用`Packages/Default/Main.sublime-menu`格式。 |
| load_binary_resource(name)               | bytes    | 加载指定的资源，name必须采用`Packages/Default/Main.sublime-menu`格式。 |
| find_resources(pattern)                  | [String] | 找到文件名和pattern相匹配的资源。                     |
| encode_value(value, <pretty>)            | String   | 把JSON相兼容的格式转成字符串的表现形式，如果`pretty`设置为`true`，字符串将以换行和缩进进行美化。 |
| decode_value(string)                     | value    | 把JSON字符串转化成对象形式，如果字符串格式不合法，将抛出一个`ValueError`错误。 |
| expand_variables(value, variables)       | value    | 用定义在字典中的`varialbes`来扩展任何字符串`value`中的变量。`value`也可以是一个数组或字典，这种情况下，其结构将进行递归拓展。字符串应该使用代码段语法，例如：`expand_variables("Hello, ${name}", {"name": "Foo"})`。 |
| load_settings(base_name)                 | Settings | 加载指定的设置。`name`应该包含一个文件名和扩展名，但不是一个路径。这将搜索和`base_name`相匹配的包，结果将被整理到setting对象中去。随后以`base_name`调用`load_settings`将不再从磁盘加载设置，而是直接返回相同的对象。 |
| save_settings(base_name)                 | None     | 把指定设置在内存中的改变冲刷到磁盘。                       |
| windows()                                | [Window] | 返回所有打开的窗口列表。                             |
| active_window()                          | Window   | 返回最近使用的窗口。                               |
| packages_path()                          | String   | 返回包的基本路径。                                |
| installed_packages_path()                | String   | 返回用户的`.sublime-package`文件所在路径。           |
| cache_path()                             | String   | 返回Sublime Text存储缓存文件的路径。                 |
| get_clipboard(<size_limit>)              | String   | 返回剪切板中的内容。`size_limit`用来防止不必要的大数据，默认是16,777,216个字符。 |
| set_clipboard(string)                    | None     | 设置剪切板的内容。                                |
| score_selector(scope, selector)          | Int      | 用给定的作用域去匹配选择器，返回一个分值。`0`表示未匹配到，大于`0`表示有匹配项。不同的选择器可能会对同一个作用域进行比较：分值越高，表示越匹配。 |
| run_command(string, <args>)              | None     | 用指定的参数（可选）运行指定的ApplicationCommand。       |
| log_commands(flag)                       | None     | 控制指令的日志。如果启用了，所有通过按键和菜单栏运行的指令都将记录到控制台。   |
| log_input(flag)                          | None     | 控制输入的日志。如果启用了，所有的按键都将被记录到控制台。            |
| log_result_regex(flag)                   | None     | 返回结果正则的日志。这对于调试构建系统中使用的正则表达式很有用。         |
| version()                                | String   | 返回版本号。                                   |
| platform()                               | String   | 返回平台类型，“osx”、“linux”或“windows”。          |
| arch()                                   | String   | 返回CPU结构，“x32”或“x64”。                     |

## Class sublime.View

表示一个文本缓冲的视图。注意多个视图可以引用相同的缓冲区，但是它们有独立的选择和几何结构。

<table>
	<thead>
	<tr>
	  <th>方法</th>
	  <th>返回值</th>
	  <th>描述</th>
	</tr>
	</thead>
	<tbody>
	<tr>
	  <td>id()</td>
	  <td>int</td>
	  <td>返回可唯一识别视图的数值。</td>
	</tr>
	<tr>
	  <td>buffer_id()</td>
	  <td>int</td>
	  <td>返回唯一识别视图中的缓冲区的数值。</td>
	</tr>
	<tr>
	  <td>file_name()</td>
	  <td>String</td>
	  <td>完整的文件名，不存在则是None。</td>
	</tr>
	<tr>
	  <td>name()</td>
	  <td>String</td>
	  <td>分配给缓冲区的名称。</td>
	</tr>
	<tr>
	  <td>set_name(name)</td>
	  <td>None</td>
	  <td>给缓冲区设置一个名字。</td>
	</tr>
	<tr>
	  <td>is_loading()</td>
	  <td>bool</td>
	  <td>如果缓冲区正则从磁盘中加载则返回true。</td>
	</tr>
	<tr>
	  <td>is_dirty()</td>
	  <td>bool</td>
	  <td>如果缓冲区中有任何未保存的修改则返回true。</td>
	</tr>
	<tr>
	  <td>is_read_only()</td>
	  <td>bool</td>
	  <td>缓冲区是否只读。</td>
	</tr>
	<tr>
	  <td>set_read_only(value)</td>
	  <td>None</td>
	  <td>给缓冲区添加只读属性。</td>
	</tr>
	<tr>
	  <td>is_scratch()</td>
	  <td>bool</td>
	  <td>如果一个缓冲区是从无到有的缓冲区（大概就是新建的文件）则返回true，这将不会被报告为dirty。</td>
	</tr>
	<tr>
	  <td>set_scratch(value)</td>
	  <td>None</td>
	  <td>给缓冲区设置`scratch`属性。</td>
	</tr>
	<tr>
	  <td>settings()</td>
	  <td>Settings</td>
	  <td>返回视图的`settings`对象的引用。`settings`对象的任何变化都属于这个视图私有。</td>
	</tr>
	<tr>
	  <td>window()</td>
	  <td>Window</td>
	  <td>返回包含视图的窗口的引用。</td>
	</tr>
	<tr>
	  <td>run_command(string, <args>)</td>
	  <td>None</td>
	  <td>以给定的参数（可选）执行`TextCommand`。</td>
	</tr>
	<tr>
	  <td>size()</td>
	  <td>int</td>
	  <td>返回文件中的字符总数。</td>
	</tr>
	<tr>
	  <td>substr(region)</td>
	  <td>String</td>
	  <td>以字符串形式返回`region`的内容。</td>
	</tr>
	<tr>
	  <td>substr(point)</td>
	  <td>String</td>
	  <td>返回`point`右边的字符。</td>
	</tr>
	<tr>
	  <td>insert(edit, point, string)</td>
	  <td>int</td>
	  <td>在缓冲区中指定的`point`处插入给定的`string`。返回插入字符串的字符数：如果tab被替换为空格，则这个结果会不同。</td>
	</tr>
	<tr>
	  <td>erase(edit, region)</td>
	  <td>None</td>
	  <td>冲缓冲区中清除`region`的内容。</td>
	</tr>
	<tr>
	  <td>replace(edit, region, string)</td>
	  <td>None</td>
	  <td>用给定的`string`替换`region`的内容。</td>
	</tr>
	<tr>
	  <td>sel()</td>
	  <td>Selection</td>
	  <td>返回选择的引用。</td>
	</tr>
	<tr>
	  <td>line(point)</td>
	  <td>Region</td>
	  <td>返回包含`point`的行。</td>
	</tr>
	<tr>
	  <td>line(region)</td>
	  <td>Region</td>
	  <td>返回`region`的一个编辑副本，这样它以一行的开始开始，以一行的结尾为结束。注意它可能跨越好几行。</td>
	</tr>
	<tr>
	  <td>full_line(point)</td>
	  <td>Region</td>
	  <td>和`line()`类似，但是这个区块包含了换行符。</td>
	</tr>
	<tr>
	  <td>full_line(region)</td>
	  <td>Region</td>
	  <td>和`line()`类似，但是这个区块包含了换行符。</td>
	</tr>
	<tr>
	  <td>lines(region)</td>
	  <td>[Region]</td>
	  <td>返回与该`region`相交的行的列表（排序过的）。</td>
	</tr>
	<tr>
	  <td>split_by_newlines(region)</td>
	  <td>[Region]</td>
	  <td>把`region`按行分开，这样每个返回的`region`都是一行。</td>
	</tr>
	<tr>
	  <td>word(point)</td>
	  <td>Region</td>
	  <td>返回包含`point`的单词。</td>
	</tr>
	<tr>
	  <td>word(region)</td>
	  <td>Region</td>
	  <td>返回`region`的一个编辑副本，这样它以一行的开始开始，以一行的结尾为结束。注意它可能跨越好几行。</td>
	</tr>
	<tr>
	  <td>classify(point)</td>
	  <td>int</td>
	  <td>
	  	Classifies pt, returning a bitwise OR of zero or more of these flags: 
		<ul>
			<li>CLASS_WORD_START</li>
			<li>CLASS_WORD_END</li>
			<li>CLASS_PUNCTUATION_START</li>
			<li>CLASS_PUNCTUATION_END</li>
			<li>CLASS_SUB_WORD_START</li>
			<li>CLASS_SUB_WORD_END</li>
			<li>CLASS_LINE_START</li>
			<li>CLASS_LINE_END</li>
			<li>CLASS_EMPTY_LINE</li>
		</ul>
	  </td>
	</tr>
	<tr>
	  <td>find_by_class(point, forward, classes, <separators>)</td>
	  <td>Region</td>
	  <td>找到`point`之后与`classes`匹配的下一个位置。如果`forward`是False，则用向后搜索代替向前搜索。`classes`是一个位运算符或`sublime.CLASS_XXX`标签，`separators`用来定义什么字符应该被视为单独的词。</td>
	</tr>
	<tr>
	  <td>expand_by_class(point, classes, <separators>)</td>
	  <td>Region</td>
	  <td>向左或向右扩展`point`直到每一个都匹配到`classes`的位置。`classes`是一个位运算符或`sublime.CLASS_XXX`标签，`separators`用来定义什么字符应该被视为单独的词。</td>
	</tr>
	<tr>
	  <td>expand_by_class(region, classes, <separators>)</td>
	  <td>Region</td>
	  <td>向左或向右扩展`region`直到每一个都匹配到`classes`的位置。</td>
	</tr>
	<tr>
	  <td>find(pattern, fromPosition, <flags>)</td>
	  <td>Region</td>
	  <td>返回匹配到正则表达式`pattern`的第一个Region，从给定的point开始，未找到则返回None。可选的`flags`参数可以是`sublime.LITERAL`、`sublime.IGNORECASE`或两者一起。</td>
	</tr>
	<tr>
	  <td>find_all(pattern, <flags>, <format>, <extractions>)</td>
	  <td>[Region]</td>
	  <td>返回所有匹配到正则表达式的区域（无重叠）。可选的`flags`参数可以是`sublime.LITERAL`、`sublime.IGNORECASE`或两者一起。如果给定了`format`字符串，则所有匹配值都将被以格式化的字符串进行格式化。</td>
	</tr>
	<tr>
	  <td>rowcol(point)</td>
	  <td>(int, int)</td>
	  <td>计算`point`的行号和列号。从0开始算。</td>
	</tr>
	<tr>
	  <td>text_point(row, col)</td>
	  <td>int</td>
	  <td>计算给定的字符偏移量，从0开始算。</td>
	</tr>
	<tr>
	  <td>set_syntax_file(syntax_file)</td>
	  <td>None</td>
	  <td>修改视图使用的语法。用`view.settings().get('syntax')`来恢复语法。</td>
	</tr>
	<tr>
	  <td>extract_scope(point)</td>
	  <td>Region</td>
	  <td>返回在给定的`point`分配给该字符的语法名称的范围。</td>
	</tr>
	<tr>
		<td>scope_name(point)</td>
		<td>String</td>
		<td>返回在给定的`point`分配给该字符的语法名称。</td>
	</tr>
	<tr>
		<td>score_selector(point, selector)</td>
		<td>Int</td>
		<td>从指定位置的作用域中匹配选择器，返回一个分值。`0`表示没有匹配项，大于`0`表示有匹配。分值越大匹配度越高。</td>
	</tr>
	<tr>
		<td>find_by_selector(selector)</td>
		<td>[Region]</td>
		<td>返回匹配到指定的选择器的区域列表。</td>
	</tr>
	<tr>
		<td>show(point, <show_surrounds>)</td>
		<td>None</td>
		<td>滚动视图到给定的`point`。</td>
	</tr>
	<tr>
		<td>show(region, <show_surrounds>)</td>
		<td>None</td>
		<td>滚动视图到给定的`region`。</td>
	</tr>
	<tr>
		<td>show(region_set, <show_surrounds>)</td>
		<td>None</td>
		<td>滚动视图到给定的`region_set`。</td>
	</tr>
	<tr>
		<td>show_at_center(point)</td>
		<td>None</td>
		<td>滚动视图到给定的`point`居中的位置。</td>
	</tr>
	<tr>
		<td>show_at_center(region)</td>
		<td>None</td>
		<td>滚动视图到给定的`region`居中的位置。</td>
	</tr>
	<tr>
		<td>visible_region()</td>
		<td>Region</td>
		<td>返回当前视图中的可视区域。</td>
	</tr>
	<tr>
		<td>viewport_position()</td>
		<td>Vector</td>
		<td>返回视区的偏移量。</td>
	</tr>
	<tr>
		<td>set_viewport_position(vector, <animate<)</td>
		<td>None</td>
		<td>滚动视图到指定的布局位置。</td>
	</tr>
	<tr>
		<td>viewport_extent()</td>
		<td>vector</td>
		<td>返回视图的宽度和高度。</td>
	</tr>
	<tr>
		<td>layout_extent()</td>
		<td>vector</td>
		<td>返回布局的宽度和高度。</td>
	</tr>
	<tr>
		<td>text_to_layout(point)</td>
		<td>vector</td>
		<td>把文本位置转化成布局位置。</td>
	</tr>
	<tr>
		<td>layout_to_text(vector)</td>
		<td>point</td>
		<td>把布局位置转化成文本位置。</td>
	</tr>
	<tr>
		<td>window_to_layout(vector)</td>
		<td>vector</td>
		<td>把窗口位置转化成布局位置。</td>
	</tr>
	<tr>
		<td>window_to_text(vector)</td>
		<td>point</td>
		<td>把窗口位置转化成文本位置。</td>
	</tr>
	<tr>
		<td>line_height()</td>
		<td>real</td>
		<td>返回布局中使用的行高。</td>
	</tr>
	<tr>
		<td>em_width()</td>
		<td>real</td>
		<td>返回布局中使用的典型字符的宽度。</td>
	</tr>
	<tr>
		<td>add_regions(key, [regions], <scope>, <icon>, <flags>)</td>
		<td>None</td>
		<td>
		给视图添加一组区域。如果指定的key已经存在了一组区域，则它们将被覆盖。scope用来指定画区域的颜色，它的值是一个作用域的名称，如“comment”或“string”。如果scope为空，则不会画区域。
		可选的icon名称，如果指定了，将会在挨着区域的gutter处绘制一个指定的icon。这个icon将使用和scope相关联的颜色进行着色。合法的icon名称是dot、circle、bookmark、cross。icon名称也可以是一个完整的package相对路径，如Packages/Theme - Default/dot.png。
	
		可选的falg参数：
		<ul>
			<li>
		`sublime.DRAW_EMPTY`，画一个带有垂直条的区域，默认是不画的。
			</li>
			<li>`sublime.HIDE_ON_MINIMAP`，在小地图上不显示当前区域</li>
			<li>`sublime.DRAW_EMPTY_AS_OVERWRITE`，画一个带有水平条的空的区域</li>
			<li>`sublime.DRAW_NO_FILL`，禁用区域的填充色，只留外边框</li>
			<li>`sublime.DRAW_NO_OUTLINE`，禁用对区域画外框线</li>
			<li>`sublime.DRAW_SOLID_UNDERLINE`，在区域下方画一条下滑线</li>
			<li>`sublime.DRAW_STIPPLED_UNDERLINE`，在区域下方画一条点状下滑线</li>
			<li>`sublime.DRAW_SQUIGGLY_UNDERLINE`，在区域下方画一条波浪线</li>
			<li>`sublime.PERSISTENT`，保存会话中的区域</li>
			<li>`sublime.HIDDEN`，不画区域</li>
		</ul>
		
		下划线样式是排它的，0和这个只能有一个。如果使用了下划线，则DRAW_NO_FILL和DRAW_NO_OUTLINE通常应该被传入。
		</td>
	</tr>
	<tr>
		<td>get_regions(key)</td>
		<td>[regions]</td>
		<td>返回和给定`key`相关联的区域。</td>
	</tr>
	<tr>
		<td>erase_regions(key)</td>
		<td>None</td>
		<td>删除命名区域。</td>
	</tr>
	<tr>
		<td>set_status(key, value)</td>
		<td>None</td>
		<td>给视图设置状态`key`。`value`将显示在状态栏，以逗号分隔，按`key`排序。`value`为空字符串时将清除状态。</td>
	</tr>
	<tr>
		<td>get_status(key)</td>
		<td>String</td>
		<td>返回先前和`key`相关联的指定的值。</td>
	</tr>
	<tr>
		<td>erase_status(key)</td>
		<td>None</td>
		<td>清除已命名的状态。 </td>
	</tr>
	<tr>
		<td>command_history(index, <modifying_only>)</td>
		<td>(String,Dict,int)</td>
		<td>对于给定的历史记录条目，返回其存储在撤销/重做堆栈中的指令名称、指令参数和重复次数。索引`0`对应最近一个指令，`-1`对应最近第二个指令，以此类推。索引值为正数表示在重做堆栈中寻找指令。如果撤销/重做历史记录不够多（超出索引），则将返回（None,None,0）。`modifying_only`为`true`表示只返回编辑缓冲区的条目，默认值是`false`。</td>
	</tr>
	<tr>
		<td>change_count()</td>
		<td>int</td>
		<td>返回当前修改的数量。缓冲区每一次被修改，修改数就会增加。这个数值可以用来判断缓冲区自上次被检测时是否有作修改。</td>
	</tr>
	<tr>
		<td>fold([regions]) </td>
		<td>bool</td>
		<td>折叠指定的区域，如果已经被折叠则返回False。</td>
	</tr>
	<tr>
		<td>fold(region) </td>
		<td>bool</td>
		<td>折叠指定的区域，如果已经被折叠则返回False。</td>
	</tr>
	<tr>
		<td>unfold(region)</td>
		<td>[regions]</td>
		<td>展开所有区域的文本，返回展开后的区域。</td>
	</tr>
	<tr>
		<td>unfold([regions])</td>
		<td>[regions]</td>
		<td>展开所有区域的文本，返回展开后的区域。</td>
	</tr>
	<tr>
		<td>encoding()</td>
		<td>String</td>
		<td>返回当前文件的编码格式。</td>
	</tr>
	<tr>
		<td>set_encoding(encoding)</td>
		<td>None</td>
		<td>设置文件的编码格式。新的编码格式会在文件下次保存时生效。</td>
	</tr>
	<tr>
		<td>line_endings()</td>
		<td>String</td>
		<td>返回当前文件使用的行结束符。</td>
	</tr>
	<tr>
		<td>set_line_endings(line_endings)</td>
		<td>None</td>
		<td>下次保存时设置将使用的行结束符。</td>
	</tr>
	<tr>
		<td>overwrite_status()</td>
		<td>Bool</td>
		<td>返回覆盖的状态。</td>
	</tr>
	<tr>
		<td>set_overwrite_status(enabled)</td>
		<td>None</td>
		<td>设置覆盖的状态。</td>
	</tr>
	<tr>
		<td>symbols(line_endings)</td>
		<td>[(Region, String)]</td>
		<td>提取在缓冲区中定义的所有符号。</td>
	</tr>
	<tr>
		<td>show_popup_menu(items, on_done, <flags>)</td>
		<td>None</td>
		<td>在光标处显示一个弹出菜单，用来从一个列表中选择一个选项。`on_done`会以指定项目的索引被调用一次。如果弹出层取消了，`on_done`将会以参数`-1`被调用。`items`是一个字符串组成的数组。`flags`目前别无选择（完全不知道这里是啥意思Flags currently only has no option）。</td>
	</tr>
	
	</tbody>
</table>


## Class sublime.Selection

维护一组区域，确保其没有重叠。区域是有序保存的。

| 方法                  | 返回值  | 描述                             |
| ------------------- | ---- | ------------------------------ |
| clear()             | None | 删除所有区域                         |
| add(region)         | None | 添加指定的区域，它将与已经包含在集合内的任何相交的区域合并。 |
| add_all(region_set) | None | 添加所有区域。                        |
| subtract(region)    | None | 从所有区域中删掉指定的区域。                 |
| contains(region)    | bool | 如果包含了给定区域则返回true。              |

## Class sublime.Region

代表缓冲区的一个区域，两个空区域a==b是合法的。

| Constructors | 描述                     |
| ------------ | ---------------------- |
| Region(a, b) | 用初始值`a`和`b`创建一个Region。 |

| 属性   | 类型   | 描述                        |
| ---- | ---- | ------------------------- |
| a    | int  | 该区域的第一端。                  |
| b    | int  | 该区域的第二端。比`a`小时表示这个区域是颠倒的。 |
| xpos | int  | 区域的水平位置，如果未定义则是`-1`。      |

| 方法                   | 返回值    | 描述                                  |
| -------------------- | ------ | ----------------------------------- |
| begin()              | int    | 返回`a`和`b`当中的较小值。                    |
| end()                | int    | 返回`a`和`b`当中的较大值。                    |
| size()               | int    | 返回区域包含的字符数。                         |
| empty()              | bool   | 区域是否为空。`a=b`时为true。                 |
| cover(region)        | Region | 返回两个区域的并集。                          |
| intersection(region) | Region | 返回两个区域的交集。                          |
| intersects(region)   | bool   | 如果两个区域存在相交的区域则返回true。               |
| contains(region)     | bool   | 如果当前区域包含`region`则返回true。            |
| contains(point)      | bool   | 如果begin() <= point <= end()则返回true。 |

## Class sublime.Edit

`Edit`对象没有函数，它的存在是为了对缓冲区的修改进行分组。

`Edit`对象是要传递给`TextCommands`的，不是用户创建的。使用一个不合法的`Edit`对象或是从一个不同的视图中使用一个`Edit`对象将会造成需要依赖它们的函数失败。

| Methods      | Return Value | Description |
| ------------ | ------------ | ----------- |
| (no methods) |              |             |

## Class sublime.Window

| 方法                                       | 返回值            | 描述                                       |
| ---------------------------------------- | -------------- | ---------------------------------------- |
| id()                                     | int            | 返回窗口的唯一识别码                               |
| new_file()                               | View           | 创建一个新文件。返回的视图将为空，`is_loaded`方法将返回true。   |
| open_file(file_name, <flags>)            | View           | 打开指定文件名的文件，返回相应的视图。如果文件已经被打开，则此文件将会被显示到最前面。注意由于文件加载时异步的，只有`is_loading()`方法返回false时才能进行操作。可选参数`flag`是一个和一下选项相结合的按位符：1.`sublime.ENCODED_POSITION`，表示文件将在`:row`或`:row:col`后缀下进行搜索。2.把文件作为一个预览打开：这将不会有一个tab，直到被编辑过。 |
| find_open_file(file_name)                | View           | 从打开的文件列表中找到指定名称的文件，返回相应的视图，如果没有文件打开则返回None。 |
| active_view()                            | View           | 返回当前正在被编辑的视图。                            |
| active_view_in_group(group)              | View           | 返回指定group中正在被编辑的视图。                      |
| views()                                  | [View]         | 返回窗口中的所有打开的视图。                           |
| views_in_group(group)                    | [View]         | 返回指定group中所有打开的视图。                       |
| num_groups()                             | int            | 返回窗口中的视图组的数量。                            |
| active_group()                           | int            | 返回当前选中的分组的索引。                            |
| focus_group(group)                       | None           | 使当前分组处于激活状态。                             |
| focus_view(view)                         | None           | 切换到指定视图。                                 |
| get_view_index(view)                     | (group, index) | 返回视图所处的分组和索引。如果没找到则返回-1。                 |
| set_view_index(view, group, index)       | None           | 把视图移动到指定的group和索引。                       |
| is_sidebar_visible()                     | bool           | 侧边栏是否可见。                                 |
| set_sidebar_visible(flag)                | None           | 设置侧边栏的可见状态。                              |
| folders()                                | [String]       | 返回当前打开文件夹组成的列表。                          |
| project_file_name()                      | String         | 返回当前打开的项目文件的名称。                          |
| project_data()                           | Dictionary     | 返回和当前窗口关联的项目的数据。                         |
| set_project_data(data)                   | None           | 更新和当前窗口相关联的项目的数据。如果窗口和`.sublime-project`文件相关联，则项目文件将在磁盘进行更新，否则窗口将在内存中存储数据。 |
| run_command(string, <args>)              | None           | 运行指令。                                    |
| show_quick_panel(items, on_done, <flags>, <selected_index>, <on_highlighted>) | None           | 显示一个快速面板，可以从中选择一个项。`on_done`将会用选择项的索引调用一次。如果取消了快速面板，`on_done`将会以`-1`进行调用。`items`可以是一个字符串组成的数组或是一个包含字符串数组的数组。 |
| show_input_panel(caption, initial_text, on_done, on_change, on_cancel) | View           | 显示输入面板。`on_done`和`on_change`如果不为none时，都应该是一个接收唯一字符串参数的函数。`on_cancel`是无参数的函数。返回输入组件使用的视图。 |
| create_output_panel(name, <unlisted>)    | View           | 返回和输出面板关联的视图，如果需要则创建。运行窗口指令`show_panel`来显示输出面板。 |
| find_output_panel(name)                  | View or None   | 返回指定输出面板的视图，如果不存在则返回none。                |
| destroy_output_panel(name)               | None           | 销毁指定输入面板，如果当前是打开的则隐藏它。                   |
| active_panel()                           | string or None | 返回当前打开的面板的名称，如果没有则返回none。                |
| panels()                                 | [string]       | 返回没有被标记为不列出的所有面板的名称。包括除了输出面板的特定内置面板。     |
| create_output_panel(name)                | View           | 返回和输出面板关联的视图，如果需要则创建。运行窗口指令`show_panel`来显示输出面板。 |
| lookup_symbol_in_index(symbol)           | [Location]     | 返回当前项目中所有文件中定义的符号的位置。                    |
| lookup_symbol_in_open_files(symbol)      | [Location]     | 返回所有打开文件中定义的符号的位置。                       |
| extract_variables()                      | Dictionary     | 返回一个字典：`packages`，`platform`，`file`，`file_path`，`file_name`， `file_base_name`，`file_extension`，`folder`，`project`， `project_path`， `project_name`，`project_base_name`，`project_extension`。这个字典适合传递给`sublime.expand_variables()`。 |

## Class sublime.Settings

| 方法                            | 值     | 描述                       |
| ----------------------------- | ----- | ------------------------ |
| get(name)                     | value | 返回指定名称的设置。               |
| get(name, default)            | value | 返回指定名称的设置，如果未定义则返回默认值。   |
| set(name, value)              | None  | 设置指定名称的设置。只支持原始类型，列表和字典。 |
| erase(name)                   | None  | 删除指定设置，不从父级Settings中删除。  |
| has(name)                     | bool  | 是否存在某项设置。                |
| add_on_change(key, on_change) | None  | 当一个设置有改动时注册一个回调函数。       |
| clear_on_change(key)          | None  | 删除所有以指定key注册的回调函数。       |

## Module sublime_plugin

| Methods      | Return Value | Description |
| ------------ | ------------ | ----------- |
| (no methods) |              |             |

## Class sublime_plugin.EventListener

很多事件都是由视图的底层触发的，因此这些方法只会以第一个视图作为参数被调用一次。

<table>
	<thead>
	<tr>
	  <th>方法</th>
	  <th>返回值</th>
	  <th>描述</th>
	</tr>
	</thead>
	<tbody>
	<tr>
	  <td>on_new(view)</td>
	  <td>None</td>
	  <td>创建新的缓冲区时调用。</td>
	</tr>
	<tr>
		<td>on_new_async(view)</td>
		<td>None</td>
		<td>创建新的缓冲区时异步调用。</td>
	</tr>
	<tr>
		<td>on_clone(view)</td>
		<td>None</td>
		<td>克隆一个视图时调用。</td>
	</tr>
	<tr>
		<td>on_clone_async(view)</td>
		<td>None</td>
		<td>克隆一个视图时异步调用。</td>
	</tr>
	<tr>
		<td>on_load(view)</td>
		<td>None</td>
		<td>文件加载完毕时调用。</td>
	</tr>
	<tr>
		<td>on_load_async(view)</td>
		<td>None</td>
		<td>加载完毕时异步调用。</td>
	</tr>
	<tr>
		<td>on_pre_close(view)</td>
		<td>None</td>
		<td>视图关闭之前被调用。</td>
	</tr>
	<tr>
		<td>on_close(view)</td>
		<td>None</td>
		<td>视图关闭后调用（注意，可能会有其他的视图到缓冲区中）。</td>
	</tr>
	<tr>
		<td>on_pre_save(view)</td>
		<td>None</td>
		<td>视图保存前调用。</td>
	</tr>
	<tr>
		<td>on_pre_save_async(view)</td>
		<td>None</td>
		<td>视图保存前异步调用。</td>
	</tr>
	<tr>
		<td>on_post_save(view)</td>
		<td>None</td>
		<td>视图保存后调用。</td>
	</tr>
	<tr>
		<td>on_post_save_async(view)</td>
		<td>None</td>
		<td>视图被保存后异步调用。</td>
	</tr>
	<tr>
		<td>on_modified(view)</td>
		<td>None</td>
		<td>视图有修改时调用。</td>
	</tr>
	<tr>
		<td>on_modified_async(view)</td>
		<td>None</td>
		<td>视图有修改时异步调用。</td>
	</tr>
	<tr>
		<td>on_selection_modified(view)</td>
		<td>None</td>
		<td>视图中的选中区被修改后调用。</td>
	</tr>
	<tr>
		<td>on_selection_modified_async(view)</td>
		<td>None</td>
		<td>视图中的选中区被修改后异步调用。</td>
	</tr>
	<tr>
		<td>on_activated(view)</td>
		<td>None</td>
		<td>视图获得输入焦点时调用。</td>
	</tr>
	<tr>
		<td>on_activated_async(view)</td>
		<td>None</td>
		<td>视图获得输入焦点时异步调用。</td>
	</tr>
	<tr>
		<td>on_deactivated(view)</td>
		<td>None</td>
		<td>视图失去输入焦点时调用。</td>
	</tr>
	<tr>
		<td>on_deactivated_async(view)</td>
		<td>None</td>
		<td>视图失去输入焦点时异步调用。</td>
	</tr>
	<tr>
		<td>on_text_command(view, command_name, args)</td>
		<td>(new_command_name, new_args)</td>
		<td>发出文本指令时调用。监视器可以返回一个（command, arguments）元组来重写改指令，如果未作修改则返回none。</td>
	</tr>
	<tr>
		<td>on_window_command(window, command_name, args)</td>
		<td>(new_command_name, new_args)</td>
		<td>发出窗口指令时调用。监视器可以返回一个（command, arguments）元组来重写改指令，如果未作修改则返回none。</td>
	</tr>
	<tr>
		<td>post_text_command(view, command_name, args)</td>
		<td>None</td>
		<td>文本指令被执行时调用。</td>
	</tr>
	<tr>
		<td>post_window_command(window, command_name, args)</td>
		<td>None</td>
		<td>窗口指令被执行时调用。</td>
	</tr>
	<tr>
		<td>on_query_context(view, key, operator, operand, match_all)</td>
		<td>bool或None</td>
		<td>
			当决定用指定key去触发一个按键绑定时被调用。如果插件知道如何对上下文进行回应，则应该返回true或false。如果上下文是未知的，则返回none。
			<p>
				<tt><i>operater</i></tt>可以是以下中的一个：
			</p>
			<ul>
				<li>
					<tt>sublime.OP_EQUAL</tt>，上下文的值是否和操作符相等？
				</li>
				<li>
					<tt>sublime.OP_NOT_EQUAL</tt>，上下文的值是否和操作符不相等？
				</li>
				<li>
					<tt>sublime.OP_REGEX_MATCH</tt>，上下文的值是否和操作符指定的正则表达式相匹配？
				</li>
				<li>
					<tt>sublime.OP_NOT_REGEX_MATCH</tt>，上下文的值是否和操作符指定的正则表达式不匹配？
				</li>
				<li>
					<tt>sublime.OP_REGEX_CONTAINS</tt>，上下文的值是否包含一个和操作符指定的正则表达式相匹配的字符串？
				</li>
				<li>
					<tt>sublime.OP_NOT_REGEX_CONTAINS</tt>，上下文的值是否不包含一个和操作符指定的正则表达式相匹配的字符串？
				</li>
			</ul>
	
			<p>
				<tt><i>match_all</i></tt> 如果上下文涉及到这些选择则应该被使用：是否每一个选择都应该匹配（match_all = True），是否匹配一项就够了（match_all = False）？
			</p>
		</td>
	</tr>
	</tbody>
</table>


## Class sublime_plugin.ApplicationCommand

| 方法                  | 返回值    | 描述                                       |
| ------------------- | ------ | ---------------------------------------- |
| run(<args>)         | None   | 指令执行时调用。                                 |
| is_enabled(<args>)  | bool   | 如果指令此时是可以运行时返回true。默认返回true。             |
| is_visible(<args>)  | bool   | 如果指令当前显示在菜单栏中则返回true。默认返回true。           |
| is_checked(<args>)  | bool   | 如果复选框显示在菜单项旁边则返回true，如果要使用这个则`.sublime-menu`文件必须把checkbox属性设置为true。 |
| description(<args>) | String | 返回指令的描述。                                 |

## Class sublime_plugin.WindowCommand

每个窗口只会实例化一次WindowCommands。Window对象可以通过`self.window`来恢复。

| 方法                  | 返回值    | 描述                             |
| ------------------- | ------ | ------------------------------ |
| run(<args>)         | None   | 指令执行时调用                        |
| is_enabled(<args>)  | bool   | 如果指令此时是可以运行时返回true。默认返回true。   |
| is_visible(<args>)  | bool   | 如果指令当前显示在菜单栏中则返回true。默认返回true。 |
| description(<args>) | String | 返回指令的描述。                       |

## Class sublime_plugin.TextCommand

每个窗口只会实例化一次TextCommands。Window对象可以通过`self.view`来恢复。

| 方法                  | 返回值    | 描述                                       |
| ------------------- | ------ | ---------------------------------------- |
| run(edit, <args>)   | None   | 指令执行时调用                                  |
| is_enabled(<args>)  | bool   | 如果指令此时是可以运行时返回true。默认返回true。             |
| is_visible(<args>)  | bool   | 如果指令当前显示在菜单栏中则返回true。默认返回true。           |
| description(<args>) | String | 返回指令的描述。                                 |
| want_event()        | bool   | 当指令值通过鼠标行为触发时返回true以接收一个事件参数。事件的信息允许指令判断视图的哪一部分被点击了，默认返回false。 |



# 移植指南

### 概述

对于插件这一块，Sublime Text 3包含一些和Sublime Text 2非常重要区别，大多数插件都至少需要一点移植才能正常工作。这些变化是：

- Python 3.3
- 进程外的插件
- 异步事件
- 受限的`begin_edit()`和`end_edit()`
- Zipped Packages
- 导入模块

### Python 3.3

Sublime Text 3使用了Python 3.3，而Sublime Text 2使用了Python 2.6。而且，在OS X上，Python的构建系统不再使用了，而是捆绑了Sublime自己的版本。Windows和Linux上和以前一样捆绑了自己的版本。

### 进程外的插件

插件现在是一个独立的进程，`plugin_host`。从插件作者的观点来看，不应该有可观察到的差异，不同的是在插件宿主崩溃将不再降低主应用程序。

### 异步事件

Sublime Text 2中只有`set_timeout`线程是线程安全的。Sublime Text 3中，每一个API方法都是线程安全的。此外，现在有异步事件处理程序使得编写无阻塞代码更加容易。

- on_modified_async
- on_selection_modified_async
- on_pre_save_async
- on_post_save_async
- on_activated_async
- on_deactivated_async
- on_new_async
- on_load_async
- on_clone_async
- set_timeout_async

当编写线程代码时，请记住函数运行时缓冲区会在底层进行改变。

### 受限的`begin_edit()`和`end_edit()`

除了一些特殊情况，`begin_edit()`和`end_edit()`不再可以直接被访问。得到一个有效`Edit`对象实例的唯一方法是把你的代码放到一个TextCommand的子类中。通常来说，大多数代码可以通过把代码放到TextCommand中的`begin_edit()`和`end_edit()`中进行重构，然后调用这个TextCommand中的`run_command`函数。

### Zipped Packages

Sublime Text 3中的包可以直接通过`.sublime-package`（如，重命名后的.zip文件）文件运行，Sublime Text 2则是解压缩之前运行。

### 导入模块

Sublime Text 3中导入其它插件更简单且更健全，并且可以用一个常规的import语句完成。如，`import Default.comment`将导入`Packages/Default/Comment.py`。

### Restricted API Usage at Startup

由于`plugin_host`是异步加载，在导入的时候是不能使用Sublime Text API的。这意味着你的模块中的所有顶层语句将不能调用`sublime`模块中的任何函数。在启动期间，API是休眠状态，将会略任何请求。
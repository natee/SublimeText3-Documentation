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

Represents a view into a text buffer. Note that multiple views may refer to the same buffer, but they have their own unique selection and geometry.

| Methods                                  | Return Value       | Description                              |
| ---------------------------------------- | ------------------ | ---------------------------------------- |
| id()                                     | int                | Returns a number that uniquely identifies this view. |
| buffer_id()                              | int                | Returns a number that uniquely identifies the buffer underlying this view. |
| file_name()                              | String             | The full name file the file associated with the buffer, or None if it doesn't exist on disk. |
| name()                                   | String             | The name assigned to the buffer, if any  |
| set_name(name)                           | None               | Assigns a name to the buffer             |
| is_loading()                             | bool               | Returns true if the buffer is still loading from disk, and not ready for use. |
| is_dirty()                               | bool               | Returns true if there are any unsaved modifications to the buffer. |
| is_read_only()                           | bool               | Returns true if the buffer may not be modified. |
| set_read_only(value)                     | None               | Sets the read only property on the buffer. |
| is_scratch()                             | bool               | Returns true if the buffer is a scratch buffer. Scratch buffers never report as being dirty. |
| set_scratch(value)                       | None               | Sets the scratch property on the buffer. |
| settings()                               | Settings           | Returns a reference to the views settings object. Any changes to this settings object will be private to this view. |
| window()                                 | Window             | Returns a reference to the window containing the view. |
| run_command(string, <args>)              | None               | Runs the named TextCommand with the (optional) given arguments. |
| size()                                   | int                | Returns the number of character in the file. |
| substr(region)                           | String             | Returns the contents of the region as a string. |
| substr(point)                            | String             | Returns the character to the right of the point. |
| insert(edit, point, string)              | int                | Inserts the given string in the buffer at the specified point. Returns the number of characters inserted: this may be different if tabs are being translated into spaces in the current buffer. |
| erase(edit, region)                      | None               | Erases the contents of the region from the buffer. |
| replace(edit, region, string)            | None               | Replaces the contents of the region with the given string. |
| sel()                                    | Selection          | Returns a reference to the selection.    |
| line(point)                              | Region             | Returns the line that contains the point. |
| line(region)                             | Region             | Returns a modified copy of region such that it starts at the beginning of a line, and ends at the end of a line. Note that it may span several lines. |
| full_line(point)                         | Region             | As line(), but the region includes the trailing newline character, if any. |
| full_line(region)                        | Region             | As line(), but the region includes the trailing newline character, if any. |
| lines(region)                            | [Region]           | Returns a list of lines (in sorted order) intersecting the region. |
| split_by_newlines(region)                | [Region]           | Splits the region up such that each region returned exists on exactly one line. |
| word(point)                              | Region             | Returns the word that contains the point. |
| word(region)                             | Region             | Returns a modified copy of region such that it starts at the beginning of a word, and ends at the end of a word. Note that it may span several words. |
| classify(point)                          | int                | Classifies pt, returning a bitwise OR of zero or more of these flags:CLASS_WORD_STARTCLASS_WORD_ENDCLASS_PUNCTUATION_STARTCLASS_PUNCTUATION_ENDCLASS_SUB_WORD_STARTCLASS_SUB_WORD_ENDCLASS_LINE_STARTCLASS_LINE_ENDCLASS_EMPTY_LINE |
| find_by_class(point, forward, classes, <separators>) | Region             | Finds the next location after point that matches the given classes. If forward is False, searches backwards instead of forwards. classes is a bitwise OR of the sublime.CLASS_XXX flags. separators may be passed in, to define what characters should be considered to separate words. |
| expand_by_class(point, classes, <separators>) | Region             | Expands point to the left and right, until each side lands on a location that matches classes. classes is a bitwise OR of the sublime.CLASS_XXX flags. separators may be passed in, to define what characters should be considered to separate words. |
| expand_by_class(region, classes, <separators>) | Region             | Expands region to the left and right, until each side lands on a location that matches classes. classes is a bitwise OR of the sublime.CLASS_XXX flags. separators may be passed in, to define what characters should be considered to separate words. |
| find(pattern, fromPosition, <flags>)     | Region             | Returns the first Region matching the regex pattern, starting from the given point, or None if it can't be found. The optional flags parameter may be sublime.LITERAL, sublime.IGNORECASE, or the two ORed together. |
| find_all(pattern, <flags>, <format>, <extractions>) | [Region]           | Returns all (non-overlapping) regions matching the regex pattern. The optional flags parameter may be sublime.LITERAL, sublime.IGNORECASE, or the two ORed together. If a format string is given, then all matches will be formatted with the formatted string and placed into the extractions list. |
| rowcol(point)                            | (int, int)         | Calculates the 0 based line and column numbers of the point. |
| text_point(row, col)                     | int                | Calculates the character offset of the given, 0 based, row and column. Note that 'col' is interpreted as the number of characters to advance past the beginning of the row. |
| set_syntax_file(syntax_file)             | None               | Changes the syntax used by the view. syntax_file should be a name along the lines ofPackages/Python/Python.tmLanguage. To retrieve the current syntax, useview.settings().get('syntax'). |
| extract_scope(point)                     | Region             | Returns the extent of the syntax name assigned to the character at the given point. |
| scope_name(point)                        | String             | Returns the syntax name assigned to the character at the given point. |
| score_selector(point, selector)          | Int                | Matches the selector against the scope at the given location, returning a score. A score of 0 means no match, above 0 means a match. Different selectors may be compared against the same scope: a higher score means the selector is a better match for the scope. |
| find_by_selector(selector)               | [Regions]          | Finds all regions in the file matching the given selector, returning them as a list. |
| show(point, <show_surrounds>)            | None               | Scroll the view to show the given point. |
| show(region, <show_surrounds>)           | None               | Scroll the view to show the given region. |
| show(region_set, <show_surrounds>)       | None               | Scroll the view to show the given region set. |
| show_at_center(point)                    | None               | Scroll the view to center on the point.  |
| show_at_center(region)                   | None               | Scroll the view to center on the region. |
| visible_region()                         | Region             | Returns the currently visible area of the view. |
| viewport_position()                      | Vector             | Returns the offset of the viewport in layout coordinates. |
| set_viewport_position(vector, <animate<) | None               | Scrolls the viewport to the given layout position. |
| viewport_extent()                        | vector             | Returns the width and height of the viewport. |
| layout_extent()                          | vector             | Returns the width and height of the layout. |
| text_to_layout(point)                    | vector             | Converts a text position to a layout position |
| layout_to_text(vector)                   | point              | Converts a layout position to a text position |
| window_to_layout(vector)                 | vector             | Converts a window position to a layout position |
| window_to_text(vector)                   | point              | Converts a window position to a text position |
| line_height()                            | real               | Returns the light height used in the layout |
| em_width()                               | real               | Returns the typical character width used in the layout |
| add_regions(key, [regions], <scope>, <icon>, <flags>) | None               | Add a set of regions to the view. If a set of regions already exists with the given key, they will be overwritten. The scope is used to source a color to draw the regions in, it should be the name of a scope, such as "comment" or "string". If the scope is empty, the regions won't be drawn.The optional icon name, if given, will draw the named icons in the gutter next to each region. The icon will be tinted using the color associated with the scope. Valid icon names are dot, circle, bookmarkand cross. The icon name may also be a full package relative path, such as Packages/Theme - Default/dot.png.The optional flags parameter is a bitwise combination of:sublime.DRAW_EMPTY. Draw empty regions with a vertical bar. By default, they aren't drawn at all.sublime.HIDE_ON_MINIMAP. Don't show the regions on the minimap.sublime.DRAW_EMPTY_AS_OVERWRITE. Draw empty regions with a horizontal bar instead of a vertical one.sublime.DRAW_NO_FILL. Disable filling the regions, leaving only the outline.sublime.DRAW_NO_OUTLINE. Disable drawing the outline of the regions.sublime.DRAW_SOLID_UNDERLINE. Draw a solid underline below the regions.sublime.DRAW_STIPPLED_UNDERLINE. Draw a stippled underline below the regions.sublime.DRAW_SQUIGGLY_UNDERLINE. Draw a squiggly underline below the regions.sublime.PERSISTENT. Save the regions in the session.sublime.HIDDEN. Don't draw the regions.The underline styles are exclusive, either zero or one of them should be given. If using an underline, DRAW_NO_FILL and DRAW_NO_OUTLINE should generally be passed in. |
| get_regions(key)                         | [regions]          | Return the regions associated with the given key, if any |
| erase_regions(key)                       | None               | Removed the named regions                |
| set_status(key, value)                   | None               | Adds the status key to the view. The value will be displayed in the status bar, in a comma separated list of all status values, ordered by key. Setting the value to the empty string will clear the status. |
| get_status(key)                          | String             | Returns the previously assigned value associated with the key, if any. |
| erase_status(key)                        | None               | Clears the named status.                 |
| command_history(index, <modifying_only>) | (String,Dict,int)  | Returns the command name, command arguments, and repeat count for the given history entry, as stored in the undo / redo stack.Index 0 corresponds to the most recent command, -1 the command before that, and so on. Positive values for index indicate to look in the redo stack for commands. If the undo / redo history doesn't extend far enough, then (None, None, 0) will be returned.Setting modifying_only to True (the default is False) will only return entries that modified the buffer. |
| change_count()                           | int                | Returns the current change count. Each time the buffer is modified, the change count is incremented. The change count can be used to determine if the buffer has changed since the last it was inspected. |
| fold([regions])                          | bool               | Folds the given regions, returning False if they were already folded |
| fold(region)                             | bool               | Folds the given region, returning False if it was already folded |
| unfold(region)                           | [regions]          | Unfolds all text in the region, returning the unfolded regions |
| unfold([regions])                        | [regions]          | Unfolds all text in the regions, returning the unfolded regions |
| encoding()                               | String             | Returns the encoding currently associated with the file |
| set_encoding(encoding)                   | None               | Applies a new encoding to the file. This encoding will be used the next time the file is saved. |
| line_endings()                           | String             | Returns the line endings used by the current file. |
| set_line_endings(line_endings)           | None               | Sets the line endings that will be applied when next saving. |
| overwrite_status()                       | Bool               | Returns the overwrite status, which the user normally toggles via the insert key. |
| set_overwrite_status(enabled)            | None               | Sets the overwrite status.               |
| symbols(line_endings)                    | [(Region, String)] | Extract all the symbols defined in the buffer. |
| show_popup_menu(items, on_done, <flags>) | None               | Shows a pop up menu at the caret, to select an item in a list. on_done will be called once, with the index of the selected item. If the pop up menu was cancelled, on_done will be called with an argument of -1.Items is an array of strings.Flags currently only has no option. |

## Class sublime.Selection

Maintains a set of Regions, ensuring that none overlap. The regions are kept in sorted order.

| Methods             | Return Value | Description                              |
| ------------------- | ------------ | ---------------------------------------- |
| clear()             | None         | Removes all regions.                     |
| add(region)         | None         | Adds the given region. It will be merged with any intersecting regions already contained within the set. |
| add_all(region_set) | None         | Adds all regions in the given set.       |
| subtract(region)    | None         | Subtracts the region from all regions in the set. |
| contains(region)    | bool         | Returns true iff the given region is a subset. |

## Class sublime.Region

Represents an area of the buffer. Empty regions, where a == b are valid.

| Constructors | Description                              |
| ------------ | ---------------------------------------- |
| Region(a, b) | Creates a Region with initial values a and b. |

| Properties | Type | Description                              |
| ---------- | ---- | ---------------------------------------- |
| a          | int  | The first end of the region.             |
| b          | int  | The second end of the region. May be less that a, in which case the region is a reversed one. |
| xpos       | int  | The target horizontal position of the region, or -1 if undefined. Effects behavior when pressing the up or down keys. |

| Methods              | Return Value | Description                              |
| -------------------- | ------------ | ---------------------------------------- |
| begin()              | int          | Returns the minimum of a and b.          |
| end()                | int          | Returns the maximum of a and b.          |
| size()               | int          | Returns the number of characters spanned by the region. Always >= 0. |
| empty()              | bool         | Returns true iff begin() == end().       |
| cover(region)        | Region       | Returns a Region spanning both this and the given regions. |
| intersection(region) | Region       | Returns the set intersection of the two regions. |
| intersects(region)   | bool         | Returns True iff this == region or both include one or more positions in common. |
| contains(region)     | bool         | Returns True iff the given region is a subset. |
| contains(point)      | bool         | Returns True iff begin() <= point <= end(). |

## Class sublime.Edit

Edit objects have no functions, they exist to group buffer modifications.

Edit objects are passed to TextCommands, and are not user createable. Using an invalid Edit object, or an Edit object from a different view, will cause the functions that require them to fail.

| Methods      | Return Value | Description |
| ------------ | ------------ | ----------- |
| (no methods) |              |             |

## Class sublime.Window

| Methods                                  | Return Value   | Description                              |
| ---------------------------------------- | -------------- | ---------------------------------------- |
| id()                                     | int            | Returns a number that uniquely identifies this window. |
| new_file()                               | View           | Creates a new file. The returned view will be empty, and its is_loaded method will return True. |
| open_file(file_name, <flags>)            | View           | Opens the named file, and returns the corresponding view. If the file is already opened, it will be brought to the front. Note that as file loading is asynchronous, operations on the returned view won't be possible until its is_loading() method returns False.The optional flags parameter is a bitwise combination of:sublime.ENCODED_POSITION. Indicates the file_name should be searched for a :row or :row:colsuffixsublime.TRANSIENT. Open the file as a preview only: it won't have a tab assigned it until modified |
| find_open_file(file_name)                | View           | Finds the named file in the list of open files, and returns the corresponding View, or None if no such file is open. |
| active_view()                            | View           | Returns the currently edited view.       |
| active_view_in_group(group)              | View           | Returns the currently edited view in the given group. |
| views()                                  | [View]         | Returns all open views in the window.    |
| views_in_group(group)                    | [View]         | Returns all open views in the given group. |
| num_groups()                             | int            | Returns the number of view groups in the window. |
| active_group()                           | int            | Returns the index of the currently selected group. |
| focus_group(group)                       | None           | Makes the given group active.            |
| focus_view(view)                         | None           | Switches to the given view.              |
| get_view_index(view)                     | (group, index) | Returns the group, and index within the group of the view. Returns -1 if not found. |
| set_view_index(view, group, index)       | None           | Moves the view to the given group and index. |
| is_sidebar_visible()                     | bool           | Returns true if the sidebar will be shown when contents are available. |
| set_sidebar_visible(flag)                | None           | Sets the sidebar to be shown or hidden when contents are available. |
| folders()                                | [String]       | Returns a list of the currently open folders. |
| project_file_name()                      | String         | Returns name of the currently opened project file, if any. |
| project_data()                           | Dictionary     | Returns the project data associated with the current window. The data is in the same format as the contents of a .sublime-project file. |
| set_project_data(data)                   | None           | Updates the project data associated with the current window. If the window is associated with a .sublime-project file, the project file will be updated on disk, otherwise the window will store the data internally. |
| run_command(string, <args>)              | None           | Runs the named Command with the (optional) given arguments. Window.run_command is able to run both any sort of command, dispatching the command via input focus. |
| show_quick_panel(items, on_done, <flags>, <selected_index>, <on_highlighted>) | None           | Shows a quick panel, to select an item in a list. on_done will be called once, with the index of the selected item. If the quick panel was cancelled, on_done will be called with an argument of -1.Items may be an array of strings, or an array of string arrays. In the latter case, each entry in the quick panel will show multiple rows.Flags is a bitwise OR of sublime.MONOSPACE_FONT and sublime.KEEP_OPEN_ON_FOCUS_LOSTon_highlighted, if given, will be called every time the highlighted item in the quick panel is changed. |
| show_input_panel(caption, initial_text, on_done, on_change, on_cancel) | View           | Shows the input panel, to collect a line of input from the user. on_done and on_change, if not None, should both be functions that expect a single string argument. on_cancel should be a function that expects no arguments. The view used for the input widget is returned. |
| create_output_panel(name, <unlisted>)    | View           | Returns the view associated with the named output panel, creating it if required. The output panel can be shown by running the show_panel window command, with the panel argument set to the name with an "output." prefix.The optional unlisted parameter is a boolean to control if the output panel should be listed in the panel switcher. |
| find_output_panel(name)                  | View or None   | Returns the view associated with the named output panel, or None if the output panel does not exist. |
| destroy_output_panel(name)               | None           | Destroys the named output panel, hiding it if currently open. |
| active_panel()                           | string or None | Returns the name of the currently open panel, or None if no panel is open. Will return built-in panel names (e.g. "console", "find", etc) in addition to output panels. |
| panels()                                 | [string]       | Returns a list of the names of all panels that have not been marked as unlisted. Includes certain built-in panels in addition to output panels. |
| create_output_panel(name)                | View           | Returns the view associated with the named output panel, created it if required. The output panel can be shown by running the show_panel window command, with the panel argument set to the name with an "output." prefix. |
| lookup_symbol_in_index(symbol)           | [Location]     | Returns all locations where the symbol is defined across files in the current project. |
| lookup_symbol_in_open_files(symbol)      | [Location]     | Returns all locations where the symbol is defined across open files. |
| extract_variables()                      | Dictionary     | Returns a dictionary of strings populated with contextual keys: packages, platform, file, file_path, file_name, file_base_name, file_extension, folder, project, project_path, project_name, project_base_name, project_extension. This dictionary is suitable for passing tosublime.expand_variables(). |

## Class sublime.Settings

| Methods                       | Return Value | Description                              |
| ----------------------------- | ------------ | ---------------------------------------- |
| get(name)                     | value        | Returns the named setting.               |
| get(name, default)            | value        | Returns the named setting, or default if it's not defined. |
| set(name, value)              | None         | Sets the named setting. Only primitive types, lists, and dictionaries are accepted. |
| erase(name)                   | None         | Removes the named setting. Does not remove it from any parent Settings. |
| has(name)                     | bool         | Returns true iff the named option exists in this set of Settings or one of its parents. |
| add_on_change(key, on_change) | None         | Register a callback to be run whenever a setting in this object is changed. |
| clear_on_change(key)          | None         | Remove all callbacks registered with the given key. |

## Module sublime_plugin

| Methods      | Return Value | Description |
| ------------ | ------------ | ----------- |
| (no methods) |              |             |

## Class sublime_plugin.EventListener

Note that many of these events are triggered by the buffer underlying the view, and thus the method is only called once, with the first view as the parameter.

| Methods                                  | Return Value                 | Description                              |
| ---------------------------------------- | ---------------------------- | ---------------------------------------- |
| on_new(view)                             | None                         | Called when a new buffer is created.     |
| on_new_async(view)                       | None                         | Called when a new buffer is created. Runs in a separate thread, and does not block the application. |
| on_clone(view)                           | None                         | Called when a view is cloned from an existing one. |
| on_clone_async(view)                     | None                         | Called when a view is cloned from an existing one. Runs in a separate thread, and does not block the application. |
| on_load(view)                            | None                         | Called when the file is finished loading. |
| on_load_async(view)                      | None                         | Called when the file is finished loading. Runs in a separate thread, and does not block the application. |
| on_pre_close(view)                       | None                         | Called when a view is about to be closed. The view will still be in the window at this point. |
| on_close(view)                           | None                         | Called when a view is closed (note, there may still be other views into the same buffer). |
| on_pre_save(view)                        | None                         | Called just before a view is saved.      |
| on_pre_save_async(view)                  | None                         | Called just before a view is saved. Runs in a separate thread, and does not block the application. |
| on_post_save(view)                       | None                         | Called after a view has been saved.      |
| on_post_save_async(view)                 | None                         | Called after a view has been saved. Runs in a separate thread, and does not block the application. |
| on_modified(view)                        | None                         | Called after changes have been made to a view. |
| on_modified_async(view)                  | None                         | Called after changes have been made to a view. Runs in a separate thread, and does not block the application. |
| on_selection_modified(view)              | None                         | Called after the selection has been modified in a view. |
| on_selection_modified_async(view)        | None                         | Called after the selection has been modified in a view. Runs in a separate thread, and does not block the application. |
| on_activated(view)                       | None                         | Called when a view gains input focus.    |
| on_activated_async(view)                 | None                         | Called when a view gains input focus. Runs in a separate thread, and does not block the application. |
| on_deactivated(view)                     | None                         | Called when a view loses input focus.    |
| on_deactivated_async(view)               | None                         | Called when a view loses input focus. Runs in a separate thread, and does not block the application. |
| on_text_command(view, command_name, args) | (new_command_name, new_args) | Called when a text command is issued. The listener may return a (command, arguments) tuple to rewrite the command, or None to run the command unmodified. |
| on_window_command(window, command_name, args) | (new_command_name, new_args) | Called when a window command is issued. The listener may return a (command, arguments) tuple to rewrite the command, or None to run the command unmodified. |
| post_text_command(view, command_name, args) | None                         | Called after a text command has been executed. |
| post_window_command(window, command_name, args) | None                         | Called after a window command has been executed. |
| on_query_context(view, key, operator, operand, match_all) | bool or None                 | Called when determining to trigger a key binding with the given context key. If the plugin knows how to respond to the context, it should return either True of False. If the context is unknown, it should return None.operator is one of:sublime.OP_EQUAL. Is the value of the context equal to the operand?sublime.OP_NOT_EQUAL. Is the value of the context not equal to the operand?sublime.OP_REGEX_MATCH. Does the value of the context match the regex given in operand?sublime.OP_NOT_REGEX_MATCH. Does the value of the context not match the regex given in operand?sublime.OP_REGEX_CONTAINS. Does the value of the context contain a substring matching the regex given in operand?sublime.OP_NOT_REGEX_CONTAINS. Does the value of the context not contain a substring matching the regex given in operand?match_all should be used if the context relates to the selections: does every selection have to match (match_all = True), or is at least one matching enough (match_all = Fals)? |

## Class sublime_plugin.ApplicationCommand

| Methods             | Return Value | Description                              |
| ------------------- | ------------ | ---------------------------------------- |
| run(<args>)         | None         | Called when the command is run.          |
| is_enabled(<args>)  | bool         | Returns true if the command is able to be run at this time. The default implementation simply always returns True. |
| is_visible(<args>)  | bool         | Returns true if the command should be shown in the menu at this time. The default implementation always returns True. |
| is_checked(<args>)  | bool         | Returns true if a checkbox should be shown next to the menu item. The .sublime-menu file must have the checkbox attribute set to true for this to be used. |
| description(<args>) | String       | Returns a description of the command with the given arguments. Used in the menu, if no caption is provided. Return None to get the default description. |

## Class sublime_plugin.WindowCommand

WindowCommands are instantiated once per window. The Window object may be retrieved via 

self.window

| Methods             | Return Value | Description                              |
| ------------------- | ------------ | ---------------------------------------- |
| run(<args>)         | None         | Called when the command is run.          |
| is_enabled(<args>)  | bool         | Returns true if the command is able to be run at this time. The default implementation simply always returns True. |
| is_visible(<args>)  | bool         | Returns true if the command should be shown in the menu at this time. The default implementation always returns True. |
| description(<args>) | String       | Returns a description of the command with the given arguments. Used in the menu, if no caption is provided. Return None to get the default description. |

## Class sublime_plugin.TextCommand

TextCommands are instantiated once per view. The View object may be retrieved via 

self.view

| Methods             | Return Value | Description                              |
| ------------------- | ------------ | ---------------------------------------- |
| run(edit, <args>)   | None         | Called when the command is run.          |
| is_enabled(<args>)  | bool         | Returns true if the command is able to be run at this time. The default implementation simply always returns True. |
| is_visible(<args>)  | bool         | Returns true if the command should be shown in the menu at this time. The default implementation always returns True. |
| description(<args>) | String       | Returns a description of the command with the given arguments. Used in the menus, and for Undo / Redo descriptions. Return None to get the default description. |
| want_event()        | bool         | Return True to receive an event argument when the command is triggered by a mouse action. The event information allows commands to determine which portion of the view was clicked on. The default implementation returns False. |


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

### 设置

**设置文件**

**示例**

**Per-syntax设置**

### 缩进检测

### Tab和空格的转换

### 自动缩进



## 拼写检查

## 包
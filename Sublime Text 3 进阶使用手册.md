<h1>Sublime Text 3 进阶使用手册</h1>

文档基于 **Sublime Text v3.1.1 Build 3176** 编写，系 **Sublime Text** 进阶使用篇，文章内容偏技术类，需要一定的基础，菜鸟可能需要花点时间，不懂请自行百度或 Google 脑补（想上 Google 吗？那得科学上网），不定期维护。

内容囊括了 Sublime Text 3 常用快捷键、个性化设置、插件推荐、插件配置、常见问题等。配置可根据个人开发环境实际需求配置，供学习参考用，如有纰漏或疑问，请 [Issues](/issues) 提问和指正。

**注意（非常重要）：** 因插件随时都可能会更新，本手册不保证能跟上开发者脚步，所以插件的设置参数也可能会随之改变，在配置插件时，务必先确认参数是否存在而导致的各种问题！

在线阅读：<a href="/Sublime Text 3 进阶使用手册.md">Sublime Text 3 进阶使用手册</a>

---

<p style="font-size: 30px; font-weight: 300; text-align: center;">撰写不易，有钱捧个钱场 :)</p>
<br>
<div align="center">
    <img src="/img/Alipay.jpg" alt="支付宝支付" width="300">
    <img src="/img/WeChatPay.jpg" alt="微信支付" width="300">
</div>

---

# 目录

<!-- GitHub 不支持 TOC 标签，所以智能自建一个目录 -->

[TOC]

---

* [常用快捷键（Common HotKey）](#常用快捷键common-hotkey)
* [个性化设置（Customization）](#个性化设置customization)
    * [设置（Settings）](#设置settings)
    * [项目（Projects）](#项目projects)
    * [编译系统（Build System）](#编译系统build-system)
        * [SASS 文件编译](#sass-文件编译)
    * [包管理（Packages）](包管理packages)
        * [包控制（Package Control）](#包控制package-control)
        * [功能介绍](#功能介绍)
        * [常见错误](#常见错误)
    * [包推荐](#包推荐)
        * [功能包](#功能包)
        * [开发包](#开发包)
        * [前端开发包](#前端开发包)
        * [辅助包](#辅助包)
        * [主题插件](#主题插件)
* [配置插件](#配置插件)
    * [SideBarEnhancements](#sidebarenhancements)
    * [Emmet](#emmet)
    * [Terminal](#terminal)
    * [Pretty JSON](#pretty-json)
    * [BracketHighlighter](#brackethighlighter)
    * [Python PEP8 Autoformat](#python-pep8-autoformat)
    * [SublimeTmpl](#sublimetmpl)
    * [ColorHighlighter](#colorhighlighter)
    * [CodeFormatter](#codeformatter)
    * [Markdown 插件设置](#markdown-插件设置)
    * [Evernote](#evernote)

---

手册 GitHub 地址：<a href="https://github.com/JearyCheung/SublimeText3AdvancedManual">https://github.com/JearyCheung/SublimeText3AdvancedManual</a>

# 常用快捷键（Common HotKey）

```text
Ctrl + Shift + P    调出命令面板
Ctrl + /            注释单行
Ctrl + Shift + /    注释多行
Tab                 缩进
Shift + Tab         向左缩进
Ctrl + [            折叠代码
Ctrl + ]            不折叠代码
Ctrl + G            跳转指定行
Ctrl + F            查找
Ctrl + H            查找和替换
Ctrl + Shift + F    在多个文件内查找
Alt + Shift + 数字  分屏显示
Ctrl + Shift + L    将选中区域打散，并同时进行编辑
Ctrl + J            合并打散的区域
Ctrl + ←/→          逐词移动
Ctrl + Shift + ←/→  逐词选择
Ctrl + Shift + ↑/↓  逐行移动
Ctrl + Shift + [    折叠代码
Ctrl + Shift + ]    展开代码
Ctrl + K + 1        折叠所有代码（1为可变数字，表示收起级数）
Ctrl + K + J        展开所有代码
```


# 个性化设置（Customization）

## 设置（Settings）

在 `Preferences（首选项）` > `Settings（基本设置）` 中添加或修改以下代码

备注：为避免异常，请复制相关数据过去即可，千万别复制注释。

```js
{

    //Sublime Text 主题，三选一，前者需安装 Boxy Theme
    "theme": "Boxy Monokai.sublime-theme", // 推荐
    "theme": "Boxy Tomorrow.sublime-theme",
    "theme": "Default.sublime-theme",

    //代码配色方案，二选一，需安装 Monokai Extended 和 Theme - Brogrammer
    "color_scheme": "Packages/Monokai Extended/Monokai Extended.tmTheme", // 推荐
    "color_scheme": "Packages/Theme - Brogrammer/brogrammer.tmTheme",

    //光标风格
    //smooth    平滑
    //phase     呼吸
    //blink     眨眼
    //solid     固定
    "caret_style": "smooth",

    //字体风格和字体大小
    "font_face": "Consolas",
    "font_size": 13,

    //Tab 大小，一般 4 个空格即可
    "tab_size": 4,

    //保存文件使用的编码。如果一个文件以特定的编码(被检测或显式地显示)打开，这个设置将被忽略，
    //并且文件将被保存，并使用它打开的编码。
    "default_encoding": "UTF-8",

    //转换 Tab 为 空格
    "translate_tabs_to_spaces": true,

    //高亮编辑行
    "highlight_line": true,

    //状态栏显示文件编码
    "show_encoding": true,

    //代码宽度指导线
    "rulers": [100],

    //滚过头
    "scroll_past_end": true,

    //显示 Tab 和空格
    //selection：只显示画中的
    //all：显示所有
    "draw_white_space": "selection",

    //按回车时自动缩进
    "auto_indent": true,

    //自动完成
    "auto_complete": true,

    //自动完成触发条件
    "auto_complete_triggers": [
        {
            "selector": "text.html",
            "characters": "<"
        },
        {
            "selector": "text.plain",
            "characters": "<"
        }
    ],

    //自动查找选择区域
    "auto_find_in_selection": true,

    //控制自动配对的引号、括号等
    "auto_match_enabled": true,

    //保存时去掉无用空格
    "trim_trailing_white_space_on_save": true,

    //切换到另一个程序时自动保存
    "save_on_focus_lost": true,

    //文件索引解析侧栏中的所有文件，并构建其符号的索引。这是 Goto 定义工作的要求。
    //当一个项目文件过多时，Sublime Text 就会出现运行卡顿现象，所以关闭它。
    "index_files": false,

    //Vim 模式
    "ignored_packages":
    [
        "Vintage"
    ],

    //加粗侧边栏的文件夹名称
    "bold_folder_labels": true,

    //排除显示在侧边栏的文件
    "file_exclude_patterns":
    [
        ".DS_Store",
        "*.pyc",
        "*.pyo",
        "*.exe",
        "*.dll",
        "*.obj",
        "*.o",
        "*.a",
        "*.lib",
        "*.so",
        "*.dylib",
        "*.ncb",
        "*.sdf",
        "*.suo",
        "*.pdb",
        "*.idb",
        "*.class",
        "*.psd",
        "*.db",
        "*.sublime-workspace"
    ],

    //排除显示在侧边栏的文件夹
    "folder_exclude_patterns":
    [
        ".svn",
        ".git",
        ".idea",
        ".hg",
        "CVS",
        "node_modules",
        "laravel-packages",
        "resources",
        "public",
        "storage"
    ],

    //自动检查更新
    "update_check": false

}
```

**其他个性化设置**

在侧边栏显示已打开文件：`View` > `Side Bar` > `Show Open Files`

## 项目（Projects）

保存项目：`Project` > `Save Project`   
编辑项目：`Project` > `Edit Project`

```js
{
    "folders":
    [
        {
            "path": ".",
            "folder_exclude_patterns":
            [
                ".git",
                ".idea",
                "node_modules"
            ],
            "follow_symlinks": true
        },
        {
            "path": "docs",
            "name": "Documentation",
            "file_exclude_patterns":
            [
                "*.css"
            ]
        },
        {
            "path": "E:\\Example\\src",
        }
    ],
    "settings":
    {
        "tab_size": 4,
        "translate_tabs_to_spaces": true,
        "trim_trailing_white_space_on_save": false
    },
    "build_systems":
    [
        {
            "name": "List",
            "shell_cmd": "ls -l"
        }
    ]
}
```

## 编译系统（Build System）

官方文档：<a href="https://www.sublimetext.com/docs/3/build_systems.html" target="_blank">Build Systems</a>

### SASS 文件编译

复制以下代码到 `Tools` > `Build System` > `New Build System...` 中，保存为 `SASS - CurrentDir - Compressed.sublime-build`

```js
{
    "cmd": ["sass", "--update", "$file:${file_path}/${file_base_name}.css", "--stop-on-error", "--no-cache", "--sourcemap=none", "--style", "compressed"],

    "selector": "source.sass, source.scss",
    "line_regex": "Line ([0-9]+):",

    "osx":
    {
        "path": "/usr/local/bin:$PATH"
    },

    "windows":
    {
        "shell": "true"
    }
}
```

然后打开一个 SASS 文件，选择 `Tools` > `Build System` > `SASS - CurrentDir - Compressed` 即可，按快捷键 `Ctrl` + `B` 进行编译

## 包管理（Packages）

### 包控制（Package Control）

通过快捷键 <code>Ctrl + \`</code> 或 `View` > `Show Console` 打开控制台，通过 <a href="https://packagecontrol.io/installation" target="_blank">官方方法</a> 安装，或通过粘贴以下代码，回车也可安装 `Package Control`

```py
import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

重启 Sublime Text 3

**NOTE:** 如果在 `Perferences` > `Package Settings` 中看到 `Package Control` 说明安装成功

了解更多，请进入 <a href="https://packagecontrol.io/" target="_blank">Package Control</a> 官网

---

### 功能介绍

使用快捷键 `Ctrl + Shift + P` 调出命令面板，输入部分英文字母即可自动筛选，如输入 `install` 自动筛选出 `Package Control: Install Package`

```
Package Control: Install Package        安装扩展包
Package Control: Remove Package         移除扩展包
Package Control: Disable Package        禁用扩展包
Package Control: Enable Package         启用扩展包
Package Control: List Package           列出全部扩展包
Package Control: Upgrade Package        更新扩展包
```

---

### 常见错误

<h3>Error: There are no packages available for installation.</h3>

>**Package Control**
>There are no packages available for installation.

**故障原因：**

由于包源在国外，网络连通较慢导致

**解决方案：**

1. 多尝试几次即可
* 也可开启 `Package Control` 的 `Debug` 模式进行分析查看

在 `Preferences` > `Package Settings` > `Package Control` > `Settings - User` 中添加或修改以下代码开启 Debug

```javascript
{
    "debug": true,
}
```

然后按 <code>Ctrl + \`</code> 键查看 Debug



# 包推荐

***说明：** 根据自己需求安装相应的包即可，并非所有包都需要安装。*

## 功能包

| 必装  | 插件             | 说明       |
| :---- | :--------------- | :--------- |
| [ x ] | <a href="#package-control">Package Control</a> | 包控制 |
| [ x ] | SideBarEnhancements | 侧边栏右键菜单增强 |
| [ x ] | SyncedSidebarBg | 同步侧边栏背景 |
| [ x ] | <a href="#terminal">Terminal</a> | 指定项目文件夹打开终端 |
| [ x ] | Clickable URLs | 右键打开链接 |
| [ x ] | ChineseLocalizations | Sublime 中文语言包（安装好后，在 `Help` > `Language` 中选择语言） |

## 开发包

| 必装  | 插件             | 说明       |
| :---- | :--------------- | :--------- |
| [ x ] | DocBlockr | 自动生成注释（使用方法：输入 `/*` 或 `/**` 回车） |
| [ x ] | <a href="#codeformatter">CodeFormatter</a> | 代码格式化插件（支持：PHP、JavaScript、Json、CSS等） |
| [ x ] | AllAutoComplete | 让代码从所有打开的文件里自动完成匹配 |
| [ x ] | Laravel 5 Snippets | Laravel 语法提示 |
| [ x ] | Blade Snippets | Laravel Blade 语法提示 |
| [ x ] | Laravel Blade Highlighter | Laravel Blade 语法高亮 |
| [ x ] | <a href="#sublimetmpl">SublimeTmpl</a> | 新建模版文件 |
| [ x ] | <a href="#brackethighlighter">BracketHighlighter</a> | 高亮显示括号、冒号、标签等 |
| [ &nbsp;&nbsp; ] | Python 3 | Python 3 代码高亮 |
| [ &nbsp;&nbsp; ] | <a href="#python-pep8-autoformat">Python PEP8 Autoformat</a> | Python 3 代码格式化插件 |

## 前端开发包

| 必装  | 插件             | 说明       |
| :---- | :--------------- | :--------- |
| [ x ] | <a href="#emmet">Emmet</a> | HTML、HTML5、CSS、CSS3 开发代码高亮插件 |
| [ x ] | HTML-CSS-JS Prettify | HTML、CSS、JS代码快速格式化插件 |
| [ x ] | CSS3 | CSS3 语法支持 |
| [ x ] | GotoCSSDeclaration | 快速跳转到 CSS 定义位置 |
| [ x ] | SASS | SASS 语法高亮插件 |
| [ x ] | SASS Build | SASS 编译插件 |
| [ x ] | SASS Snippets | SASS 语法提示 |
| [ x ] | LESS | LESS 语法高亮 |
| [ x ] | ColorHighlighter | 颜色高亮插件 |
| [ x ] | JavaScriptNext | JavaScript 语法高亮，支持 ES6 |
| [ x ] | Javascript-API-Completions | JavaScript、jQuery、Bootstrap、HTML5 标签属性提示插件 |
| [ x ] | Minify | HTML、CSS、JS 代码压缩 |
| [ x ] | <a href="#pretty-json">Pretty JSON</a> | JSON 代码格式化 |
| [ &nbsp;&nbsp; ] | TypeScript | TypeScript 代码高亮（建议使用 Visual Studio Code） |

## 辅助包

| 必装  | 插件             | 说明       | 配置     |
| :---- | :--------------- | :--------- | :------- |
| [ x ] | <a href="#omnimarkuppreviewer">OmniMarkupPreviewer</a> | 实时预览 Markdown | `Ctrl + Alt + O` 在浏览器中实时预览 Markdown |
| [ x ] | <a href="#evernote">Evernote</a> | 用 Markdown 写印象笔记 | sublime-evernote 使用 Markdown 编辑笔记，然后同步到印象笔记中 |

## 主题插件

| 必装  | 插件             | 说明       | 配置     |
| :---- | :--------------- | :--------- | :------- |
| [ x ] | Monokai | Monokai 主题 | 无需下载，默认自带，非常好用，就是不支持 Markdown 语法 |
| [ x ] | Theme - Brogrammer | Brogrammer 主题 | 强烈推荐，配色最完善，支持 Markdown |
| [ x ] | Monokai Extended | Monokai 扩展主题 | 在 Monokai 的基础上升级的主题 |
| [ x ] | Boxy Theme | Boxy 主题 | 也不错，个人不是很喜欢配色 |
| [ x ] | A File Icon | Boxy 主题的文件图标 | 可以很直观的看到文件是什么类型 |



# 配置插件

***说明：** 配置插件前，请先确认自己是否真的需要这些功能，若不需要或不懂，请保持默认即可，以免造成不必要麻烦。*

## SideBarEnhancements

在 `Preferences` > `Package Settings` > `Side Bar` > `Settings - User` 添加或修改以下参数代码即可

```js
{
    "statusbar_modified_time": false,
    "statusbar_modified_time_format": "%A %b %d %H:%M:%S %Y",
    "statusbar_modified_time_locale": "",

    "statusbar_file_size": false,

    "close_affected_buffers_when_deleting_even_if_dirty": false,

    "hide_open_with_entries_when_there_are_no_applicable": false,

    "confirm_before_deleting": true,

    "confirm_before_permanently_deleting": true,

    "new_files_relative_to_project_root": false,
    "new_folders_relative_to_project_root": false,

    "disabled_menuitem_edit": true,
    "disabled_menuitem_edit_to_right": true,
    "disabled_menuitem_open_run": false,
    "disabled_menuitem_open_in_browser": false,
    "disabled_menuitem_open_in_new_window": false,
    "disabled_menuitem_find_in_project": false,
    "disabled_menuitem_copy_name": false,
    "disabled_menuitem_copy_path": false,
    "disabled_menuitem_copy_path_windows": true,
    "disabled_menuitem_copy_dir_path": true,
    "disabled_menuitem_paste_in_parent": true,
    "disabled_menuitem_empty": true,

    //if installed in a default location maybe this works.
    "default_browser": "", //one of this list: firefox, chrome, canary, chromium, opera, safari, ie
    "open_all_browsers": ["firefox", "chrome", "opera", "safari", "ie", "edge"], //any of this list: firefox, chrome, canary, chromium, opera, safari, ie, edge

    "portable_browser": "", // for example:  C:/Program Files (x86)/Nightly/firefox.exe

    "disable_send_to_trash": false,

    "use_powershell": true,

    "auto_close_empty_groups": false,

    "copy_path_absolute_from_project_includes_line_number": false,

    // if you donated set this value to "https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=DD4SL2AHYJGBW"
    // to remove the menuitem "Donate 20$" from the sidebar context menu.
    "i_donated_to_sidebar_enhancements_developer": false,

}
```

删除 Packages > Default 目录内的以下文件

```
Side Bar.sublime-menu
Side Bar Mount Point.sublime-menu
```

## Emmet

### 插件设置

**注意：** 此插件安装完后可能会提示 PyV8 未安装，不理会便是，首次使用时插件会自动下载安装 PyV8

在 `Preferences` > `Package Settings` > `Emmet` > `Settings - User` 添加或修改以下参数代码即可

```js
{

    // Custom snippets definitions, as per https://github.com/sergeche/emmet-sublime/blob/master/emmet/snippets.json
    "snippets": {
        "variables": {
            "lang": "zh-CN",
            "charset": "UTF-8"
        },
        "html": {
            "snippets": {
                "description": "<meta name=\"description\" content=\"\">",
                "keywords": "<meta name=\"keywords\" content=\"\">",
                //"favicon": "<link rel=\"shortcut icon\" type=\"image/x-icon\" href=\"${1:favicon.ico}\">",
                //"touch_icon": "<link rel=\"apple-touch-icon\" sizes=\"114x114\" href=\"${1:favicon.png}\">"
            },
            "abbreviations": {
                "html:5": "!!!+doc[lang=${lang}]",
                "doc": "html>(head>meta[charset=${charset}]+title{${1:Document}}+description+keywords+favicon+touch_icon)+body"
            }
        }
    }

}
```

实际输出结果

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <meta name="description" content="">
    <meta name="keywords" content="">
    <link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
    <link rel="apple-touch-icon" sizes="114x114" href="favicon.png">
</head>
<body>

</body>
</html>
```

### Error：Please wait a bit while pyV8 binary

><h3>Sublime Text 3</h3>
>Please wait a bit while pyV8 binary

**注意：** 此插件安装完后可能会提示 PyV8 未安装，不理会便是，首次使用时插件会自动下载安装 PyV8，若未解决，在选择使用以下方式。

* 去 GitHub 下载 PyV8，连接地址：<a href="https://github.com/emmetio/pyv8-binaries" target="_blank">https://github.com/emmetio/pyv8-binaries</a>
* 然后找到你的 `Sublime Text 3` 的安装包 `Packages` 路径
    * 如果是 Windows 系统：
        * 打开菜单栏 `Preferences` > `Browser Packages`
        * 然后解压文件至 `Packages\PyV8` 文件夹内，重启软件即可解决。
    * 如果是 Linux 系统：找到相应的路径，根据我在 Unbuntu 14.04 下面，解决如下：
        * 在当前用户中使用命令`ll`，你会发现一个 `.config` 的隐藏文件夹
        * 然后依次进去找到 `sublime_text/Packages` 创建 `PyV8` 文件夹，把刚才下载的文件解压进去
        * 重启解决



## Terminal

在 `Preferences` > `Package Settings` > `Terminal` > `Settings - User` 添加或修改以下参数代码即可

```
{
    "terminal": "D:\\terminal\\terminal.bat",
    "parameters": ["%CWD%"]
}
```



## Pretty JSON

### 插件设置

```js
{

    //默认不选中时对整个文件做操作
    "use_entire_file_if_no_selection" : true,

    //默认缩进 4 个空格，可自定义为缩进4个空格或一个制表符\t
    "indent" : 4,

    //默认为对 Key 做自然排序，有习惯的同学可以改成格式化时自然排序
    "sort_keys" : false,

    //默认关闭，开启时将对所有非ASCII编码的字符做unicode编码
    "ensure_ascii" : false

}
```

### 快捷键

```
Ctrl + Alt + J          格式化
Ctrl + Alt + M          压缩
```

---


## BracketHighlighter

### 插件设置

在 `Preferences` > `Package Settings` > `BracketHighlighter` > `Bracket Settings - User` 添加或修改以下参数代码即可

```js
{

    "scope_brackets": [
        {
            "name": "single_quote",
            "enabled": false
        },
        {
            "name": "double_quote",
            "enabled": false
        },
    ],

    // Define region highlight styles
    "bracket_styles": {
        // "default" and "unmatched" styles are special
        // styles. If they are not defined here,
        // they will be generated internally with
        // internal defaults.

        // "default" style defines attributes that
        // will be used for any style that does not
        // explicitly define that attribute.  So if
        // a style does not define a color, it will
        // use the color from the "default" style.
        "default": {
            "icon": "dot",
            // BH1's original default color for reference
            // "color": "entity.name.class",
            "color": "brackethighlighter.default",
            "style": "underline"
        },

        // This particular style is used to highlight
        // unmatched bracket pairs.  It is a special
        // style.
        "unmatched": {
            "icon": "question",
            "color": "brackethighlighter.unmatched",
            "style": "underline"
        },
        // User defined region styles
        "curly": {
            "icon": "curly_bracket",
            "color": "brackethighlighter.curly",
            "style": "underline"
        },
        "round": {
            "icon": "round_bracket",
            "color": "brackethighlighter.round",
            "style": "underline"
        },
        "square": {
            "icon": "square_bracket",
            "color": "brackethighlighter.square",
            "style": "underline"
        },
        "angle": {
            "icon": "angle_bracket",
            "color": "brackethighlighter.angle",
            "style": "underline"
        },
        "tag": {
            "icon": "tag",
            "color": "brackethighlighter.tag",
            "style": "underline"
        },
        "c_define": {
            "icon": "hash",
            "color": "brackethighlighter.c_define",
            "style": "underline"
        },
        "single_quote": {
            "icon": "single_quote",
            "color": "brackethighlighter.quote",
            "style": "underline"
        },
        "double_quote": {
            "icon": "double_quote",
            "color": "brackethighlighter.quote",
            "style": "underline"
        },
        "regex": {
            "icon": "regex",
            "color": "brackethighlighter.quote",
            "style": "underline"
        }
    }

}
```

---

## Python PEP8 Autoformat

### 使用方法

在 .py 文件上单击右键 `Python PEP8 Autoformat` > `ReFormat file` 或者快捷键 `Ctrl` + `Shift` + `R`

---

## SublimeTmpl

### 插件设置

在 `Preferences` > `Package Settings` > `SublimeTmpl` > `Settings - User` 中添加或修改以下参数代码即可

```js
{

    "disable_keymap_actions": false, // "all"; "html,css"
    "date_format" : "%Y-%m-%d %H:%M:%S",
    "attr": {
        "author": "example",
        "email": "example@example.org",
        "link": "http://www.example.com",
        "copyright":"Copyright © Example 保留所有权利."
    }

}
```

配置好以后在 `Preferences` > `Browse Packages` 找到 `SublimeTmpl`，首先查看 `README.md` 文档，之后修改 `templates` 文件夹下的文件，根据需求修改，例如修改html.tmpl

```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="initial-scale=1,maximum-scale=1,minimum-scale=1">
    <meta name="author" content="cjj">
    <meta name="description" content="">
    <meta name="keywords" content="">
    <title></title>
    <link href="" rel="stylesheet">
        <!-- ${author}在${date}编写 ${copyright}-->
</head>
<body>

    $0

</body>
</html>
```

配置好以后进行保存，根据 README.md 文档按快捷键 `Ctrl + Alt + h` 就可以使用配置好以后的模版了 ~ js也是如此配置，具体请查看帮助。


---

## ColorHighlighter

在 `Preferences` > `Package Settings` > `Color Highlighter` > `Settings - User` 中添加或修改以下参数代码即可

```js
{
    "ha_style": "filled"
}
```

---

## CodeFormatter

```
Ctrl + Alt + F      格式化代码
```

## Markdown 插件设置

### OmniMarkupPreviewer

* 相关文章
    * <a href="http://www.appinn.com/markdown/" target="_blank">Markdown 语法</a>
    * <a href="https://blog.csdn.net/qq_30490125/article/details/53230408" target="_blank">OmniMarkupPreviewer 使用方法</a>

```js
{
    //预览使用的模板名称
    "html_template_name": "koodoon",

    //主机地址，默认为 localhost 地址，可修改为本机 IP，这样可以让其他主机也能访问
    "server_host": "127.0.0.1",

    //MathJax 数学公式渲染库
    "mathjax_enabled": true,

    //支持的 Markdown 标签
    "renderer_options-MarkdownRenderer": {
        // "attr_list"：定义 HTML 标签属性
        // "footnotes"：文档脚注
        // "codehilite"：代码块语法高亮支持
        // "tables"：表格支持
        // "toc"：文档目录
        // "strikeout"：删除线
        // "subscript"：下标
        // "superscript"：上标
        "extensions": ["fenced_code", "footnotes", "tables", "codehilite", "toc"]
    }
}
```

### Error: 404 Not Found

OmniMarkupPreviewer 出现跟下面类似的 404 页面

><h3>Error: 404 Not Found</h3>
>Sorry, the requested URL 'http://127.0.0.1:51004/view/83' caused an error:
>'buffer_id(83) is not valid (closed or unsupported file format)'

>**NOTE:** If you run multiple instances of Sublime Text, you may want to adjust the `server_port` option in order to get this plugin work again.

**解决办法：**

在 `Preferences` > `Package Settings` > `OmniMarkupPreviewer` > `Settings - User` 中添加或修改以下参数代码即可

```js
{

    "renderer_options-MarkdownRenderer": {
        "extensions": ["tables", "fenced_code", "codehilite", "toc"]
    }

}
```

**NOTE:** 需要安装 Pygments 库才能使用 codehilite 代码语法高亮，在管理员模式下的终端里运行：`pip install pygments`

---

## Evernote

### 插件设置

* 设置 Sublime Text 与印象笔记做关联，打开下面链接创建 Token
    * 国内用户：<a href="https://app.yinxiang.com/api/DeveloperToken.action" target="_blank">https://app.yinxiang.com/api/DeveloperToken.action</a>   
    * 国际用户：<a href="https://www.evernote.com/api/DeveloperToken.action" target="_blank">https://www.evernote.com/api/DeveloperToken.action</a>   
    * 点 `Create a developer token` 生成 Token


* 将创建好的 Token 对号入座，并设置个性化 CSS

    在 `Preferences` > `Package Settings` > `Evernote` > `Settings - User` 添加或修改以下参数代码即可

```js
{

    //你的 NoteStore URL
    "noteStoreUrl": "你的 NoteStore URL",

    //你的 Developer Token
    "token": "你的 Developer Token",

    //个性化 CSS
    "inline_css": {
        "body": "font-family: 'Helvetica Neue', 'Luxi Sans', 'DejaVu Sans', 'Tahoma', 'Hiragino Sans GB', 'STHeiti', 'Microsoft YaHei'; font-size: 1em; line-height: 1.5; color: #2c3f51;",
        "h1": "margin-bottom: 1em; margin-top: 1.2em; padding-bottom: 0.3em; font-family: Helvetica, 'Microsoft YaHei', 'Droid Sans', 'Source Code Pro', Monaco, Courier, Consolas; font-size: 2em; border-bottom: 2px solid #d5d5d5;",
        "h2": "padding-bottom: 0.3em; font-family: Helvetica, 'Microsoft YaHei', 'Droid Sans', 'Source Code Pro', Monaco, Courier, Consolas; font-size: 1.5em; border-bottom: 2px solid #d5d5d5;",
        "h3": "font-family: Helvetica, 'Microsoft YaHei', 'Droid Sans', 'Source Code Pro', Monaco, Courier, Consolas; font-size: 1.17em;",
        "h4": "font-family: Helvetica, 'Microsoft YaHei', 'Droid Sans', 'Source Code Pro', Monaco, Courier, Consolas; font-size: 1em;",
        "h5": "font-family: Helvetica, 'Microsoft YaHei', 'Droid Sans', 'Source Code Pro', Monaco, Courier, Consolas; font-size: 0.83em;",
        "h6": "font-family: Helvetica, 'Microsoft YaHei', 'Droid Sans', 'Source Code Pro', Monaco, Courier, Consolas; font-size: 0.67em;",
        "hr": "height: 2px; border: none; background-color: #d5d5d5; color: #d5d5d5;",
        "pre": "padding: 6px 10px; border: 1px solid #cccccc; border-radius: 3px; font-family: 'Source Code Pro', Monaco, Courier, Consolas; background-color: #f8f8f8; overflow: auto; white-space: pre-wrap; word-wrap: break-word;",
        "code": "display: block; padding: 0.5em 0.5em !important; font-family: 'Source Code Pro', Monaco, Courier, Consolas;",
        "inline-code": "padding: 0.1em 0.2em; margin: 0.1em; border-radius: 3px; border: 1px solid #cccccc; background-color: #F5F5F5; font-family: 'Source Code Pro', Monaco, Courier, Consolas; font-size: 90%;",
        "footnotes": "border-top: 1px solid #9AB39B; font-size: 80%;",
        "sup": "color: #6D6D6D; font-size: 1ex",
        "blockquote": "border-left: .5ex solid #BFBFBF; margin-left: 0px; padding-left: 1em; margin-top: 1.4285em; margin-bottom: 1.4285em;",
        // ONLY USED IF wiki_tables or gfm_tables are enabled
        "table": "border-collapse: collapse; border-spacing: 0; margin: 1em;",
        "td": "border: 1px solid #ddd; padding: 6px 13px;",
        "th": "border: 1px solid #ddd; padding: 6px 13px;",
        "tr:odd": "border: 1px solid #ddd; padding: 6px 13px;",
        "tr:even": "border: 1px solid #ddd; padding: 6px 13px; background-color: #F8F8F8;"
    },

    //代码高亮样式
    "code_highlighting_style": "monokai"

}
```

### 插件快捷键

```js
[

    //按 Ctrl + S 保存印象笔记
    {"keys": ["ctrl+s"], "command": "save_evernote_note" },

]
```
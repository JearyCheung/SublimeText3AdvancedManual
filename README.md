# Sublime Text 3 进阶使用手册

# 简介

文档基于 **Sublime Text v3.1.1 Build 3176** 编写，系 **Sublime Text** 进阶使用篇，文章内容偏技术类，需要一定的基础，菜鸟可能需要花点时间，不懂请自行百度或 Google 脑补（想上 Google 吗？那得科学上网），不定期维护。

内容囊括了 Sublime Text 3 常用快捷键、个性化设置、插件推荐、插件配置、常见问题等。配置可根据个人开发环境实际需求配置，供学习参考用，如有纰漏或疑问，请 [Issues](/issues) 提问和指正。

**注意（非常重要）：** 因插件随时都可能会更新，本手册不保证能跟上开发者脚步，所以插件的设置参数也可能会随之改变，在配置插件时，务必先确认参数是否存在而导致的各种问题！

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

# 联系作者与反馈

* Email：<a href="mailto:jeary.cheung@koodoon.com">jeary.cheung@koodoon.com</a>
* 博客：<a href="http://www.koodoon.com">www.koodoon.com</a>
* 反馈：<a href="https://github.com/JearyCheung/SublimeText3AdvancedManual/issues">https://github.com/JearyCheung/SublimeText3AdvancedManual/issues</a>

# 欢迎捐赠

<h3 align="center" style="font-size: 30px; font-weight: 300;">领红包或赞助支持支持作者 ^_^</h3>
<h3 align="center" style="font-size: 30px; font-weight: 300;">扫码或打开支付宝首页搜索“517446586”即可领红包（保存永久可领）</h3>
<div align="center">
    <img src="img/AlipayBonus.png" alt="支付宝红包码" width="290">
    <img src="img/Alipay.jpg" alt="支付宝支付" width="290">
    <img src="img/WeChatPay.jpg" alt="微信支付" width="290">
</div>

---

在线阅读：<a href="https://github.com/JearyCheung/SublimeText3AdvancedManual/blob/master/Sublime Text 3 进阶使用手册.md">Sublime Text 3 进阶使用手册</a>

---

GitHub 地址：<a href="https://github.com/JearyCheung/SublimeText3AdvancedManual">https://github.com/JearyCheung/SublimeText3AdvancedManual</a>
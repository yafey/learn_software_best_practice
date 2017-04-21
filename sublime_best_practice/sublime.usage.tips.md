
[TOC]

# Sublime Text 3

## 置顶


### TODO

- sublime 快捷键
- sublime 自定义 `code snippet`
- [Sublime Text 3 配置和使用方法](https://www.zybuluo.com/king/note/47271) : 多技巧点、目录
- 像 办公室 电脑那样 自动提示 mdl 等， 这样就可以 按回车了。

### 自定义sublime代码片段   （sublime 自定义 `code snippet`）
[一个前端程序猿的Sublime Text3的自我修养](http://blog.guowenfh.com/2015/12/26/SublimeText/#NO-1-AdvancedNewFile：快速新建文件。) : ~~[已废链接](http://guowenfh.github.io/2015/12/26/SublimeText/ "http://guowenfh.github.io/2015/12/26/SublimeText/")~~

自定义sublime代码片段

我们在开发中有很多代码是需要重复编写的，每一次都去复制粘贴显然是一件效率极其低下的事情，sublime的自定义代码片段功能就很好的解决了这个问题。下面就来看一下如何在sublime中自定义代码片段

首先在菜单栏选择：Tools ->developer -> New Snippet可以看到新建一个xml类型的描述文件，如下：

```
<snippet>
    <content><![CDATA[
Hello, ${1:this} is a ${2:snippet}.
]]></content>
    <!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
    <!-- <tabTrigger>hello</tabTrigger> -->
    <!-- Optional: Set a scope to limit where the snippet will trigger -->
    <!-- <scope>source.python</scope> -->
</snippet>
```
注释已经非常详细了，content 里面就是代码模版：${序号：默认值} ，序号相同的地方光标会同时停在那可以多处同时编辑。序号大小就是 tabindex。在实际使用代码的时候，可以使用 tab 切换光标位置。

以hexo新建一篇博客头部为例：

```

<snippet>
    <content>
        <![CDATA[
title: ${1:标题}
date: ${2:2015-12-26 15:26:17}
tags: [${3:标签}]
categories: [${4:分类}]
]]>
    </content>
    <!-- 可选：快捷键，利用Tab自动补全代码的功能 -->
    <tabTrigger>hexoH</tabTrigger>
    <!-- 可选：使用范围，不填写代表对所有文件有效。附：source.css和test.html分别对应不同文件。 -->
    <!-- <scope>source.md</scope> -->
    <!-- 可选：在snippet菜单中的显示说明（支持中文）。如果不定义，菜单则显示当前文件的文件名。 -->
    <description>hexo博客头部生成</description>
</snippet>

```
**设置完毕，最后还差一步，要想代码片段生效，还必须保存到sublime的文件目录\Data\Packages\User，文件名任意，但文件后缀必须为.sublime-snippet。**

现在输入hexoH试试，你想要的代码片段是不是已经有了呢？


### sublime Markdown `Code Snippet`
> >参考自 ： [近乎完美的 Markdown 写作体验 - Sublime Text 3 + OmniMarkupPreviewer](http://macplay.leanote.com/post/近乎完美的-Markdown-写作体验-Sublime-Text-3-OmniMarkupPreviewer)
>
>目前笔者定义了四枚 Code Snippet, 对应如下：
>
- mdlink - 插入链接
- mdimg - 插入图片
- mdacr - 插入参考式链接
- mdfn- 插入脚注

|操作|效果|
|---|---|
|mdi,tab|`![Alt text](/path/to/img.jpg "Optional title")`|
|mdc,tab| 代码块 ，3个 ` ` ` |
|mdl,tab| `[](link)`|
|mdh1,tab|`# Header Text #`|
|mdh2..3,tab| 以 `mdh3`为例： `### Header Text ###`|
|Alt+Shift+6 (待自定义 dmfn)|脚注|


## [如何优雅地使用Sublime Text](http://jeffjade.com/2015/12/15/2015-04-17-toss-sublime-text/)

> 最好结合 下面这个整理：  [近乎完美的 Markdown 写作体验 - Sublime Text 3 + OmniMarkupPreviewer](http://macplay.leanote.com/post/近乎完美的-Markdown-写作体验-Sublime-Text-3-OmniMarkupPreviewer) 


```
{ "keys": ["Command+\\"], "command": "toggle_side_bar" }
{ "keys": ["Ctrl+\\"], "command": "toggle_side_bar" } 关闭左边SideBar，这样配置快捷键很舒服，如Atom一样（Sublime 默认是 Ctrl/ Command + k + b）。
```

。
```
Exclude files and folders from search in Sublime Text 3。

使用 SublimeText 来开发前端，这真是一个很好的存在；但当你从事一些略大项目时，必然会借助 npm/yarn 来安装很多插件，存放在 node_modules 之内；以及其他你想到的很多缓存文件、不涉及读写的文件夹等。这些文件(夹)阻碍我们进行便捷搜索，以及优雅的使用。譬如 node_modules 这个大文件夹会经常自动展开，这让我 SublimeText 的侧边栏显得臃肿杂乱，扰乱。现在有了拯救我生命的方法：打开设置（Sublime Text > Preferences > Settings，快捷键 Command + , ），注入如下配置即可；它即可将侧边栏的 node_modules 予以隐藏，So Nice；而你可根据自己的需要自行配置，从而使得可以优雅的使用，优雅的生活。

"folder_exclude_patterns": [".svn", ".git", ".hg", "CVS", "node_modules"]

其思路来源于这篇文章： http://www.lugolabs.com/articles/90-exclude-files-and-folders-from-search-in-sublime-text-3 。
```
。
```
如今前端进入到 MVVM 框架的时候，那么 React Vue必是首当其冲的选择。而项目一大，Eslint 则是必备装备了。那么问题来了，配背的 Eslint 风格必须统一，比如 是否要分号啦，缩进规则了。我团队现在用 2个空格 作为缩进准则，所以，必须要配置下：
点开 Preferences -setting 添加如下配置即可：
{
"tab_size": 2,
"translate_tabs_to_spaces": true
}
这番配置 保存在：Packages/User/Preferences.sublime-settings 这里，改得顺手，才能撸的更飞起。
```

。
```
轩哥 Sublime Text内运行javascript(ES6) 这一段 我实践证明

升级node 

不用配置 { “cmd”: [“node”, “–use-strict”, “–harmony”, “$file”], “selector”: “source.js”}

只需这样 { “cmd”: [“node”, “$file”], “selector”: “source.js”} 就可以支持ES6的

如果配置了 反而会报错
```


### [sublime text 下的Markdown写作](http://www.cnblogs.com/jadeboy/p/4165449.html)

> 结合 这个 整理：  [Sublime Text：我的极简 Markdown 编辑器](http://tinyletter.com/CNFeat/letters/sublime-text-markdown)

关于使用
Markdown Preview较常用的功能是preview in browser和Export HTML in Sublime Text，前者可以在浏览器看到预览效果，后者可将markdown保存为html文件。
preview inbrowser据称是实时的，但是实践上还是需要在st保存，然后浏览器刷新才能看到新的效果，
好在markdown写得多的话也不需要每敲一行看一次效果。

在浏览器预览Markdown文档
按Ctrl + Shift + P
输入mp 后回车(Markdown Preview: current file in browser)
此时就可以在浏览器里看到刚才编辑的文档了;
若设置了快捷键,直接(alt+m/..)即可.

关于快捷键
st支持自定义快捷键，markdown preview默认没有快捷键，我们可以自己为preview in browser设置快捷键。
方法是在Preferences -> Key Bindings User打开的文件的中括号中添加以下代码(可在Key Bindings Default找到格式)：
```
{ "keys": ["alt+m"], "command": "markdown_preview", "args": { "target": "browser"} }
```
"alt+m"可设置为您自己喜欢的按键。
如果你这里没有看到目录而只是看到代码，说明简书不支持目录自动生成...

打印成pdf
将markdown转换为pdf应该有很多种方法的。可直接用谷歌浏览器虚拟打印功能生成。
利用Markdown Preview的Preview in Browser功能可以在浏览器上看到html效果。在页面右键->打印->另存为pdf->调节页边距即可将pdf文件下载下来。



## [如何查看sublime安装了哪些插件 ](如何查看sublime安装了哪些插件 )
你应该安装过package control。
 那么只要这样：按ctrl+shift+p，输入package，选择list packages，就看到了。
 或者直接查看Installed Packages目录。




## [Sublime Text3前端必备插件](http://www.jianshu.com/p/edbc2a13494b)
emmet：

前端神器。一个可以极大提高web开发者HTML和CSS工作效率的工具箱组件。
查看介绍

CSS3：

CSS3语法高亮、CSS语法提示，美中不足的是缺少游览器私有属性高亮。
查看介绍

CSS Extended Completions：

关联CSS文件，智能提示css文件中的类名，非常好用。
查看介绍

JavaScript Completions

支持javascript原生语法提示，妈妈再也不用担心我输入document.getElementById(id)。
查看介绍

jQuery

为jQuery的大部分方法提供了示例代码段，让jQuery的API更加容易使用。
查看介绍

ColorHighlighter

它可以展示你所选择的颜色代码（像“#FFFFFF”, “rgb(255,255,255)”, “white”）的真正颜色。同时它还包含一个颜色选择器让你可以方便地更改颜色。
查看介绍

BracketHighlighter

括号以及标签层级显示，不用担心选中的代码属于哪个代码块，一目了然。
查看介绍

HTML-CSS-JS Prettify

THML、CSS、JS代码格式化，压缩过后的代码可以通过该工具复原。
查看介绍

Align​Tab

使用正则表达式来帮助代码对齐，比如几行代码以=号对齐。
查看介绍

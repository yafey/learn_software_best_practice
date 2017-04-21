[TOC]



> yafey 注 ： 建议配置在 `Settings - Syntax Specific` 里面，这样针对的是 设置了 `Syntax ` 的文件。



# 列模式
> yafey 注： Windows 下 列模式 的操作 tip ： 右键选择完后，再放开 Shift 键， 不会出现 右键菜单。

## [Sublime Text的列模式如何操作？](http://jingyan.baidu.com/article/7f766dafbc89f24101e1d085.html)
苹果：OS X

- 鼠标左键＋Option
- 或者鼠标中键
- 增加选择：Command，减少选择：Command+Shift

Windows：

- **鼠标右键＋Shift**
- 或者鼠标中键
- 增加选择：Ctrl，减少选择：Alt

Linux：

- 鼠标右键＋Shift
- 增加选择：Ctrl，减少选择：Alt




## [Sublime Column Selection （Sublime 列编辑进阶）](http://maider.blog.sohu.com/303735928.html)
背景：
某些时候，在Sublime中使用列编辑将大大提高效率。例如，我需要将每行的前七个字符都去掉，便可以使用通过列编辑模式，选中每行的前七个字符并删去。如下图所示：
![Alt text](http://sucimg.itc.cn/sblog/j31face692b36ae0bfe99fceca81f871c "列模式 去掉 每行的前七个字符")


基本篇：
打开列编辑模式很简单，按住鼠标右键，并开始拖拽需要选中的区域即可。更多的快捷键，参见：
https://www.sublimetext.com/docs/2/column_selection.html


进阶篇：

如果**每行**的字符串**长度不同**，而你需要**删除每行的最后7个字符**，该怎么办呢？

1. Ctrl+A 全选

2. Ctrl+Shift+L 进入列选模式

3. 使用方向键左右移动所有列的光标，并配合使用Shift键来多选每行的字符


这种方法还可以适用于大型文件的列编辑，这样你就不用浪费时间按住右键选中大篇幅的内容了。


参考资料：http://stackoverflow.com/questions/10080202/how-can-i-do-a-column-select-across-the-entire-file





# 显示行号 （参考 [sublime 免打扰模式下如何显示行号](https://segmentfault.com/q/1010000007030601/a-1020000007031074)）
如题， sublime 免打扰模式(shift + F11)下如何显示行号?

进入免打扰模式很爽， 不过看不到行号有点恐慌...

参考这篇文章 https://www.sublimetext.com/docs/3/distraction_free.html

```
{

"line_numbers": true,
"gutter": true,
}
```

line_numbers 和 gutter 都设置为true，其它选项看个人习惯






#  [Sublime 小技巧：文本自动换行显示？](http://www.jianshu.com/p/c75d21d2e967)


配置

如果想默认打开文件即换行显示，在选项配置中设置word_wrap为true即可
```
{
    "word_wrap": true
}
```
如果想默认打开文件即单行显示，在选项配置中设置word_wrap为false即可

```
{
    "word_wrap": false
}
```
快捷键

我们可以通过鼠标点击View -> Word Wrap来选中自动换行显示或者单行显示；自然也可以通过配置快捷键来实现快速的切换，如下设置ctrl+shift+w在是否 Word Wrap之间进行切换（toggle）
```
[
    { "keys": ["ctrl+shift+w"], "command": "toggle_setting", "args": {"setting": "word_wrap"}}
]
```
注：修改完快捷键配置无需重启，即刻生效，并且会在菜单上显示所配置的快捷键，很是贴心。
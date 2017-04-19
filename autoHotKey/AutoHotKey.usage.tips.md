

## [Win下最爱效率神器:AutoHotKey](http://jeffjade.com/2016/03/11/2016-03-11-autohotkey/#)
AutoHotkey是一个windows下的开源、免费、自动化软件工具。它由最初旨在提供键盘快捷键的脚本语言驱动(称为：热键)，随着时间的推移演变成一个完整的脚本语言。但你不需要把它想得太深，你只需要知道它可以简化你的重复性工作，一键自动化启动或运行程序等等；以此提高我们的工作效率，改善生活品质；通过按键映射，鼠标模拟，定义宏等。


为了方便修改该脚本，你可以将其放置于你觉得方便的位置，丝毫不影响，双击可运行之。我们还可以为该脚本设置开机自启动，只需要将该脚本生成一个“快捷方式”，然后将此快捷方式放置到程序自启动文件夹之下即可,一般都在这儿：
C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp
如此一开机，就可以使用脚本中所配置的功能，大为便捷。

### 简单实用的实例
这里简单说明下脚本中常用符号代表的含义：
```
# 号代表 Win 键；
! 号代表 Alt 键；
^ 号代表 Ctrl 键；
+ 号代表 shift 键；
:: 号(两个英文冒号)起分隔作用；
run，非常常用 的 AHK 命令之一;
; 号代表 注释后面一行内容；
```
run它的后面是要运行的程序完整路径（比如我的Sublime的完整路径是：D:\Program Files (x86)\Sublime Text 3\sublime_text.exe）或网址。为什么第一行代码只是写着“notepad”，没有写上完整路径？因为“notepad”是“运行”对话框中的命令之一。
如果你想按下“Ctrl + Alt + Shift + Win + Q”（这个快捷键真拉风啊。(￣▽￣)）来启动 QQ 的话，可以这样写：
>^!+#q::run QQ所在完整路径地址。


```
温馨提示： 以下几个系统默认的 Win 快捷键：
Win + E：打开资源管理器；
Win + D：显示桌面；
Win + F：打开查找对话框；
Win + R：打开运行对话框；
Win + L：锁定电脑；
Win + PauseBreak：打开系统属性对话框;
Win + Q: 本地文件/网页等搜索;
Win + U: 打开控制面板－轻松使用设置中心;
```


## 题外话： 折腾之美
最后自荐简书一专题《[折腾之美](http://www.jianshu.com/collection/2f6a49e22121 "http://www.jianshu.com/collection/2f6a49e22121")》：工欲善其事，必先利其器。大道至简：因为折腾，所以简洁；为爱折腾的你而生，欢请你的入盟(专题起源可参见[折腾之美-序](http://www.jeffjade.com/2016/02/22/2016-02-22-beautiful-of-toss/#more "http://www.jeffjade.com/2016/02/22/2016-02-22-beautiful-of-toss/#more"))。
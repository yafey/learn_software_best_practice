# 0x00 [Win下必备神器之Cmder](http://www.jianshu.com/p/b691b48bcee3)
>Cmder ( 具有Linux 温度的Windows 命令提示字元工具 )


诚言，对于开发码字者，Mac和Linux果断要比Windows更贴心;但只要折腾下，Windows下也是有不少利器的。之前就有在Windows下效率必备软件一文中对此做了下记载；其虽没oh-my-zsh那么逆天的存在，却也甚是好用，至少要比Windows原生Cmd好出了天际。因为好用，所以“必备”





## 题外话：Chocolatey 软件包管理系统
> 利用 Chocolatey 快速在 Windows 下搭建一个开发环境 https://phphub.org/topics/67

在 Linux 下，大家喜欢用 apt-get(mac下用brew) 来安装应用程序，如今在 windows 下，大家可以使用 Chocolatey 来快速下载搭建一个开发环境。Chocolatey的哲学就是完全用命令行来安装应用程序， 它更像一个包管理工具（背后使用 Nuget ）

另外需要说明的是， Chocolatey 只是把官方下载路径封装到了 Chocolatey 中，所以下载源都是其官方路径，所以下载的一定是合法的，但是如果原软件是需要 Licence 注册的话，那么 Chocolatey 下载安装好的软件还是需要你去购买注册。不过 Chocolatey 一般还是会选用免费 Licence 可用的软件。

安装chocolatey , 运行如下命令即可：
```
@powershell -NoProfile -ExecutionPolicy unrestricted -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin
```
安装软件命令 choco install softwareName, 短写是 cinst softwareName
可安装的应用程序，可以参见其 Package列表
以下是window下开发常用的开发环境应用:
```
choco install autohotkey.portable    #安装 AutoHotkey (Portable)
choco install nodejs.install  #安装 node
choco install git.install     #安装 git
choco install ruby            #安装 ruby
choco install python          #安装 python
choco install jdk8            #安装 JDK8
choco install googlechrome    #安装 Chrome
choco install google-chrome-x64 #Google Chrome (64-bit only) 
choco install firefox         #安装 firefox
choco install notepadplusplus.install #安装 notepad++
choco install Atom                    #安装 Atom
choco install SublimeText3            #安装 SublimeText3
```
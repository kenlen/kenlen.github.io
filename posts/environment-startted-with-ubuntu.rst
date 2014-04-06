.. title: 开始使用Ubuntu作为主环境
.. slug: environment-startted-with-ubuntu
.. date: 2014/04/06 15:57:20
.. tags: Ubuntu
.. link: 
.. description: 
.. type: text

最近刚买了一个sandisk至尊高速系列128GB的SSD来替代的5,400转的机械硬盘，琢磨着要重装系统，于是干脆转到ubuntu上面作为工作学习的环境，Python和R是我最主要的工作语言，这两个东西在windows下很多包安装比较费劲，干脆全面拥抱开源吧。时不时接触Debian系列的系统，安装的过程不怎么费劲，费劲的地方是配置，记录下来作为一篇文档给自己或者别人作为以后的一种参考.

硬件配置 
----------

**SSD：**
在买之前看了一些网上文章和评论 大部分人还是纠结着分数的抱怨，跑分之类的文章，其实分数都是给人看主要关心实际应用怎么样，毕竟不是服务器环境快1秒半秒感觉不出来，所以挑了个保修过硬，口碑不错，价格适中的Sandisk。4k对齐的问题，其实开发人员早就考虑过这个问题，在安装的时候全部挂载到根目录，一个人用又是这么小的硬盘就没必要分目录了，内存超过4G没必要用swap。系统基本用不完的，很多人还启用了一些内存当着ramdisk挂在/tmp目录下面怕过多的写导致SSD寿命缩短，怕麻烦，我就选择相信厂商的实力忽略了。
关闭EXT4的日志功能，对个人电脑来说日志倒是无所谓，写了几句关闭了它
测试结果如下，还不错
 
/dev/sda:

Timing cached reads: 15856 MB in 2.00 seconds = 7933.67 MB/sec 

Timing buffered disk reads: 1472 MB in 3.00 seconds = 490.28 MB/sec


**显卡**

我这台笔记本是双显卡，intel和NV G640，默认是两个卡全开，这样会导致风扇呼呼的吹，内部温度居高不下，电池耗电，所以得想办法禁用了它，网上看搜索了下文档::

$sudo add-apt-repository ppa:bumblebee/stable
$sudo apt-get update 
$sudo apt-get install bumblebee bumblebee-nvidia

靠上面的命令可以装上我们的大黄蜂nv显卡驱动，查看显卡工作状态得靠下面的命令::

$lspci|grep VGA
$00:02.0 VGA compatible controller: Intel Corporation 3rd Gen Core processor Graphics Controller (rev 09)
$01:00.0 VGA compatible controller: NVIDIA Corporation GK107M [GeForce GT 640M] (rev ff)

如果rev 是ff状态就代表关闭独显了

**触摸板**

这电脑的触摸板比较坑，系统把它认成了鼠标，fn+f3没办法禁用触摸板，驱动程序不起作用，放狗搜索了下，决定用touchpad-indicator来禁用吧::

$sudo add-apt-repository ppa:lorenzo-carbonell/atareao
$sudo apt-get update
$sudo apt-get install touchpad-indicator

安装完成后，可点击Applications > Accessories > Touchpad Indicator来禁用触摸板

软件环境
----------

本着不折腾的原则来选择自己的喜欢的软件

**Terminal**
直接用自带的gnome-terminal 出于喜欢rxvt透明环境，在.bashrc里面加上下面的一段bash，90是调整透明度的 

**浏览器** google 的chrome，顺手把firefox卸载了

**输入法** 卸载了ibus，用小企鹅::
 
$sudo add-apt-repository ppa:fcitx-team/nightly && sudo apt-get update

我比较喜欢google的拼音输入法::

$sudo apt-get install fcitx-googlepinyin

**邮件** ThunderBird比较顺手，无缝集成newsgroup

**VIM** 从spf13出来后，我就再也没配置过vim了，这个插件足够好用，该有的都有了。折腾vim是个吃力不讨好的事情，但是我喜欢它的高效，配置的事情丢给别人去做吧

**TeamViewer** 有时候要远程到公司的工作机上，我使用了teamviewer的解决方案，安装比较坑，因为12.04及以后的版本缺失了Multiarch这个包后根本没办法装上官方版本，不过好歹在文档上提示了。网上搜索了下按照这样的方式就ok了::

$wget http://www.teamviewer.com/download/teamviewer_linux.deb
$sudo apt-get install gdebi
$sudo gdebi teamviewer_linux.deb

其他的比较大众化，装了一个Dropbox,架设了把goagent的梯子，Office用自带的LibreOffice,git,python 等等或是大众或是专业的软件可以通过apt来装，大家想用啥就用啥吧。
陆陆续续用了几天来配置，除了网银外，其他还算顺手，顺便说句SSD真的很爽，开机post 后2秒进入桌面。


**参考信息：**

http://blog.codinglabs.org/articles/getting-started-with-ubuntu.html 

http://blog.sina.com.cn/s/blog_6dee445401013sss.html 

https://www.linuxwind.org/html/tag/dell-inspiron-7420 

http://forum.ubuntu.org.cn/ 

etc..

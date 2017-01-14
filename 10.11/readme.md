2017.1.15 Update:

今天早上起来黑苹果莫明挂掉，没办法，遂开始一次重装；和以前一样，做好U盘后（做的UEFI引导），进到bios里却找不到U盘的UEFI引导选项，无语恼怒中。。。一翻google后，发现有人与我类似情况（虽然年代久远）https://www.reddit.com/r/hackintosh/comments/51wcty/clean_reinstall_of_el_capitan_reboot_and_select/ ，LZ是后来自己解决的，按LZ说的，需要去更新下主板bios固件，即使是在主板bios固件已经是最新的。然后去官网下固件，在主机主板上找到我的板子是rev. 1.1，下载后，一定要放倒fat 32 格式的移动硬盘里，f2进到bios使用 Q-FLASH 更新bios固件。我和LZ的主板一样的，Gigabyte GA-Z97M-D3H；

更新完后，会自动重启，亮后会再次重启，主板便恢复了出厂，启动列也看到了U盘的UEFI引导，问题解决； 记得 disable VT-d 再装系统。



2016.1.9配了台电脑，索性一次性上10.11。写点文字，记录下安装黑苹果遇到的一些坑，以供后人参考。

电脑的配件购买基本都是按tonymacx86上的buyer guide买的，主要就是挑主板。总的下来还比较顺利，下面详细说下：

1. 首先是U盘的制作，我使用的是8g的，制作的过程有些久，远超过教程说的10分钟，建议用更大的u盘，可以节省拷贝ei capitan镜像的时间。

2. 然后是bios设置，按照教程即可，没啥坑。我的是z97m，需要改的就是 disable VT-d

3. 插上u盘安装系统。这里有个坑。连接显示器不要用vga的线，会导致进不到安装界面。详读这篇文章：http://www.tonymacx86.com/el-capitan-desktop-support/173991-big-list-solutions-el-capitan-install-problems.html#CategoryFreeze
还有就是现在使用的是新的一个 clover 的引导吧（不知道怎么形容），如果需要自定义选项进入的话，按下 空格键 就可以选择模式了（这是和以前不同的地方）。可以选择 安全模式， verbose模式等进入。

4. 安装后用MultiBeast， MultiBeast 加入了一些比较用的东西，详见：http://www.macbreaker.com/2015/12/how-to-use-multibeast-8-el-capitan.html
主要是一个能测cpu相关温度的应用，叫做 FakeSMC HWMonitor。因为黑苹果的原因，所以市面上的很多
测cpu温度的app都是没有用的，我找一个gem install iStats，测不出cpu的温度。所以这是个很有用的app，建议除了安装需要的驱动以外，把它也钩上。（注意：白苹果请不要安装，有风险）

5. 还有一个很大的坑：声卡的问题。 我的是 892，有个问题就是 黑苹果休眠后再唤醒 就会没声音。国外坛子里也很多人遇到这个问题。如果是10.11以下，可以通过安装MuliBeast 6.1.0版本的 892驱动解决。但是到了10.11，MultiBeast 6.1.0会crash，所以找到了
这个解决方案：http://www.insanelymac.com/forum/topic/308483-no-sound-after-sleep-alc-892-el-capitan-clover/?p=2178813

就这些，黑苹果使用愉快。

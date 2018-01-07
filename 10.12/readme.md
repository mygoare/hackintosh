2016.10.25日将原系统升级到了10.12

几乎无障碍，胆子也大了很多，看到tonymacx86上[Install macOS Sierra on Any Supported Intel-based PC](https://www.tonymacx86.com/threads/unibeast-install-macos-sierra-on-any-supported-intel-based-pc.200564/)的标题，胆子就更大了，毫无以前装黑苹果战战兢兢、小心翼翼的心理。

装下了也很顺利，提前已用13年买的mbp从app store下好了sierra os的镜像，然后刻盘，一切如前

因为是同一台机器，驱动方面也参照[10.11](../10.11)的选择即可


---

**Edit 2017.1.7**

这次折腾是给deskmini 110 安装 10.12.6， 不过应该适用于所有安装10.12.6 的cpu和主板

首先走的是正常的tonymac86 流程，

制作 usb 启动盘，安装

安装完成后重启，先从u盘启动，进系统后，用multibeast安装默认的kext

再重启，按一般流程重启前这里就可以 拔掉 u盘，从系统盘启动了，因为系统盘已经安装好了UEFI了，但却是一直碰壁没能成功

deskmini网上的很多资料都是过时的了，现在我装的是最新的10.12.6，该系统苹果已经可以完美识别kale lake CPU了，所以以前fakeCPU的安装经验也没有用

这里通过google  hackintosh 630 12.6  搜索到了这个网站  http://hackintosher.com/guides/guide-installing-macos-kabylake-hackintosh-sierra/

提供现成的EFI文件和各种主板，各种CPU的解决方案，简直太全面了。

然后就一气呵成，完美成功。


注意的两点：

1.  不要用VGA线，deskmini主板上有这个老接口，显示器会无信号 no signal，坑爹

2.  启动的时候需要 patch dell bios， 不知道为什么没看网上有人说，但我这台deskmini 110却是需要的，不勾上的话进不去系统


clover configurator 下载 http://mackie100projects.altervista.org/download-clover-configurator/


由这次可见： 装黑苹果的关键就在于 EFI 这个文件夹，以及其中的 kext 包 和 config.plist 配置文件

假使以后黑苹果被弄坏了，只要安装的U盘还在，照样可以进系统，换换EFI文件，配置配置config.plist，打打 kext 的补丁之类的

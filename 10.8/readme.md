公司主板  Gigabyte H77N Wifi

##Hackintosh Based On Mesheven PC

###The way to get here

We spend much of the part-time start installing hackintosh from zero, we met many
problems and bugs, restarted pc many many times, but all solved through searching
and learning from Internet.

Really happy to share it with you!

###About

This is project about how to install [hackintosh](http://en.wikipedia.org/wiki/Hackintosh)(黑苹果) painless on mesheven pc.

The motherboard is [Gigabyte H77N Wifi](http://www.gigabyte.com.au/products/product-page.aspx?pid=4338#ov), thanks Steve.
So if your pc also use the motherboard, the guide also can help.


###How to install

#### Install Mountain Lion (10.8)

Basically we can follow the tutorial from [tonymacx86.com](http://www.tonymacx86.com/61-unibeast-install-os-x-mountain-lion-any-supported-intel-based-pc.html)
to install the mac os X 10.8 (mountain lion)
![MultiBeast](./10.8/Snip20140208_2.png)

###Bugs fix

Although install successfully, but hackintosh still exist some bugs need to fix, mostly of
them are from Device Drivers.

Below I will list some of the bugs have been fixed:

* **Sometimes can't connect the internet**

<del>At first, we solve this issue use the stupid way by restarting the system again and again.
Several times later, It gone ok.

<del>But now, we find the way to solve:

<del>`sudo ifconfig en0 ether 90:2b:34:de:19:e4`

<del>`sudo ifconfig en0 down`

<del>`sudo ifconfig en0 up`

<del>`en0` is the first network card, so `en1` is the second card.

<del>`90:2b:34:de:19:e4` is the mac address of the network card you used.(Mesheven pc has two network cards)

<del>`down`, `up` is restarting the network card.

<del>现在，一直插了两根网线，一直未出现断网

现在发现，可能是astrill软件的问题。现在使用shadowsocks翻墙，一直未出现断网情况

* **Audio device can't found** (10.9.3没有此问题)

Can't control the system voice & can't find the audio device. But USB headphone works.

So we should reinstall driver self:

    cd ./10.8/Audio/
    mv AppleHDA.kext HDAEnabler1.kext ~/Desktop/
    Doublclick [KextBeast](http://tonymacx86.blogspot.com/2010/08/kextbeast-simple-kext-installer.html) to install (It will move the two files to /System/Library/Extensions/ folder)
    reboot

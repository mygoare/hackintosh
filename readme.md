##Hackintosh Based On Mesheven PC

###About

This is project about how to install [hackintosh](http://en.wikipedia.org/wiki/Hackintosh)(黑苹果) painless on mesheven pc.

The motherboard is [Gigabyte H77N Wifi](http://www.gigabyte.com.au/products/product-page.aspx?pid=4338#ov), thanks Steve.
So if your pc also use the motherboard, the guide also can help.


###How to install

#### Install Mountain Lion

Basically we can follow the tutorial from [tonymacx86.com](http://www.tonymacx86.com/61-unibeast-install-os-x-mountain-lion-any-supported-intel-based-pc.html)
to install the mac os X 10.8 (mountain lion)
![MultiBeast](./10.8/Snip20140208_2.png)

###Bugs fix

Although install successfully, but hackintosh still exist some bugs need to fix, mostly of
them are from Device Drivers.

Below I will list some of the bugs have been fixed:

* **Sometimes can't connect the internet**

At first, we solve this issue use the stupid way by restarting the system again and again.
Several times later, It gone ok.

But now, we find the way to solve:

    sudo ifconfig en0 ether 90:2b:34:de:19:e4
    sudo ifconfig en0 down
    sudo ifconfig en0 up

`en0` is the first network card, so `en1` is the second card.

`90:2b:34:de:19:e4` is the mac address of the network card you used.(Mesheven pc has two network cards)

`down`, `up` is restarting the network card.

* **Audio device can't found**

Can't control the system voice & can't find the audio device. But USB headphone works.

So we should install driver self:

    cd ./10.8/Audio/
    mv AppleHDA.kext HDAEnabler1.kext ~/Desktop/
    Doublclick KextBeast to install (It will move the two files to /System/Library/Extensions/ folder)
    reboot

###Notes:

1.  Don't shutdown hackintosh force
2.  Don't upgrade your system version. Don't upgrade to 10.8.5 or 10.9. After upgrade,
hackintosh will crash.

###Tips:

Above are based on Mesheven PC (Gigabyte H77N Wifi motherboard), please notice. Other
PC(motherboard) I can't guarantee this guide works.

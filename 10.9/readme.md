公司主板  Gigabyte H77N Wifi

#### Install Mavericks (10.9.3)

1. 制作U盘启动盘（10.9.3的系统一定要在App Store里下载，其他第三方网盘或迅雷下载的在用Unibeast制作U盘启动盘时都会报错：系统不完整）
2. 启动电脑进入U盘系统，如果进不去`-x`进安全模式，格式化U盘（注意options分区选项，选择可启动分区）
3. 系统安装完成后，启动进到系统盘中（进不去同样`-x`进安全模式），用MulitBeast安装各种驱动，可在坛子里提前找好DSDT文件。需要特别选择的是声卡 和 网卡 驱动
4. 最后需要特别添加一个启动选项`dart=0`，可以将这项配置添加到`/Extra/org.chameleon.Boot.plist`文件中：

		<key>Kernel Flags</key>
		<string>dart=0</string>

Bug:

1. 10.9.3无法sleep（sleep后进入系统无需输入密码）
2. <del>sleep唤醒后声卡没声音（10.8的声卡驱动对10.9.3无效，会导致system preferences crash）</del>*已解决，使用MultBeast 6.1.0 安装声卡驱动即可*


#### Install Mavericks (10.9.4)

同 10.9.3，下载app store的升级包，问题不大

### Update
声卡 用multBeast 6.1 安装，选 892；

网卡选Realtel offical 最后一个。彻底解决一直以来都存在的网卡bug :-)


###Notes:

2.  **Don't Install NEED RESTART UPDATES from App Store**
4.  **Don't use [cleanmymac](http://macpaw.com/cleanmymac) or similar software, sometimes it will delete some system related files make hackintosh crash**

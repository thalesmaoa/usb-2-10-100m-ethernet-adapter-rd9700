![](images/usb-2-10-100m-ethernet-adapter-9700.jpg)

## Installation of "USB 2.0 10/100M Ethernet Adapter" (model QTS1081B 9700) (Corechip RD9700) in Apple macOS High Sierra

Installation guide for an inexpensive ($2 on eBay, shipped) unbranded "USB 2.0 10/100M Ethernet Adapter" model QTS1081B 9700 (RD9700 chip by [Corechip](http://www.corechip-sz.com/)) in Apple macOS High Sierra (10.13.6) (tested in 2017 Macbook Air). Included driver files were provided on the installation CD included with the adapter.

Please help saving beautiful minds by turning off WiFi microwave radios.

### 1) Disabling SIP (System Integrity Protection)

From the menu bar, select "****" (Apple symbol), then "**Restart**". <br>
As soon as the screen becomes black, hold down "**Command**" and "**R**" until the Apple logo and a progress bar appear. <br>
Wait for the computer to boot into recovery mode. <br>
From the menu bar, select "**Utilities**" and then “**Terminal**”. <br>
In the terminal, type: ```csrutil disable```, press Return. <br>
From the menu bar, select "****" (Apple symbol), then "**Restart**". <br>

### 2) Installing driver
**For Catalina users only** <br>
Open “**Terminal**” and type
```
sudo mount -uw /
sudo killall Finder
```
Execute file "**RD9700  Mac OS 10.10 Driver.pkg**" from the directory "**RD9700Driver/MAC DRIVER**", by double clicking on it. <br>
Installer window will appear. <br>
Proceed with the installation. Proceed with the installation. Installation can fail but it will work anyway.<br>
Once installation application has finished, the application window should state: "**The installation was successful. The software was installed.**". <br>
Click on "**Close**". <br>
Kernel extension files should have been copied to directory "**/System/Library/Extensions/RD9700.kext**". <br>

### 3) Enabling SIP (System Integrity Protection)

From the menu bar, select "****" (Apple symbol), then "**Restart**". <br>
As soon as the screen becomes black, hold down "**Command**" and "**R**" until the Apple logo and a progress bar appear. <br>
Wait for the computer to boot into recovery mode. <br>
From the menu bar, select "**Utilities**" and then “**Terminal**”. <br>
In the terminal, type: ```csrutil enable```, press Return key. <br>
From the menu bar, select "****" (Apple symbol), then "**Restart**". <br>

### 4) Verifying adapter is recognized by the system (optional step)

From the menu bar, select "****", select "**About This Mac**" -> click "**System Report**" -> select "**Hardware**" -> select "**USB**" -> select "**USB 3.0 Bus**" -> select "**USB 2.0 10/100M Ethernet Adaptor**". <br>
An example of a configuration:

    USB 2.0 10/100M Ethernet Adaptor:
    
      Product ID:	0x9700
      Vendor ID:	0x0fe6
      Version:	1.01
      Speed:	Up to 12 Mb/sec
      Location ID:	0x14200000 / 9
      Current Available (mA):	500
      Current Required (mA):	120
      Extra Operating Current (mA):	0

![](images/01.png)

### 5) Adding network interface

NOTE: The USB adapter will not show up in the list of network interfaces if it is not plugged in the USB port (it's not relevant, if the ethernet cable is plugged in or if it is "live").<br>

From the menu bar, select "****" (Apple symbol) -> "**System Preferences**" -> "**Network**" -> "**+**" (to add service) -> select "**USB 2.0 10/100M Ethernet Adaptor**" -> click "**Create**". <br>
The new adapter should be added to the list in the window on the left. If the ethernet cable is not inserted into the adapter or if it is not live, the status will state "**Not Connected**". If ethernet cable is connected and "live", the status should be **"Connected"**. <br>
From here, network specific options should be configured (such as: automatic configuration of IPv4 with DHCP, etc.) as per user's need - as in the examples below. <br>
NOTE: This interface gets assigned a random MAC address. The reported USB connection throughput is 12 Mbps (USB 1.1, not (advertised) USB 2.0 speeds), thus data throughputs will be in the 600-700 KiB/s range.<br>

![](images/02.png)

![](images/03.png)

#### SHA256 sums

```
bb1706c1c58fcb57039c3e767f79847ae342d15c32e49d1102427edadd489c0b  ./RD9700Driver/9700/WINCE500/CoreChip QF9700 USB Driver For WINCE 5.0.cab
ffd44be0b28412c470260b4269802cc9b8ef7880390f1e0376fe3b65e78401c6  ./RD9700Driver/9700/WINCE500/QF9700USB.bib
933d32da2241fd6cd818b23d68324685ab080d9f2e49fe4886356501328eb048  ./RD9700Driver/9700/WINCE500/QF9700USB.dll
7796a0447c7cfac760068d8d7f27651d3e52574f4913f73336ac9c19e7f58676  ./RD9700Driver/9700/WINCE500/QF9700USB.reg
a049f97b5e003806e8466c68414808e487d3d7dda05b7b232e1dcb0d0e6c8dfb  ./RD9700Driver/9700/WINCE500/README.txt
7975b83020baba374b088c62e3a35844afc6234e156506533643c3e6b449f470  ./RD9700Driver/9700/WINCE600/QF9700Release/CoreChip QF9700 Driver For Windows CE 6.0.cab
ffd44be0b28412c470260b4269802cc9b8ef7880390f1e0376fe3b65e78401c6  ./RD9700Driver/9700/WINCE600/QF9700Release/QF9700USB.bib
19d39a02ff3ebc55c39788002063b5dd480a36a2aa9342b1ae08561bdfb511cf  ./RD9700Driver/9700/WINCE600/QF9700Release/QF9700USB.dll
7796a0447c7cfac760068d8d7f27651d3e52574f4913f73336ac9c19e7f58676  ./RD9700Driver/9700/WINCE600/QF9700Release/QF9700USB.reg
a049f97b5e003806e8466c68414808e487d3d7dda05b7b232e1dcb0d0e6c8dfb  ./RD9700Driver/9700/WINCE600/QF9700Release/README.txt
bb1706c1c58fcb57039c3e767f79847ae342d15c32e49d1102427edadd489c0b  ./RD9700Driver/ce/WINCE500/CoreChip QF9700 USB Driver For WINCE 5.0.cab
ffd44be0b28412c470260b4269802cc9b8ef7880390f1e0376fe3b65e78401c6  ./RD9700Driver/ce/WINCE500/QF9700USB.bib
933d32da2241fd6cd818b23d68324685ab080d9f2e49fe4886356501328eb048  ./RD9700Driver/ce/WINCE500/QF9700USB.dll
7796a0447c7cfac760068d8d7f27651d3e52574f4913f73336ac9c19e7f58676  ./RD9700Driver/ce/WINCE500/QF9700USB.reg
a049f97b5e003806e8466c68414808e487d3d7dda05b7b232e1dcb0d0e6c8dfb  ./RD9700Driver/ce/WINCE500/README.txt
7975b83020baba374b088c62e3a35844afc6234e156506533643c3e6b449f470  ./RD9700Driver/ce/WINCE600/QF9700Release/CoreChip QF9700 Driver For Windows CE 6.0.cab
ffd44be0b28412c470260b4269802cc9b8ef7880390f1e0376fe3b65e78401c6  ./RD9700Driver/ce/WINCE600/QF9700Release/QF9700USB.bib
19d39a02ff3ebc55c39788002063b5dd480a36a2aa9342b1ae08561bdfb511cf  ./RD9700Driver/ce/WINCE600/QF9700Release/QF9700USB.dll
7796a0447c7cfac760068d8d7f27651d3e52574f4913f73336ac9c19e7f58676  ./RD9700Driver/ce/WINCE600/QF9700Release/QF9700USB.reg
a049f97b5e003806e8466c68414808e487d3d7dda05b7b232e1dcb0d0e6c8dfb  ./RD9700Driver/ce/WINCE600/QF9700Release/README.txt
e95d902f2f8a95e4be9e6d57703cbeb70684ce83142b5833ad7c60cbb42976af  ./RD9700Driver/Linux/.qf9700.ko.cmd
c98daf88a2f5aaecd27ab2ea25f44814f504b01ae2bcdcc449e75258d19b0318  ./RD9700Driver/Linux/.qf9700.mod.o.cmd
7c3c877ab3b522795ccb63507905066dd3d7d1698095480c692fdbd3d24d1246  ./RD9700Driver/Linux/.qf9700.o.cmd
f7fa0319a4da3e938a4c575468ca385b9462ce6c9b4e2b67ee413b022e730415  ./RD9700Driver/Linux/.tmp_versions/qf9700.mod
98f9dd31430651df92733a2926c44c21adb8889dd12b54258f4647b8b1586e2a  ./RD9700Driver/Linux/Makefile
4329d514dc0cf66e48899403a6d92d953e0df6265dbdad81c81a541af09964f0  ./RD9700Driver/Linux/Module.markers
e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855  ./RD9700Driver/Linux/Module.symvers
bedc6fa0be671eb1d52671de47654818632ffc45ff3b631c93de083dc05f857f  ./RD9700Driver/Linux/modules.order
eaf23fd6ac01f06e017704cfb1110907ddb08839c9ac2fb1a745996239e0bb37  ./RD9700Driver/Linux/qf9700.c
35a9dba78792ad31bccb2024c5d90d35fc75643467b66c90f2165c7f73c74d26  ./RD9700Driver/Linux/qf9700.h
50ce037f0adb70cb6074dcb456bf1482bf55dfd6341995e0c6f00d89f29edac7  ./RD9700Driver/Linux/qf9700.ko
38481e489ed2f98cb6c5c01584db7d9ee836d1c84dc5efea54b7749fd7c52749  ./RD9700Driver/Linux/qf9700.mod.c
db36914c23059cea830a3c66790da6b15bbe9cde5c4c5e6cab46286e273bfe1e  ./RD9700Driver/Linux/qf9700.mod.o
7443e3ea2caef9232c80ace57d684e7df25f10ebd21e226f948f94d1ae88b8b3  ./RD9700Driver/Linux/qf9700.o
8f944d2431248e42d6351c4193635f2feda09d3ec3456f9f63290b87c2f0910a  ./RD9700Driver/Linux/README
247a282ed42787fe306cfcd8e925829e15ad037fe6bd417b81e7cab18608ba29  ./RD9700Driver/MAC DRIVER/.DS_Store
b80a403ce986794ee660b7005b82b4e197db855dda279ee8b4954c9074e2a633  ./RD9700Driver/MAC DRIVER/i386/USBCDCNET.pkg
ca2809d4a4be3c7e9f1ab49936c7d520eb19402c2c0c9905be1aa7c3298d2a84  ./RD9700Driver/MAC DRIVER/ppc/USBCDCNET.pkg
cf4741b68d6b694817c57a833d5d6c74be1475e6950279362dbd1216d704634c  ./RD9700Driver/MAC DRIVER/RD9700  Mac OS 10.10 Driver.pkg
4f38be8beea70e3139326c60617fce2d4e450af5640b237402a2b6cfa264d5ea  ./RD9700Driver/MAC DRIVER/x86_64/USBCDCNET.pkg
8ad277cc5af5bcec3037162064fd2aa6263df48931e10c7350531be2a784f2b9  ./RD9700Driver/sr9700_android_2.6.35/Makefile
0f76341e7506d96ef988ce6c339375afeb17b6e9deb86823d5d4b254b0d55ebf  ./RD9700Driver/sr9700_android_2.6.35/sr9700.c
38c8051f82d180009ccfabd7da330ff8db56ba4ca103b805048fdbdbc02ddfdb  ./RD9700Driver/sr9700_android_2.6.35/sr9700.h
08418c29c5ea865fca36d256ac32bfb5a13d9d6d9e46212b737ec7dd80f3cc16  ./RD9700Driver/XP-WIN8-32/rd9700.cat
5b0b3f2b44d09971a5af8d79809ec38ede397df8f8e425a6a9b91cbb53082bb1  ./RD9700Driver/XP-WIN8-32/RD9700.inf
2136c78e8ef760bbf4ce8dccfc7940b3943f2022ded23da14fcb3f0bee2f73d8  ./RD9700Driver/XP-WIN8-32/RD9700.sys
087a0e9452024689e3ff042cb4e9a59596f4257731481ad3db1a01c3ec21dca8  ./RD9700Driver/XP-WIN8-64/rd9700.cat
3a08b1a191c26077e1d46e3c372530cf4cb7830c6cfe1189712ac3482221ad08  ./RD9700Driver/XP-WIN8-64/RD9700.inf
4255dd49fc4703360a76fc007f5e370b66a7c4234e8739ef814b3474fe9de046  ./RD9700Driver/XP-WIN8-64/RD9700.sys
6179f8783575c79ffad7c4d4d32730554394b47fe8a70440c9fee14269b6a19f  ./RD9700Driver/XP-WIN8Setup微软数字认证/Setup.exe
```


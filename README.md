# ADB for ARM
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-adb--arm-green.svg?style=flat)](https://android-arsenal.com/details/1/2232)

This is an *all-in-one* script to build the Android **adb** tool (*v. 1.0.31*) for **ARM architecture**. When executed, the script will download all the necessary files and it will run a custom makefile to build the adb.

References
--

 - [Android.ServerBox] *(which contains the most useful information)*
 - [XDA]
 - [StackOverflow]



Requirements
--
 - a Git client
 - an **ARM cross compile toolchain** (you can get one from [YOCTOproject])
 

Setup
--
The script should be ready to execute without any configuration, except for the *TOOLCHAIN* variable inside **makefile.sample**:

```
...
#TODO change TOOLCHAIN variable to your toolchain path 
TOOLCHAIN= /opt/poky/1.5/sysroots/x86_64-pokysdk-linux/usr/bin/arm-poky-linux-gnueabi/arm-poky-linux-gnueabi-

CC= $(TOOLCHAIN)gcc
LD= $(TOOLCHAIN)gcc
CXX=$(CC)
...
```

Run
--
```
sh adb-download-make.sh
```
If the script compile successfully, you will find the **adb** executable in your current directory. If something went wrong, feel free to open an issue with your error. **You can also use the pre-compiled ARM binary (adb-arm-binary)**.

Verify binary
--
 - Verify architecture
``` file adb-arm-binary```
 - Verify dependecies
``` objdump -x adb-arm-binary | grep NEEDED ```


[YOCTOproject]:http://downloads.yoctoproject.org/releases/yocto/yocto-1.5/toolchain/
[Android.ServerBox]:http://android.serverbox.ch/?p=1217
[XDA]:http://forum.xda-developers.com/showthread.php?t=1924492
[StackOverflow]:http://stackoverflow.com/questions/5904765/build-android-adb-for-arm-processor

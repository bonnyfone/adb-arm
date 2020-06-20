# ADB for ARM
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-adb--arm-green.svg?style=flat)](https://android-arsenal.com/details/1/2232)

This is an *all-in-one* script to build the Android **adb** tool (*v. 1.0.31*) for **ARM architecture**. When executed, the script will download all the necessary files and it will run a custom makefile to build the adb.

The current script is able to build the latest Android 4 branch. Building Android 5 or newer will require further modification. 
Even if old, the binary has been successfully used for installing APK's on Chrome OS 83.

References
--

 - [Android.ServerBox] *(which contains the most useful information)*
 - [XDA]
 - [StackOverflow]



Requirements
--
 - a Git client
 - an **ARM cross compile toolchain** providing an environment script. The script has been written for [YOCTOproject].
   For example, install
   [this toolchain](http://downloads.yoctoproject.org/releases/yocto/yocto-3.1/toolchain/x86_64/poky-glibc-x86_64-core-image-sato-aarch64-qemuarm64-toolchain-3.1.sh)
   for compiling for aarch64 on x86_64.
 

Setup
--
The script should be ready to execute without any configuration, except for the sourced environment inside **adb-download-make.sh**:

```
...
#TODO change to your toolchain path
source /opt/poky/3.1/environment-setup-aarch64-poky-linux
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
``` file adb```
 - Verify dependecies
``` objdump -x adb | grep NEEDED ```

License
----

```
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org/>
```

[YOCTOproject]:http://downloads.yoctoproject.org/releases/yocto/yocto-3.1/toolchain/
[Android.ServerBox]:http://android.serverbox.ch/?p=1217
[XDA]:http://forum.xda-developers.com/showthread.php?t=1924492
[StackOverflow]:http://stackoverflow.com/questions/5904765/build-android-adb-for-arm-processor

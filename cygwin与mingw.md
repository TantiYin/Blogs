title: cygwin与MinGW/msys
date: 2016-08-21 16:46
tags:
- 编程
- cygwin
- MinGW
- msys
categories:
- 编程笔记
---

# cygwin
cygwin是windows上运行的模拟的linux环境。  
可以为不想转移到linux平台的程序员提供linux的开发环境，包括gcc，gdb等开发工具集。  
cygwin提供cygwin1.dll来翻译posix api到win32api。所以，cygwin中开发的程序可以放心地使用posix api，开发出的程序可以不用修改源代码，只需重新编译就可完美运行于linux平台。

# MinGW/msys
MinGW是Minimalist GNU for Windows的缩写，又称mingw32，是将GCC编译器和GNU Binutils移植到Win32平台下的产物，包括一系列头文件（Win32API）、库和可执行文件。  
MinGW为开发win32程序但不想使用vs的程序员提供GNU开发体验。  
MinGW上开发程序，是可以直接调用win32api的，所以开发的是原生的win32程序，需要修改源代码才可以移植到linux下。  
MinGW提供了一个msys(minimal system)，是在windows上模拟的linux shell环境，方便使用MinGW工具集。

另有可用于产生32位及64位Windows可执行文件的MinGW-w64项目，是从原本MinGW产生的分支。如今已经独立发展。  
msys也有msys2项目，提供了更多功能，尤其是包管理器pacman。

# 总结：
如果是要在windows上开发linux可以运行的程序，推荐使用cygwin。  
如果只是开发windows应用，但是想使用GNU工具集，推荐使用MinGW-w64/msys2。

注意，msys2提供包管理器，所以不必单独安装MinGW-w64，而是安装完msys2后，通过pacman命令安装MinGW。  
msys2 pacman国外的源太慢，可以添加国内的源，[中科大的源](https://lug.ustc.edu.cn/wiki/mirrors/help/msys2)。

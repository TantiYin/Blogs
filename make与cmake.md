title: make与cmake
date: 2016-08-20 18:29
tags:
- 编程
- make
- cmake
categories:
- 编程笔记
---

# make
程序从源代码变成可执行程序，要经过编译，链接的处理，这个过程叫做构建。  
从前这些步骤都是程序员手动输入编译链接指令执行的。当源代码的规模变大后，这种手动的方式就变成噩梦。  
为了解决这个问题，程序员发明了make工具，能够自动化批处理执行构建过程。  
make工具依据makefile规则文件，进行构建。所以编写makefile也是程序员必备技能之一。

## make工具有几种：

* **GNU make**  
	GNU make仿照make的标准功能（通过clean-room工程）重新改写，并加入作者觉得值得加入的新功能，常和GNU编译系统一起被使用，是大多数GNU Linux安装的一部分。  
	当在其他平台使用GNU make时，它的名字通常会是gmake，因为make这个名字已经被本平台占用，GNU make不得不改变叫法。
* **BSD make**  
	是从Adam de Boor的制作的版本上发展成的。它编译目标的时候有并发计算的能力。它在FreeBSD，NetBSD和OpenBSD中不同程度的修改下存活了下来。
* **Microsoft nmake**  
	广泛应用于微软的Windows，微软的nmake不要与来自AT&T和贝尔实验室的Unix系统的nmake混淆。

## makefile的语法：
makefile是由一系列下述形式的规则所组成的。

```{bash}
target : prerequisites
[tab]command
[tab]…
[tab]…
```

上面第一行冒号前面的部分，叫做"目标"（target），冒号后面的部分叫做"前置条件"（prerequisites）；第二行必须由一个tab键起首，后面跟着"命令"（command）。
更详细的规则，请看文档。

# cmake
有了make之后，写makefile成了程序员的必备技能，但是手写比较困难，难免会出错，而且当软件要跨平台时，就要针对不同平台写不同的makefile，就更麻烦了。  
所以程序员发明了cmake，cmake依据CMakeLists.txt规则文件，可以生成不同平台的makefile，再由不同平台的make工具来构建。  
从此程序员就只需手写一份CMakeLists就可以了。写CMakeLists也成了程序员的必备技能之一了。

## cmake工具有几种：

* **cmake**  
	“CMake”这个名字是"cross platform make"的缩写。虽然名字中含有"make"，但是CMake和Unix上常见的“make”系统是分开的，而且更为高级。  
	Cmake并不直接建构出最终的软件，而是产生标准的建构档（如Unix的Makefile或Windows Visual C++的项目文件），然后再由相应平台make工具使用。  
	cmake所依据的规则文件叫做CMakeLists.txt
* **automake**
	GNU Automake是一种编程工具，可以产生供make程式使用的Makefile，用来编译程式。它是自由软件基金会发起的GNU计划的其中一项，作为GNU构建系统的一部分。automake所产生的Makefile符合GNU编程标准。 
	automake是由Perl语言所写的，必须和GNU autoconf一并使用。
* **qmake**  
	qmake是一个协助简化跨平台进行项目开发的构建过程的工具程序，Qt附带的工具之一 。qmake能够自动生成Makefile、Microsoft Visual Studio 项目文件 和 xcode 项目文件。不管源代码是否是用Qt写的，都能使用qmake，因此qmake能用于很多软件的构建过程。  
	qmake对应的CMakeLists叫做.pro文件。

## CMakeLists的语法：
这个大家先看文档吧。


## 最后的流程图：
![](http://static.oschina.net/uploads/space/2012/1102/210924_Gx9w_191887.jpg)

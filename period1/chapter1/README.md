当前比较流行的操作系统主要有：

* windows
* Linux
* MacOS

在日常的开发中，建议大家使用Linux作为开发环境，因为在工作中我们开发的程序大部分都是部署在Linux上运行的，学习Linux的基础知识还是很有必要的。本章主要介绍了Linux比较流行的一个发行版Ubuntu的日常使用。

# 1 Ubuntu系统安装

如果大家是首次使用Linux系统，建议大家使用虚拟机安装Ubuntu。常用的虚拟机软件主要有：VMWare workstation, VirtualBox，其中VMWare是一个商业的软件，virtualbox是开源的软件。使用哪个虚拟机软件来安装Ubuntu虚拟机系统都是可以的。关于安装的详细过程，大家可以自行百度，本文不详细描述, 只做一个大概的介绍。

主要的步骤是如下的几点：
1. 下载系统镜像文件，推荐大家使用清华镜像源进行下载，地址：https://mirrors.tuna.tsinghua.edu.cn/ubuntu-releases/16.04.6/, 下载其中.iso后缀的文件。其中有server(服务器版，没有桌面环境)和desktop(桌面环境)两个版本。初次使用推荐使用desktop版本。
2. 使用虚拟机安装的时候，需要选择磁盘镜像，然后手动的配置操作系统的硬件资源分配。

# 2 基本使用

对于Linux系统的操作使用，我们更多的使用命令来操作。安装完Ubuntu之后，就可以打开自带的Terminal工具，在该工具内我们就可以使用命令来进行使用Ubuntu系统了。

## 2.1 安装软件

常用的软件安装方式有如下两种：

* 使用自带的apt工具进行安装
* 下载.deb包，然后使用dpkg工具进行手动安装, 或者使用gdebi工具进行安装(推荐使用gdebi工具进行手动下载的包的安装)

apt工具是Ubuntu系统提供的一个包管理工具，使用该工具可以安装大部分常用的软件。apt会从软件源下载一个软件包的列表到本地, 列表中记录了可以软件包的信息。另外，还可以添加PPA安装源，安装一些不在apt软件源中的软件。如果我们想要安装一个软件，需要apt能够知道这个包所在的位置，然后才能将其进行下载，如果apt无法确定软件的位置就无法下载，此时可以我们手动的配置一个PPA软件源，这样apt就能找到我们需要的软件了。

## 2.2 常用的文件操作命令

touch, rm, find, locate, whereis, 

## 2.3 常用的目录操作命令

mkdir, rm, mv, cp, tar

## 2.4 常用的文本处理命令

vim，sed, cut, tr, awk, grep等工具。

# 参考文献

1.《Ubuntu Linux操作系统》张金石著。 
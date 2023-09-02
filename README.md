# Linux基础入门

1. ### linux简介

   - linux为一个操作系统、位于软硬件交界处，起着管理计算机软硬件、管理系统资源的功能。

2. ### 基本概念及操作

   - 终端：linux提供了一个叫终端模拟器的程序（Terminal），可以在图形界面中实现在一个窗口中实现用户输入和显示输出。本课程使用的终端模拟器为xfce-terminal。
   - Shell（壳）：“提供给使用者使用界面”的软件（命令解析器）；普遍意义上的shell就是可以接受用户输入命令的程序。
   - 重要快捷键：【Tab】为命令、参数等补全；【Ctrl+C】为强行终止程序；【up】为恢复之前输入过的命令。
   - touch命令为创建文件；man命令可以调用手册；--help查看参数具体作用，如touch --help

3. ### 用户及文件权限管理

   *Linux可以多用户登录，不同用户的文件是放在同一个物理磁盘甚至同一个目录里，但是由于Linux的用户管理和权限机制，不同用户不可以轻易查看、修改彼此的文件。*

   - whoami：打印当前有效的用户名称
   - root账户拥有整个系统至高无上的权限，创建用户需要root权限，用到sudo命令，如sudo adduser lilei；
   - 切换登录用户命令：su -l lilei;
   - 退出当前用户：exit命令或者【Ctrl+D】；
   - 删除用户：sudo deluser lilei --remove-home;
   - ls命令用来显示当前目录下的文件；
   - 变更权限：chmod 600 iphone11;600为以二进制表示权限rwx；
   - 给用户sudo权限：sudo usermod -G sudo loutest；

4. ### 目录结构及文件基本操作

   *windows以存储介质为主，linux以树形目录结构的形式来构建整个系统，每一个目录不仅可以使用本地磁盘分区的文件系统，也可以使用网络上的文件系统。*

   - cd命令切换目录；cd ..进入上一级目录；cd ~进入home目录。

   - linux文件的基本操作:

     - touch命令创建空白文件；
     - mkdir命令创建空白目录，使用 -p参数可以同时创建父目录，如 mkdir -p father/son/grandson
     - cp命令复制一个文件到指定目录；
     - 复制一个目录要加上-r，如 cp -r father family
     - rm命令删除一个文件，rm -f 为强制删除，删除目录用rm -r family，也可以加f强制删除；
     - mv命令移动文件、重命名文件；
     - 查看文件：cat命令，加-n参数显示行号；
     - file命令用于查看文件的类型；
     - keil命令杀死进程，如 sudo kill -9 934；

     *轻松一刻：xeyes命令可以召唤一双眼睛盯着你*

5. ### 文件打包与解压缩

   - zip压缩打包程序

     ```
     cd /home/shiyanlou
     zip -r -q -o shiyanlou.zip /home/shiyanlou/Desktop
     du -h shiyanlou.zip
     file shiyanlou.zip
     ```

   - 使用unzip命令解压缩zip文件

   - tar打包

6. ### linux下软件安装

   *linux上的软件安装主要有4种方式：在线安装；从磁盘安装dep软件包；从二进制软件包安装；从源代码安装*

   - 如sudo apt-get install w3m;APT是Advanced Packaging Tool(高级包装工具)的缩写，APT可以自动下载，配置，安装二进制或者源代码格式的软件。
   - 重新安装：sudo apt-get --reinstall install <packagename>
   - 更新软件源：sudo apt-get update
   - 升级没有依赖问题的软件包：sudo apt-get upgrade
   - 卸载：sudo apt-get remove w3m
   - 使用dpkg本地安装：sudo dpkg -i xxxxxx.deb


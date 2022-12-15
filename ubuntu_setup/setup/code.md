# 常用命令整理

# Ubuntu操作系统不同于Windows，基本上命令行可以完成所有操作，而纯命令行会极大提升工作效率，所以熟悉命令极为重要。

## 一般操作  
### **pwd**  
显示当前的工作目录/路径  
  
### **cd**  
改变目录，用于输入需要前往的路径/目录  
有些特殊命令也很常用：  
> `cd ..`&nbsp;//表示进入上层目录  
> `cd -`&nbsp;//表示返回上一次的目录  
> `cd ~`&nbsp;//进入主目录，即`/home/用户名`的简写  
### **ls**  
显示当前目录下的文件（不包括隐藏文件和缓存文件等）  
### **ll**  
以列表形式显示当前路径下的所有文件的详细信息（包括隐藏文件和缓存文件等）  
### **mkdir**  
创建目录，后面接上directory的名字。  
> `mkdir hahaha`&nbsp;//创建一个“哈哈哈”目录  
### **rm**  
删除文件，后面接上要删除的文件名。删除文件夹的命令如下：
> `rm -d 目录名`&nbsp;//删除一个空目录  
> `rm -r 目录名`&nbsp;//删除一个非空目录  

rm [选项] 文件名
> `-f`&nbsp;//强力删除，不要求确认  
> `-i`&nbsp;//每删除一个文件或进入一个子目录都要求确认  
> `-I`&nbsp;//在删除超过三个文件或者递归删除前要求确认  
> `-v`&nbsp;//显示删除结果  

如果无法删除文件夹，执行：  
> `sudo rm -rf 文件夹名`  

还是不行，就用：
> `sudo chmod 777 文件夹名`  
> `sudo rm -rf 文件夹名`  
### **touch**  
创建任意格式的文件，包括源代码、文本等等，通过后缀来决定。  
> `touch hello_world.py`&nbsp;//创建hello_world的python源代码文件  
### **cp**  
复制命令，通常格式为：  
> `cp -? <源文件/源目录> <目的目录>`&nbsp;//第一个"-?"表示参数，出发地在左，目的地在右  

如果想把某目录下所有文件都复制，可以使用参数-r  
> `cp -r xxx/ xx`&nbsp;//把xxx目录下的所有资源都复制到xx目录中  
### **mv**  
移动+重命名命令，格式类似cp命令  
> `mv -? <源文件/源目录> <目的目录>`&nbsp;//第一个"-?"表示参数，出发地在左，目的地在右  
移动文件可以分为以下三种情况：  
> `mv a.txt b.txt`&nbsp;//出发地和目的地同一路径，名称改变，是重命名  
> `mv ~/目录1/a.txt ~/目录2`&nbsp;//出发地和目的地不是同一路径，名称不变，是移动  
> `mv ~/目录1/a.txt ~/目录2/b.txt`&nbsp;//出发地和目的地不是同一路径，名称改变，是移动+重命名  
### **gedit**  
在煮面临时新建一个text editor（文本编辑器）显示文件夹的内容，并且支持修改，按**ctrl+c**退出文件显示。  
> `gedit <文件名>`  
### **cat**  
在终端打印出文本内容。  
> `cat <文件名>`&nbsp;//在终端内部打印，和gedit相区分  
### **解压缩**  
.tar文件
> `tar -xvf FileName.tar`    

.gz文件  
> `gunzip FileName.gz`&nbsp;//解压1  
`gzip -d FileName.gz`&nbsp;//解压2  

.tar.gz文件、。tgz文件  
> `tar -zxvf FileName.tar.gz`  

.zip文件  
> `unzip FileName.zip`  

.rar文件  
> `rar x FileName.rar`&nbsp;//需要下载rar  

### **du**
查看目录及文件占用磁盘容量。  
> `du -sh`&nbsp;//查看当前目录总共占用容量，不单独列出各子项占用容量。
 `du -lh --max-depth=1`&nbsp;//查看当前目录下一级子文件和子目录占用的磁盘容量。  
 ### **code/nano/vi/vim**  
 使用四种编辑器，打开或者新建一个源代码文件。  
 ### **apt/apt-get**  
 更推荐使用apt命令而不是apt-get命令，它的命令更精简而且易用。
 >`sudo apt install <软件名>`&nbsp;//安装软件最简单的方式  
 `sudo apt list`&nbsp;//查看所有已安装的软件列表  
 `sudo apt search <软件名>`&nbsp;//搜索某个软件  
 `sudo apt remove <软件名>`&nbsp;//删除某个软件  
 `sudo apt purge <软件名>`&nbsp;//删除某个软件及配置文件  

以及我们常用的更新相关指令  
>`sudo apt update`  
`sudo apt upgrade`  
### **dpkg**  
包管理工具。  
首先是下载功能。先在官网下载软件的deb格式安装包，然后cd到下载文件夹，打开terminal（终端）输入：  
>`dpkg -i <.deb后缀的软件名>`&nbsp;//i 表示 install  
### **kill**  
结束指定进程时使用，就比如某个软件不响应了，这时候kill就相当于windows系统中的任务管理器中的“结束进程”按钮。我们只要指定进程的编号（ID#)  
>`kill <ID#>`&nbsp;//结束编号为<ID#>的进程  
### **ps**  
查看所有进程：  
>`ps -A`  

查看所有包含其他使用者的进程：
>`ps -aux`  

关键字查找某个进程，这个办法用于结束指定的进程。  
>`ps -ef | grep <关键字>`  
### **grep**  
Linux grep 命令用于查找文件里符合条件的字符串。
### **find**  
用于查找目录中的文件。   
### **ln**
插入链接。  
### **chmod**  
改变权限。


原文链接：[Ubuntu常用命令 总结整理](https://zhuanlan.zhihu.com/p/392986700)  
原文链接：[ubuntu如何删除文件夹？](https://zhuanlan.zhihu.com/p/136747577)  
原文链接：[Ubuntu 常用解压与压缩命令](https://blog.csdn.net/songbinxu/article/details/80435665)  
原文链接：[linux 查看当前目录占用空间](https://blog.csdn.net/db2china/article/details/84032137)
# 关闭桌面图形

## 很多帖子都是缺斤少两的，最终整合起来实测OK的如下  

### 首先修改Grub配置文件  
>`sudo vim /etc/default/grub`  

然后定位到：  
>`GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"`  

其中的 `quiet splash` 改为 `text`  
>`GRUB_CMDLINE_LINUX_DEFAULT="text"`  

然后执行  
>`sudo update-grub`  
`sudo systemctl set-default multi-user.target`  
`sudo reboot`  

卸载gnome3
>`sudo snap remove gnmoe`  
`sudo snap remove store`  //卸载图形商店  
`sudo apt remove snaped`  

接下来，就可以享受纯命令之旅了！

原文链接：[Ubuntu20.04 桌面版正确的关闭并卸载图形界面（实测）](https://blog.csdn.net/zisain/article/details/108344022?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~Rate-1-108344022-blog-107140558.pc_relevant_aa_2&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2~default~CTRLIST~Rate-1-108344022-blog-107140558.pc_relevant_aa_2&utm_relevant_index=1)
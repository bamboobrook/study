# 安装clash代理

## Ubuntu配置clash系统代理，并自动更新订阅链接

### 1. 下载clash并解压
- [官方网站](https://link.zhihu.com/?target=https%3A//github.com/Dreamacro/clash/releases)下载**clash-linux-amd64-v1.12.0.gz**，也可以下载最新版，前缀是clash-linux-amd64即可，也可复制链接，利用命令下载
> `wget https://github.com/Dreamacro/clash/releases/download/v1.12.0/clash-linux-amd64-v1.12.0.gz`
- 解压下载的文件
> #&nbsp;解压  
> `gunzip clash-linux-amd64-v1.12.0.gz`  
> #&nbsp;将clash-linux-amd64-v1.12.0改名为clash  
> `mv clash-linux-amd64-v1.12.0 clash`  
> #&nbsp;在此目录下创建文件夹  
> `mkdir Clash`   
> #&nbsp;移动clash到文件夹Clash  
> `mv clash ./Clash`  
### 2. 进入新建的Clash文件夹，下载config.yaml和Country.mmdb  
> #&nbsp;进入新建的Clash文件夹  
> `cd Clash`  
> #&nbsp;下载clash配置文件config.yaml （从代理商那里复制订阅链接）  
> `wget -O config.yaml [订阅链接]`  
### 3. 启动clash  
> - 执行 `./clash -d .` 即可启动clash，如果提示权限不足，先执行 `chmod +x clash`，再执行 `./clash -d .` 成功后**保持此终端打开**  
> - 打开配置文件config.yaml，给它设置一个密码：  
> &nbsp;&nbsp;&nbsp;`# RESTful API 的口令 secret:'123456'`  
> - 打开系统设置，选择网络，点击网络代理右边的按钮，选择手动，填写HTTP和HTTPS代理为 127.0.0.1:7890，填写Socks主机为 127.0.0.1:7891，即可启用系统代理。  
> - 访问[Clash Dashboard](clash.razord.top/)可以切换节点、测试延迟等操作，启动页面输入密码`123456`即可。  
### 4. 配置开机启动  
> #&nbsp;打开终端，获取权限   
> `sudo su root`  
> #&nbsp;输入密码  
> #&nbsp;创建service文件  
> `touch /etc/systemd/system/clash.service`  
> #&nbsp;编辑service文件  
> `vim /etc/systemd/system/clash.service`  
> #&nbsp;编辑如下文本:  
`[Unit]`  
`Description=clash daemon`  
`[Service]`  
`Type=simple`  
`User=root`  
`ExecStart=/home/username/Downlads/Clash/clash -d /home/username/Downloads/Clash/`  
`Restart=on-failure`  
`[Install]`  
`WantedBy=multi-user.target`  

补充一下操作命令
> 使用**vim**进入文本后，按**i**开始编辑文本  
> 退出编辑模式，按**ESC**，然后按如下按键退出**vim**  
> **:q!** 不保存文件，强制退出**vim**  
> **:w** 保存文件，不退出**vim**  
> **:wq** 保存文件，退出**vim**  
### 5. 设置clash为开机启动项  
> `sudo systemctl daemon-reload`  
> `sudo systemctl enable clash`  
> `sudo systemctl start clash`  
> `sudo systemctl status clash`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;#&nbsp;查看clash运行状态  


原文链接：[ubuntu配置clash系统代理](https://zhuanlan.zhihu.com/p/430035973)
# 无人值守Linux安装iso
## 实验要求
- [x]定制用户名和默认密码
- [x]定制安装OpenSSH Server
- [x]安装过程禁止自动联网更新软件包
- [][PXE](https://en.wikipedia.org/wiki/Preboot_Execution_Environment) 启动和无人值守同时安装 Debian & Ubuntu
- []如何配置无人值守安装iso并在Virtualbox中完成自动化安装。
- []Virtualbox安装完Ubuntu之后新添加的网卡如何实现系统开机自动启用和自动获取IP？
- []如何使用sftp在虚拟机和宿主机之间传输文件？
## 实验环境
Virtualbox+[Ubuntu 18.04.4 Server 64bit](https://mirror.tuna.tsinghua.edu.cn/ubuntu-cdimage/releases/18.04/release/) 
## 实验步骤
1. 先有人值守安装一个ubuntu，步骤如下。  
安装virtualbox。下载ubuntu-18.04.4镜像并安装，安装过程中已设置用户名和默认密码，如下图选择安装了OpenSSH Server，安装后备份纯净系统。
* 安装ubuntu，有一个自动更新，如果选择，每次一打开系统就自动更新了，由于做作业不选择，生产环境下选择是错误行为
![](images/openssh-choose.png)
如下图所示安装成功。
![](images/userset.png)
2. 启动ubuntu,```ifconfig -a```查看host-only的ip地址,此处得到：192.168.56.107.
* 如果网卡未启动，输入以下命令手动启动并动态获取ip以后再查看。
```
sudo ifconfig enp0s8 up 
sudo dhclient enp0s8
```
![](images/ip-get.png)
## 实验问题

server版的ubuntu如何从命令行挂载Virtualbox的虚拟光驱中镜像？
server版的ubuntu如何安装Virtualbox增强功能套件？
server版的ubuntu如何从命令行挂载Virtualbox的共享目录？
## 参考文献

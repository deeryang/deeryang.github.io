---
title : windows与linux系统文件互访
tags  : linux
categories: linux
---

### Windows10系统与Win10商店Ubuntu子系统文件互访

Windows10商店中可以直接下载Ubuntu子系统。Windows10系统和Ubuntu系统之间的文件如何互相访问呢？

<!--more-->

#### 在Windows10系统下访问Ubuntu系统中的文件
在Microsoft Store安装下载Ubuntu后，Ubuntu系统的目录位置为
`C:\Users\admin\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc\LocalState\rootfs`，
目录结构为：

```bash
.
├── bin
├── boot
├── dev
├── etc
├── home
├── init
├── lib
├── lib64
├── media
├── mnt
├── opt
├── proc
├── root
├── run
├── sbin
├── snap
├── srv
├── sys
├── tmp
├── usr
└── var
```

#### 在Ubuntu系统下访问Windows10系统中的文件
运行Ubuntu系统，要访问Windows10中的文件，只需要将目录切换至`/mnt/`路径中即可。
``` bash
yang@Yang:/$ cd /mnt/
yang@Yang:/mnt$ ls
c  d  e
```
其中，`c`、`d`、`e`为Windows10系统中对应的盘符。


### Windows10系统与阿里云服务器linux系统文件互访
在阿里云购买服务器后，下载Xshell，通过ssh进行连接。
文件互访有两种方式。

#### 第一种：安装lrzsz
以CentOS系统为例，在远端服务器上安装`lrzsz`，命令为：
```
yum install lrzsz
```
- 将本地文件上传到远端CentOS上时，先在Xshell中输入命令`rz`，然后在弹出的框中选择要上传的文件。
![image1](/images/04/image1.PNG)

- 将远端CentOS中的文件下载到本地Windows时，在Xshell中输入命令`sz 文件名`，然后在弹出的窗口中选择保存的位置即可。
![image2](/images/04/image2.PNG)

#### 第二种：安装Xftp
Xftp常和Xshell配套使用，下载安装Xftp后，直接按提示操作即可。先点击Xshell上的新建文件传输，在弹出的窗口中可以进行远端CentOS系统和本地Windows系统之间的文件传输。
![image3](/images/04/image3.png)
![image4](/images/04/image4.png)

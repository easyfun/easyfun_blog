Title: mint 18开发环境搭建
Date: 2018-01-08 14:00:00
Modified: 2018-01-08 14:00:00
Category: 软件工程
Tags: linux mint
Slug:
Author: easyfun


## 1. 安装mint 18

### xp下无法硬盘安装，使用U盘启动安装。

在mint官网下载iso镜像

利用ultraiso制作U盘启动，先往U盘[写入]iso镜像文件，使用raw方式，写入完成之后，[便携启动]写入[syslinux]系统引导文件

U盘启动安装mint 18，遇到对话框显示不全时，光标移动到对话框上，按住ctrl+shift+alt+鼠标左键+移动鼠标，可以对话框


### 修改工作源为阿里云

Ubuntu/Mint更换阿里云源

    sudo cp /etc/apt/sources.list /etc/apt/sources.list.bak #备份
    sudo vim /etc/apt/sources.list #修改

    #阿里云源
    deb http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse
    deb http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse
    deb http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse
    deb http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse
    deb http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-security main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-updates main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-proposed main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ trusty-backports main restricted universe multiverse

    sudo apt-get update #更新列表


### 更新系统
安装Linux Mint 17后要做的20件事
https://linux.cn/article-3353-1.html

### windows和linux系统时间不一致修复
https://www.cnblogs.com/shareidea/p/5465306.html

在Windows下的解决方法：

1. 打开cmd
2. 执行命令Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1

## 2. 安装firefox

更新firefox

安装firefox中文包

    sudo apt-get install firefox-locale-zh-hans

安装adobe flash插件

官网下载flash插件解压，把libflashplayer.so复制到/usr/lib/mozilla/plugins/

    sudo cp ./libflashplayer.so /usr/lib/mozilla/plugins/

## 3. 安装sublime text3

安装sublime text3

http://www.linuxidc.com/Linux/2017-06/144432.htm

安装中文输入支持

https://www.cnblogs.com/wangkongming/p/4302642.html

设置

## 4. locate命令的使用

https://www.cnblogs.com/flysnail/archive/2012/05/16/2504266.html

## 5. 安装jdk8


## 6. 安装eclipse

https://www.jianshu.com/p/730db54aefab

## 7 安装mysql

安装mysql:sudo apt-get install mariadb-client,mariadb-server

https://imcn.me/html/y2016/27689.html

sudo apt-get install mariadb-client,mariadb-server安装首次登陆设置

http://www.err123.com/2017/08/03/error-1698-28000-access-denied-for-user-root-localhost/?lang=zh

原因:mysql启用plugin功能

解决:

    停止服务 sudo service mysql stop
    安全模式启动 mysqld_safe --skip-grant-tables &
    无密码登陆 mysql -u root
    查看plugin状态 select host,user,plugin from mysql.user;
    更改plugin状态 UPDATE mysql.user SET authentication_string=PASSWORD('easyfun'), PLUGIN='mysql_native_password' WHERE USER='root';
    重启mysql sudo service mysql restart
    登陆 mysql -u root -p
    查看服务器信息 status;

mysql启动命令:

    启动mysql sudo service mysql start
    重启mysql sudo service mysql restart
    停止mysql sudo service mysql stop



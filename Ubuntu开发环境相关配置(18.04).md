# Ubuntu开发环境相关配置(18.04)  
* ***anaconda安装和环境配置***  
* ***pycharm专业版的安装和激活***  
* ***安装显卡驱动***  


**anaconda安装和环境配置**  

-----安装   
1，到官网上下载安装包(也可以复制下载链接通过wget下载)  
2，运行指令sh Anaconda3-2018.12-Linux-x86_64.sh  
3，同意协议，选择安装路径  

-----配置  
1，运行指令：sudo gedit /etc/profile  
2，运行指令：export PATH=/opt/anaconda3/bin:$PATH(选择Anaconda安装的路径)  
3，运行指令：source /etc/profile  

**pycharm专业版的安装和激活**

1，到pycharm官网下载专业版  
2，点击[这里](https://shimo.im/docs/CjyjvCyPTqWRHV3X/read)，复制里面的激活码进行激活  

**显卡驱动安装**

-----禁用nouveau  
##### 禁用原因:nouveau是第三方为NVIDIA显卡开发的一个开源3D驱动，没得到NVIDIA的认可与支持。  
##### 个人用户除了想让正常显示图形界面外很多时候还需要一些3D特效，Nouveau多数时候并不能完成，而用  
##### 户在安装NVIDIA官方私有驱动的时候Nouveau又成为了阻碍，不干掉Nouveau安装时总是报错。  
1，运行指令：sudo gedit /etc/modprobe.d/blacklist-nouveau.conf  
2，运行指令：blacklist nouveau 和 options nouveau modeset=0(将nouveau加入黑名单)  
3，运行指令：sudo update-initramfs -u 和 sudo reboot(使禁用生效然后重启)  
4，运行指令：lsmod | grep nouveau(验证，如不返回内容即生效)   

-----安装显卡驱动  
1，运行指令：sudo apt-get remove --purge nvidia*(ppa源文件卸载)  
2，运行指令：ubuntu-drivers devices(查询电脑最适合的显卡驱动版本，cuda10.2最好安装440【未验证】)  
3，运行指令：sudo add-apt-repository ppa:graphics-drivers/ppa 和 sudo apt-get update 和  
sudo apt-get install nvidia-driver-435(此处数字要对应上面查询到的版本号) 和  
sudo apt-get install mesa-common-dev  
4，运行指令： sudo reboot(重启)  
5，运行指令： nvidia-smi(验证，有内容即验证通过)  







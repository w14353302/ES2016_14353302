# ES2016_14353302
***
#Description(DOL框架描述)
 1. 配置DOL之前首先下载VMWARE虚拟机，然后使用虚拟机安装Ubuntu，这两步都是根据ppt给出的教程来完成的，没有特别要注意的地方，只是感觉装个乌邦图要好久的样子。
 2. 装好Ubuntu之后就开始配置DOL了，首先安装一些必要的环境：
$sudo apt-get update在执行这一步时出现了error:"could not get lock /var/lib/dpkg"百度得知是因为有另外一个程序正在运行，导致资源被锁不可用。而导致资源被锁的原因可能是上次运行安装或更新时没有正常完成，进而出现此状况，解决的办法其实很简单：
在终端中敲入以下两句sudo rm /var/cache/apt/archives/lock，sudo rm /var/lib/dpkg/lock再进行安装就可以了
接着继续安装一些环境，如下所示，在这一步骤中没有出现任何错误
$sudo apt-get install ant  
$sudo apt-get install openjdk-7-jdk
$sudo apt-get install unzip
***
#How to install(DOL安装笔记)
***
#Experimental experience(实验感想.实验心得)

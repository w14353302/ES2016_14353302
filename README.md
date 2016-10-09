# ES2016_14353302
***
#Description(DOL框架描述)
 1. 配置DOL之前首先下载VMWARE虚拟机，然后使用虚拟机安装Ubuntu，这两步都是根据ppt给出的教程来完成的，没有特别要注意的地方，只是感觉装个乌邦图要好久的样子。
 2. 装好Ubuntu之后就开始配置DOL了，首先安装一些必要的环境：$sudo apt-get update在执行这一步时出现了error:"could not get lock/var/lib/dpkg"百度得知是因为有另外一个程序正在运行，导致资源被锁不可用。而导致资源被锁的原因可能是上次运行安装或更新时没有正常完成，进而出现此状况，解决的办法其实很简单：在终端中敲入以下两句,再进行安装就可以了sudo rm /var/cache/apt/archives/lock sudo rm /var/lib/dpkg/lock
 3. 接着继续安装一些环境，如下所示，在这一步骤中没有出现任何错误
$sudo apt-get install ant  
$sudo apt-get install openjdk-7-jdk
$sudo apt-get install unzip
 4. 解压文件，这一步直接照着ppt来的没有出现什么错误
首先新建dol的文件夹 $mkdir dol，接着将dolethz.zip解压到 dol文件夹中$unzip dol_ethz.zip -d dol，最后解压systemc$tar -zxvf systemc-2.3.1.tgz
 5. 编译systemc，这一步也是照着ppt进行的，最后运行configure之后的结果和给出的截图一样，在此就不列出来了。
首先解压后进入systemc-2.3.1的目录下$cd systemc-2.3.1，接着新建一个临时文件夹objdir：$mkdir objdir。然后进入该文件夹objdir：$cd objdir最后运行configure(能根据系统的环境设置一下参数，用于编译)$../configure CXX=g++ --disable-async-updates
接着编译$sudo make install编译完后文件目录如ppt记录当前的工作路径：/home/wangwenjing14353302/systemc-2.3.1
 6. 编译dol，这一步也是照着ppt来的在打开build_zip.xml文件后发现此文件无法修改，在终端输入sudo gedit build_zip.xml即可修改
首先进入刚刚dol的文件夹$cd ../dol修改build_zip.xml文件
找到下面这段话，就是说上面编译的systemc位置在哪里，
<property name="systemc.inc" value="YYY/include"/>
<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>
把YYY改成上页pwd的结果（注意，对于  64位 系统的机器，lib-linux要改成lib-linux64）
 7. 编译dol
然后是编译$ant -f build_zip.xml all
最后结果成功显示build successful
但是在运行第一个例子$ant -f runexample.xml -Dnumber=1的时候一直报错，照着给出的Q&A也没有解决，在网上百度原因是要设置一下JAVA的环境变量，但是设置之后也还是有错，浪费了不少时间，所以只能是放弃，选用TA给出的配置好的ubuntu




#How to install(DOL安装笔记)

#Experimental experience(实验感想.实验心得)

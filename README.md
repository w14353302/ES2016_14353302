# ES2016_14353302
***
# Description(DOL框架描述)
* Distributed Operation Layer : The distributed operation layer (DOL) is a software development framework to program parallel applications. The DOL allows to specify applications based on the Kahn process network model of computation and features a simulation engine based on SystemC. Moreover, the DOL provides an XML-based specification format to describe the implementation of a parallel application on a multi-processor systems, including binding and mapping.DOL consists of basically three parts:

1. DOL Application Programming Interface: The DOL defines a set of computation and communication routines that enable the programming of distributed, parallel applications for the SHAPES platform. Using these routines, application programmers can write programs without having detailed knowledge about the underlying architecture. In fact, these routines are subject to further refinement in the hardware dependent software (HdS) layer.
2. DOL Functional Simulation: To provide programmers a possibility to test their applications, a functional simulation framework has been developed. Besides functional verification of applications, this framework is used to obtain performance parameters at the application level.
3. DOL Mapping Optimization: The goal of the DOL mapping optimization is to compute a set of optimal mappings of an application onto the SHAPES architecture platform. In a first step, XML based specification formats have been defined that allow to describe the application and the architecture at an abstract level. Still, all the information necessary to obtain accurate performance estimates is contained.

# How to install(DOL安装笔记)
1. 配置DOL之前首先下载VMWARE虚拟机，然后使用虚拟机安装Ubuntu，这两步都是根据ppt给出的教程来完成的，没有特别要注意的地方，只是感觉装个乌邦图要好久的样子。  
2. 装好Ubuntu之后就开始配置DOL了，首先安装一些必要的环境： 
$sudo apt-get update  
在执行这一步时出现了error:"could not get lock/var/lib/dpkg"  
百度得知是因为有另外一个程序正在运行，导致资源被锁不可用。而导致资源被锁的原因可能是上次运行安装或更新时没有正常完成，进而出现此状况，解决的办法其实很简单： 
在终端中敲入以下两句,再进行安装就可以了  
$sudo rm /var/cache/apt/archives/lock
$sudo rm /var/lib/dpkg/lock
3. 接着继续安装一些环境，如下所示，在这一步骤中没有出现任何错误  
$sudo apt-get install ant  
$sudo apt-get install openjdk-7-jdk   
$sudo apt-get install unzip  
4. 下载文件   
$sudo wget <http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz>  
$sudo wget <http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip>
5. 解压文件，这一步直接照着ppt来的没有出现什么错误  
  首先新建dol的文件夹:$mkdir dol，  
  接着将dolethz.zip解压到dol文件夹中:
  $unzip dol_ethz.zip -d dol，  
  最后解压systemc:$tar -zxvf systemc-2.3.1.tgz
6. 编译systemc，这一步也是照着ppt进行的，最后运行configure之后的结果如下：
![图片1.png](https://ooo.0o0.ooo/2016/10/09/57fa5c55707bd.png)  
首先解压后进入systemc-2.3.1的目录下：
$cd systemc-2.3.1，  
接着新建一个临时文件夹objdir： $mkdir objdir。  
然后进入该文件夹objdir： 
$cd objdir  
最后运行configure(能根据系统的环境设置一下参数，用于编译)  $../configure CXX=g++ --disable-async-updates  
接着编译：
$sudo make install  
编译完后文件目录如下：  
![图片2.png](https://ooo.0o0.ooo/2016/10/09/57fa5cf9a280e.png)  
记录当前的工作路径：/home/wangwenjing14353302/systemc-2.3.1
7. 编译dol，这一步也是照着ppt来的在打开build_zip.xml文件后发现此文件无法修改，在终端输入：
$sudo gedit build_zip.xml即可修改。  
首先进入刚刚dol的文件夹$cd ../dol修改build_zip.xml文件,找到下面这段话，就是说上面编译的systemc位置在哪里，  
property name="systemc.inc" value="YYY/include"/    
property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/    
把YYY改成上页pwd的结果
8. 编译dol
然后是编译:  
$ant -f build_zip.xml all  
最后结果成功显示build successful
9. 但是在运行第一个例子：  
$ant -f runexample.xml -Dnumber=1  
的时候一直报错如下：  
![图片3.png](https://ooo.0o0.ooo/2016/10/09/57fa5cf96c49f.png)  
照着给出的Q&A也没有解决，在网上百度原因是要设置一下JAVA的环境变量，但是设置之后也还是有错，浪费了不少时间，所以只能是放弃，选用TA给出的配置好的ubuntu

# Experimental experience(实验感想.实验心得)
1. 这是实验首先是在配置DOL的基础上进行的，关于DOL的配置照着ppt应该是不难的，前面几步也都很开心的完成了，但最后一步还是没跑成功，在网上查了很久照着提示也都尝试过，国庆大概搞了一天也没有搞好，只好用师兄给出的配置好的，心好累！！！
2. 然后选择使用Git进行版本控制，并将仓库托管在 Github 上。Github 是一个基于 Git 的在线仓库，提供了网页供用户管理仓库，本次实验首先就是在github.com上建立新的仓库，建立README文件，然后在虚拟机上跑代码$ sudo apt-get install git来安装git,把github上的仓库拷贝到虚拟机，然后把README.md文件添加到仓库中去，之后就可以在虚拟机修改README.md文件,然后输入相应的语句向远程仓库提交本次修改，我理解的实验流程大概应该是这样吧，不知道对不对，其实现在我也不是很清楚有点懵。对于实验文档给出的版本控制是什么也不是很了解，然后那个Git教程和原理也都看了，好像没看懂的样子，可能以后做多了实验就了解了吧。实验文档上给出了Git的安装教程，然后是clone了github上的仓库，然后可以在虚拟机上远程操作自己的仓库。
3. 对于本次实验了解了新的标记语言Markdown，挺简单易懂而且排版很好，使用起来也比较方便

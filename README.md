#ROS配置过程   
.因为自己在第一次配置ROS的时候忘记截图，为了实验效果所以重新跑了一遍指令，截到的图有些东西已经下载完了所以会有不同   
1.setup sources list   
输入指令：sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'   
2.Set up my keys   
输入指令：sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116   
运行结果：   
![图片1.png](https://ooo.0o0.ooo/2016/11/11/58256bfa9e71b.png)     
3.Installation   
输入指令：sudo apt-get update   
运行结果：   
![图片2.png](https://ooo.0o0.ooo/2016/11/11/58256c2fb8ae0.png)       
4.Desktop-Full install   
输入指令：sudo apt-get install ros-jade-desktop-full   
运行结果：   
![图片3.png](https://ooo.0o0.ooo/2016/11/11/58256c2fc4ee5.png)   
![图片4.png](https://ooo.0o0.ooo/2016/11/11/58256c2fc7b84.png)   
![图片5.png](https://ooo.0o0.ooo/2016/11/11/58256c2fecd0a.png)     
5.find available packages   
输入指令：apt-cache search ros-jade   
运行结果：   
![图片6.png](https://ooo.0o0.ooo/2016/11/11/58256c30eefa3.png)
6.initialize rosdep   
输入指令：echo "source /opt/ros/jade/setup.bash" >> ~/.bashrcsource ~/.bashrc   
7.change the environment of my current shell   
输入指令：sudo apt-get install python-rosinstall   
8.getting rosinstall   
输入指令：sudo apt-get install python-rosinstall   
运行结果：   
![图片7.png](https://ooo.0o0.ooo/2016/11/11/58256c2fd3f11.png)   
#二.配置完成后，重启虚拟机，运行指令   
 1.运行指令roscore跑出结果，截图如下：   
![图片8.png](https://ooo.0o0.ooo/2016/11/11/58256c2fe02d1.png)   
![图片9.png](https://ooo.0o0.ooo/2016/11/11/58256c2fec2ea.png)   
#三．实验感想   
这次实验主要是体验了一番ros的配置过程，感觉并不是很好。每一步都是照着教程来写的。没有遇到太大的问题，但是也不是很理解自己在干什么，有什么意义，所以比较懵逼。   


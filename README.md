# 一.改完的*.dot截图   
1. 修改example2后的example2.dot截图如下：   
![example2.dot.png](https://ooo.0o0.ooo/2016/10/18/5805e60527874.png)   
example2 运行结果如图所示：   
![Rexample2.jpg](https://ooo.0o0.ooo/2016/10/18/5805e904cd670.jpg)   
2. 修改example1后的example1.dot截图如下：   
![example1.png](https://ooo.0o0.ooo/2016/10/18/5805e737bfa48.png)   
由图可知运行后的.dot和之前的.dot没有差别，但是运行结果发生了变化，变为了三次方,结果图如下：    
![Rexample1.png](https://ooo.0o0.ooo/2016/10/18/5805e7bb6aa24.png)   
## 二.具体如何修改的解释   
1. 修改example2，让3个square模块变成2个, tips:修改example2.xml的iterator,把value由3变为2，如图：    
![result2.jpg](https://ooo.0o0.ooo/2016/10/18/5805ea02ca80c.jpg)   
2. 修改example1，使其输出3次方数，tips:修改square.c,把i的平方变为i的立方，如下图：    
![result1.jpg](https://ooo.0o0.ooo/2016/10/18/5805eb0697fb5.jpg)   
### 三.实验感想
1. 这次实验挺简单的因为师兄已经把要修改的内容告诉了我们，很直接也很方便很不错!主要还是理解.c和.h文件以及.xml文件代码的含义，理解generator.c和consumer.c以及square.c的之间的联系。说实话没看太懂，只是理解个大概。

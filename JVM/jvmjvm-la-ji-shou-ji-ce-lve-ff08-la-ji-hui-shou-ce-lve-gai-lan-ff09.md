## 垃圾回收策略概览

6种组合策略：

![](/assets/3331517072385_.pic_hd.jpg)

年轻代的GC策略:

1. 


![](/assets/3341517072613_.pic_hd.jpg)


2. 


![](/assets/3351517072760_.pic_hd.jpg)

在年轻代使用并行GC处理的时候会产生一个STW的暂停，在进行对象扫描回收的时候，其他的线程将被暂时性挂起。

3.


![](/assets/3371517106157_.pic_hd.jpg)


老年代的GC策略:


1.


![](/assets/3381517106284_.pic_hd.jpg)


2.


![](/assets/3391517106559_.pic_hd.jpg)


3.


![](/assets/3411517107576_.pic_hd.jpg)


![](/assets/3421517107673_.pic_hd.jpg)


![](/assets/3431517107723_.pic_hd.jpg)

> 2020/3/13 第三天 坚持就是胜利

## 1. C/C++ 基础知识
(1) 多态能否用C语言实现？
>在C++程序设计中，多态指的是：具有不同功能的函数可以用同一个函数名，这样可以用一个函数名调用不同内容的函数。C语言可以通过宏实现编译时多态  
[参考链接](https://blog.csdn.net/dumpling5232/article/details/52632060)  

(2) 区别指针函数和函数指针？ 
>指针函数本质是一个函数，其返回值为指针。  
函数指针本质是一个指针，其指向一个函数。  
[参考链接](https://blog.csdn.net/luoyayun361/article/details/80428882) 

## 2. 操作系统
(1) 什么是死锁？死锁产生的条件？
>**死锁**是指两个或两个以上的进程在执行过程中，由于竞争资源或者由于彼此通信而造成的一种阻塞的现象，若无外力作用，它们都将无法推进下去。此时称系统处于死锁状态或系统产生了死锁，这些永远在互相等待的进程称为死锁进程。  
互斥条件  
请求与保持条件  
不可剥夺条件  
循环等待条件  
[参考链接](https://www.cnblogs.com/Kevin-ZhangCG/p/9038223.html)

(2) 进程有哪几种状态？
>就绪状态  
执行状态  
阻塞状态  
[参考链接](https://blog.csdn.net/qq_33774935/article/details/52724884)

## 3. 计算机网络
(1) GET 和 POST 的区别？
>本质是一样的，并无区别  
[参考链接](https://blog.csdn.net/qq_38182125/article/details/89071899)

(2) 为什么要三次握手、四次挥手？  
>[参考链接](https://mp.weixin.qq.com/s/8t_KFtrrBkFyZKPJg_y6pw) 


## 4. 数据库
(1) 什么是脏读？什么是幻读？
>[参考链接](https://blog.csdn.net/Watkins_OS/article/details/100511348)

(2) 第一范式、第二范式、第三范式分别是什么？
>1.第一范式：数据库表中的所有字段都是单一属性，不可再分的。这个单一属性是由基本数据类型所构成的。即第一范式要求数据库的表都是二维表。  
2.第二范式：数据库的表中不存在非关键字段对任意候选关键字段的部分函数依赖。部分函数依赖是指存在着组合关键字中的某一关键字决定非关键字的情况。即所有但关键字段的表都符合第二范式。  
3.第三范式：二范式在三范式之上，如果数据表中不存在非关键字段对任意候选关键字段的传递函数依赖规则则符合第三范式。  
BC范式：如果复合关键字，则复合关键字之间也不能存在传递函数依赖关系。（即把第三范式中的非关键字段升级为关键字及其分关键字段）

## 5. 算法
(1) 反转一个单链表

示例:

> 输入: 1->2->3->4->5->NULL  
> 输出: 5->4->3->2->1->NULL


(2) 一个数组中，找出除最大值之外的最大的k个数。 
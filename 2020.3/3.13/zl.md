> 2020/3/13 第三天 坚持就是胜利

## 1. C/C++ 基础知识
(1) 多态能否用C语言实现？

能，大多数C++编译器就是用C语言写的，理解了C++虚函数实现机制（vptr、vtbl）就可以用C语言来模拟这种机制。
(2) 区别指针函数和函数指针？ 

指针函数：返回指针的函数。
函数指针：指针，存储函数的地址。

## 2. 操作系统
(1) 什么是死锁？死锁产生的条件？

死锁：在多道程序环境中，多个进程可以竞争有限数量的资源。当一个进程申请资源时，如果这时没有可用资源，那么这个进程进入等待状态。有时，如果所申请的资源被其他等待进程占有，那么该等待进程有可能再也无法改变状态。这种情况称为死锁。

产生死锁必须满足以下四个条件，缺一不可：

1. 互斥条件：一个资源只能被一个进程所占用，此时若其它进程请求该资源，则请求进程必须等待
2. 不剥得条件：进程使用的资源在未完成使用之前，不能被其它进程强行得走。
3. 请求和保持条件：一个进程因为请求资源而阻塞时，对已获资源保持不放
4. 循环等待条件：若干进程形成了一种头尾相接环状等待资源的关系

(2) 进程有哪几种状态？

## 3. 计算机网络
(1) GET 和 POST 的区别？

GET 和 POST 是两种HTTP请求方法。

下面的表格比较了 GET 和 POST ：
||GET|POST|
|-|-|-|
|后退按钮/刷新|无害|数据会被重新提交（浏览器应该告知用户数据会被重新提交）。|
|书签|可收藏为书签|不可收藏为书签|
|缓存|能被缓存|不能缓存|
|编码类型|application/x-www-form-urlencoded|application/x-www-form-urlencoded或multipart/form-data。为二进制数据使用多重编码。|
|历史|参数保留在浏览器历史中|参数不会保存在浏览器历史中|
|对数据长度的限制|是的。当发送数据时，GET方法向URL添加数据；URL的长度是受限制的（URL的最大长度是2048个字符）|无限制|
|对数据类型的限制|只允许ASCII字符。|没有限制，也允许二进制数据|
|安全性|与POST相比，GET的安全性较差，因为所发送的数据是URL的一部分。|POST比GET更安全，因为参数不会被保存在浏览器历史或web服务器日志中。|
|可见性|数据在URL中对所有人都是可见的。|数据不会显示在URL中。|

(2) 为什么要三次握手、四次挥手？  

1. 为什么要三次握手？



## 4. 数据库
(1) 什么是脏读？什么是幻读？

(2) 第一范式、第二范式、第三范式分别是什么？

## 5. 算法
(1) 反转一个单链表

示例:

> 输入: 1->2->3->4->5->NULL  
> 输出: 5->4->3->2->1->NULL


(2) 一个数组中，找出除最大值之外的最大的k个数。 
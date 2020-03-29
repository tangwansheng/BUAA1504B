## 1. C/C++ 基础知识
(1) 下列程序编译时，（1）（2）（3）（4）（5）中有语法错误的语句是

```cpp
#include<iostream>
#include<string>
using namespace std; 
class Pet
{
     string name;
public:
     Pet(string p=" "){name=p;}
      string getName()const {return name;}
     virtual void call()const=0;
}; 
class Dog: public Pet{
public:
Dog(string n):Pet(n){}
void call()const{cout<<"##"<<" ";}
};
class Cat:public Pet{
public:
Cat(string n):Pet(n){}
void call()const{cout<<"**";}
};
void f(Pet *p)
{p->call();}
int main()
{ 
Pet pet0("#");           	//(1)
Dog pet1("*");           	//(2)
Cat pet2("$");           	//(3)
f(&pet1);					//(4)
f(&pet2);					//(5)
return 0;
}
```

(1) Pet类具有纯虚函数，为抽象类。抽象类不能实例化。

(2) 请说一下C/C++ 中指针和引用的区别？

1. 引用是另一个变量的别名，不额外开辟空间而指针本身是一个对象，保存的是内存地址。
2. 引用声明的时候必须初始化，并且之后不能更改其引用对象；指针声明的时候可不必初始化，在运行过程中可以改变指针所指地址。

## 2. 操作系统
(1) 操作系统中的缺页中断

在执行一条指令时，如果发现他要访问的页没有在内存中，那么停止该指令的执行，并产生一个页不存在的异常，对应的故障处理程序可通过从外存加载该页的方法来排除故障，之后，原先引起的异常的指令就可以继续执行，而不再产生异常。

(2) 操作系统中的结构体对齐，字节对齐

## 3. 计算机网络
(1) 搜索baidu，会用到计算机网络中的什么层？每层是干什么的

1、物理层：负责光电信号传递方式。集线器工作在物理层。以太网协议。
2、数据链路层：负责设备之间的数据帧的传输和识别。交换机工作在数据链路层。例如网卡设备的驱动，帧同步，冲突检测，数据差错校验等工作。
3、网络层：负责地址管理和路由选择。路由器工作在网络层。
4、传输层：负责两台主机之间的数据传输。
5、应用层：负责应用程序之间的沟通。网络编程主要针对的就是应用层。


(2) 数字证书是什么，里面都包含那些内容

数字证书在一个身份和该身份的持有者所拥有的公/私钥对之间建立了一种联系，由认证中心（CA）或者认证中心的下级认证中心颁发的。根证书是认证中心与用户建立信任关系的基础。在用户使用数字证书之前必须首先下载和安装。

数字证书的格式普遍采用的是X.509V3国际标准，一个标准的X.509数字证书包含以下一些内容：

1、证书的版本信息；

2、证书的序列号，每个证书都有一个唯一的证书序列号；

3、证书所使用的签名算法；

4、证书的发行机构名称，命名规则一般采用X.500格式；

5、证书的有效期，通用的证书一般采用UTC时间格式；

6、证书所有人的名称，命名规则一般采用X.500格式；

7、证书所有人的公开密钥；

8、证书发行者对证书的签名。

## 4. 数据库
(1) 索引是什么，多加索引一定会好吗

数据库索引是为了增加查询速度而对表字段附加的一种标识，是对数据库表中一列或多列的值进行排序的一种结构。

不一定好。创建索引和维护索引要耗费时间，这种时间随着数据量的增加而增加。索引需要占物理空间，除了数据表占数据空间之外，每一个索引还要占一定的物理空间，如果要建立聚簇索引，那么需要的空间就会更大。当对表中的数据进行增加、删除和修改的时候，索引也要动态的维护，这样就降低了数据的维护速度。

(2) 请你说一说inner join和left join

1. left join(左联接) 返回包括左表中的所有记录和右表中联结字段相等的记录。 
2. right join(右联接) 返回包括右表中的所有记录和左表中联结字段相等的记录。
3. inner join(等值连接) 只返回两个表中联结字段相等的行。

## 5. 算法
(1) 求1+2+…+n [Leetcode链接](https://leetcode-cn.com/problems/qiu-12n-lcof/)  
> 求 1+2+...+n ，要求不能使用乘除法、for、while、if、else、switch、case等关键字及条件判断语句（A?B:C）。  限制：1 <= n <= 10000  
> 示例:
```c
输入: n = 3
输出: 6
输入: n = 9
输出: 45
```

可以利用构造函数求解：
```c
#include <iostream>

using namespace std;

class Sum{
public:
    Sum(){ sum = sum + (++cnt); }
    static int getSum(){
        int temp = sum;
        cnt = sum = 0;
        return temp;
    }
private:
    static int cnt;
    static int sum;
};
int Sum::sum = 0;
int Sum::cnt = 0;
int calc_sum(int n){
    Sum* sum = new Sum[n];
    int res = Sum::getSum();
    delete[] sum;
    return res;
}
int main(int argc, char* argv[]){
    int res1 = calc_sum(10);
    int res2 = calc_sum(12);
    cout << res1 << " " << res2 <<  endl;
    return 0;
}
```



(2) 两数相加 [Leetcode链接](https://leetcode-cn.com/problems/add-two-numbers)
> 给出两个 非空 的链表用来表示两个非负的整数。其中，它们各自的位数是按照 逆序 的方式存储的，并且它们的每个节点只能存储 一位 数字。   
>
> 如果，我们将这两个数相加起来，则会返回一个新的链表来表示它们的和。
>
> 您可以假设除了数字 0 之外，这两个数都不会以 0 开头。  
> 示例:
```c
输入：(2 -> 4 -> 3) + (5 -> 6 -> 4)
输出：7 -> 0 -> 8
原因：342 + 465 = 807
```
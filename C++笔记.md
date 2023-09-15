# C++笔记

## 第一章 绪论

### 计算机系统

硬件：输入输出设备、存储设备、运算设备

计算机指令系统：硬件能识别的机器语言的集合

软件：应用软件、操作系统、中间件

### 计算机语言和程序设计方法发展

机器语言-汇编语言-高级语言（抽象层次逐渐提高，屏蔽底层细节,接近人类思维方式)

面向过程程序设计、面向对象程序设计、泛型程序设计

---

高级语言：

+ C++语言：将客观事物看作对象，通过消息传送进行沟通，支持分类和抽象

---

面向过程程序设计：按既定的求解问题的过程进行计算

面向对象程序设计：系统由对象组成，对象与对象之间通过消息进行通信

---

面向对象的基本概念：

+ 类与对象：就是类型与实例的关系
+ 封装： 隐蔽对象内部细节，保留有限对外接口，安全性好
+ 继承：在已有类的基础上改造、扩展形成新的类，用于软件复用
+ 多态：同样的消息作用在不同对象上引起不同的行为

---

### 程序的开发过程

机器语言程序-汇编语言程序-高级语言程序

源程序-（编译为二进制代码）-目标程序-（加上需要调用的已编译好的程序）-可执行程序

---

三种翻译程序：

+ 汇编程序：将汇编语言源程序翻译为目标程序

+ 编译程序：将高级语言程序源程序翻译为目标程序

+ 解释程序：将高级语言源程序翻译为机器指令，边翻译边执行

  JAVA程序是半编译半解释，目的是为了跨平台；JAVA程序-字节码-JAVA虚拟机-可执行程序

  C++程序是直接编译为本地机器语言代码

---

C++程序开发过程：

+ 算法与数据结构设计
+ 编辑源程序
+ 编译
+ 连接
+ 测试

### 计算机中的信息与存储单位

计算机的基本功能：算术运算、逻辑运算

计算机中的信息：控制信息、数据信息（数值信息，非数值信息）

信息的存储单位：位、字节（8位）

### 计算机的数字系统

二进制系统

八进制系统

十六进制系统

---

进制转换：

+ R进制转十进制：各位数字与权相乘再相加

+ 十进制转R进制：除以R取余

+ 十进制小数转二进制小数：乘以二取整

---

二进制的编码表示：

+ 原码的缺点：
  + 零表示不唯一
  + 四则运算时，符号位需单独处理
  + 运算规则复杂

+ 补码：
  + 零表示唯一
  + 符号位可作为数值参加运算

+ 模数和补数：
  + 时钟的模是12，2的补数是10
+ 反码计算规则：
  + 负整数：符号位不变，其余各位取反
  + 正整数：原码就是补码

+ 补码计算规则：
  + 反码作为中间码
  + 负数补码=反码+1
  + 正数补码=原码

+ 补码的优点：
  + 零表示唯一
  + 符号位可作为数值参加运算
  + 补码运算结果仍为补码
  + 补码再求补码即为原码
  + 运算结果溢出：负数之和为正数、正数之和为负数

---

+ 实数的浮点表示：
  + 计算机中用浮点方式表示小数
  + 包括阶码和尾数两个部分

+ 字符在计算机中的表示：
  + 字符通过编码表示
  + ASCII码：7位二进制数表示一个字符
  + 汉字编码：中国国家标准

## 第二章 C++简单程序设计

C++能处理的基本数据类型：

+ 整数类型
+ 实数类型
+ 字符类型
+ 布尔类型

C++支持的基本运算：

+ 算术运算
+ 逻辑运算

数据的输入与输出

流程控制

自定义数据类型（枚举类型）

---

### 字符集与词法记号

C++基本字符集包括：

+ 大小写英文字母
+ 数字字符
+ 特殊字符

C++词法记号：

+ 关键字
+ 标识符
+ 文字
+ 分隔符
+ 运算符
+ 空白符

标识符：

+ 以英文字母或下划线开头
+ 由英文字母、下划线或数字组成
+ 区分大小写
+ 不能是关键字或操作符

---

### 基本数据类型

C++能处理的基本数据类型：

+ 整数类型
+ 实数类型
+ 字符类型
+ 布尔类型

程序中的数据：

+ 常量：在程序运行过程中不可改变
+ 变量：在程序运行过程中允许改变

---

整数类型：

+ 基本整数类型 int
+ 按符号分为有符号、无符号
+ 按范围分为：短整（short)、长整、长长整

浮点类型：

+ 单精度
+ 双精度
+ 扩展精度
+ 浮点数在计算机中都是近似存储的
+ 不能直接比较两个浮点数是否相等，应该看两者的差是否足够小

字符串类型：

+ 字符串常量
+ 采用字符数组存储的字符串
+ String类的对象存放字符串

布尔类型：只有两个值true和false

---

常量：

+ 程序运行过程中值不可改变的量
+ 直接使用文字表示的值，如数字、单引号字符

整数常量：

+ 以文字形式出现的整数
+ 分为十进制、八进制、十六进制
+ 后缀U表示无符号，L表示long

浮点数常量：

+ 以文字形式出现的实数
+ 分为一般形式和指数形式
+ 默认为double型
+ 后缀F表示float型

字符常量：

+ 单引号括起来的字符
+ 在计算机中以ASCLL码存储

C风格字符串常量

+ 一对双引号括起来的字符序列
+ 在内存中按字符顺序存放，末尾添加'\0'作为标记
+ 通过加前缀可改变字符串常量的类型

---

变量：

+ 在程序运行过程中可以改变的量
+ 就是将名字结合到内存单元（通过定义变量的方式来使用内存空间）
+ 定义变量时应对其进行初始化
  + 全局变量会自动初始化
  + 局部变量不初始化就是垃圾数据

初始化方式：

+ int a =0
+ int a(0)
+ 列表初始化
  + int a = {0}
  + int a{0}
  + 不允许信息丢失，如用double初始化int

符号常量：

+ 使用const修饰
+ 也是将名字结合到内存单元，但是不允许修改
+ 定义时一定要初始化，程序运行过程中不允许修改

### 算术运算符与算术表达式

基本算术运算符：

+ 加减乘除：整数相除只取整

+ 取余
+ 自增自减
+ 赋值运算符
+ 复合赋值运算符

+ 逗号运算符
+ 关系运算符
+ 逻辑运算符
+ 条件运算符
+ sizeof运算符：得到变量对应的位数
+ 位运算符
  + 按位与：可将某位置零、取出指定位
  + 按位或：可讲某位置一
  + 按位异或：与0异或不变，与1异或取反
  + 移位：左移低位补零（乘二），右移高位补符号位（除二）

---

运算优先级

类型转换：

+ 隐含转换：
  + 低类型转换为高类型
  + 布尔类型与算数值转换
  + 浮点数与整数转换

+ 显示转换：
  + 类型说明符（表达式）
  + （类型说明符）表达式
  + 类型转换说明符<类型说明符>（表达式）
  + int(z); (int)z; static_cast<int>(z)三者等价

### 数据输入与输出

I/O流：

+ 流：数据从一个对象到另一个对象的流动
+ 流在使用前要被建立，使用后要被删除
+ 数据的输入与输出是通过I/O流实现的
+ cin和cout是预定义的流类对象，用来处理标准输入与输出
+ 从流中获取数据称为提取操作，向流中添加数据的操作称为插入

+ 通过插入和提取运算符作用在流类对象上实现向标准设备输入与输出

I/O流类库操纵符：

+ 用于插入或提取过程中控制格式
+ 主要在输出时进行格式控制

### 流程控制

条件语句：

+ If语句：
  + 分为单分支、双分支、多分支
  + 每个else始终去找最近的if去匹配
  + 嵌套时，如果内部为单分支，需要用大括号括起来作为复合语句

~~~c++
/*比较两个数的大小*/
#include <iostream>
using namespace std;
int main(){
int x,y;
cout>>"Please input x and y:"z<<endl;
cin>>x>>y;
if(x!=y)
  if(x>y)
    cout<<"x>y"<<endl;
  else
    cout<<"x<y"<<endl;
else
  cout<<"x=y"<<endl;
return 0;
}
~~~



+ switch语句：
  + 每个分支都要有break
  + 若进入的分支没有break，则会执行后面的所有语句，包括default，直到遇到break或运行结束

~~~c++
#include <iostream>
using namespace std;
int main(){
    int x;
    cout<<"Please input a number:"<<endl;
    cin>>x;
    switch(x){
        case 1:cout<<"monday"<<endl;break;
        case 2:cout<<"tuesday"<<endl;break;
        case 3:cout<<"wednesday"<<endl;break;
        case 4:cout<<"thursday"<<endl;break;
        case 5:cout<<"friday"<<endl;break;
        case 6:cout<<"saturday"<<endl;break;
        case 7:cout<<"sunday"<<endl;break;
        default:
            cout<<"This is just a number"<<endl;break;
    }
    return 0;
}
~~~

循环语句：

+ 用同样的方法去处理不同的数据时使用
+ 循环体中必须有能改变条件表达式的语句，否则就是死循环

+ while语句：
  + 先判断表达式，若为true则执行语句

~~~c++
#include <iostream>
using namespace std;
int main(){
    int x=1;
    int sum=0;
    while(x<=10){
        sum +=x;
        x++;
    }
    cout<<"sum="<<sum<<endl;
    return 0;
}
~~~

+ do while语句：
  + 先执行语句，在判断条件

~~~c++
/*将输入的数字各位翻转后输出*/
#include <iostream>
using namespace std;
int main(){
    int numinput,numoutput;
    cout<<"Please enter the number:"<<endl;
    cin>>numinput>>endl;
    cout<<"The number in reverse order is:"<<endl;
    do{
        numoutput=numinput%10;
        cout<<numoutput;
        numinput/=10;
    }while(numinput！=0)；//采用do while输入为零时也有输出，采用while需单独考虑输入为零的情况
    cin>>endl;
    return 0;
}
~~~

+ for语句：
  + 用来处理循环次数已知的循环
  + 最强大的循环语句

~~~c++
/*找出一个数的所有因子*/
#include <iostream>
using namespace std;
int main(){
    int numinput;
    cout<<"Please enter the number:"<<endl;
    cin>>numinput;
    cout<<"Number"<<numinput<<"Factor:";
    for(int i=1;i<=numinput;i++)
       if(numinput%i==0)
           cout<<i<<" ";
    cout<<endl; 
    return 0;
}
~~~

+ 循环嵌套：

  ~~~c++
  /*循环和选择嵌套*/
  /*统计正负数的个数，读入零则停止*/
  #include <iostream>
  using namespace std;
  int main(){
      int numinput,i=0,j=0;
      cout<<"Please enter the number:"<<endl;
      cin>>numinput;
      while(numinput!=0){
          if(numinput>0)
              i++;
          if(numinput<0)
              j++;
          cin>>numinput;
      }
      cout<<"The number of positive integers is:"<<i<<endl;
      cout<<"The number of negative integers is:"<<j<<endl;
      return 0;
  }
  ~~~

其他控制语句：

+ break语句：
  + 使程序从循环体和switch语句中跳出之后执行逻辑上的下一条指令
+ continue语句：
  + 结束本次循环，判断是否执行下一次循环

### 自定义类型

已定义好的数据类型不足以表示现实世界，故需要自定义类型

类型别名：

+ 为已有类型另外名
+ 两种语法方式
  + typedef 已有类型名 新类型名表
  + using 新类型名 =已有类型名

枚举类型：

+ 将全部可取值都列举出来
+ 分为限定作用域枚举类型、不限定作用域枚举类型
+ 不限定作用域枚举类型
  + 语法形式：enum 枚举类型名 {变量值列表}
  + 枚举元素是常量，不能赋值
  + 枚举元素具有默认值，依次从零递增
  + 可以在声明时指定枚举元素的值
  + 枚举值可以进行关系运算，也就是可比较大小
  + 整数赋值给枚举变量需进行强制类型转换，并且需要该整数在枚举元素的范围内，才能转换成功
    + 枚举变量的声明形式：enum 枚举类型名 枚举变量名
  + 枚举值可以给整型变量赋值

~~~ c++
#include <iostream>
using namespace std;
enum GameResult {WIN,LOSE,TIE,CANCEL};
int main(){
    enum GameResult result;
    GameResult x;
    for(int i=WIN;i<=CANCEL;i++){
        result=GameResult(i);
        if(result==WIN)
            cout<<"The result of game is win"<<endl;
        if(result==LOSE)
            cout<<"The result of game is lose"<<endl;
        if(result==TIE)
            cout<<"The result of game is tie"<<endl;
        if(result==CANCEL)
            cout<<"The result of game is cancel"<<endl;
    }
    return 0;
}
~~~

## 第三章 函数

函数的定义和调用：将函数所描述的方法写出来并使用

内联函数：对于简单的函数，函数调用所产生的开销大于直接执行操作所产生的开销，使用内联函数

constexpr函数：常量表达式函数，参数值为常数时返回值为常数，可用来初始化符号常量

带默认参数值的函数：定义函数时给函数的参数定一个默认值，可以给出全部参数、部分参数、不给参数

函数重载：一个函数名对应多种不同的算法，通过函数参数列表来区分不同的函数体

---

### 函数定义

定义函数：将算法用编程语言描述出来

函数名：功能模块的名字

函数参数：计算所需要的数据和条件

函数的返回值：需要返回的计算结果，并不是所有函数都有返回值，无返回值类型不用写return语句

语法形式：类型标识符 函数名（形式参数表）{语句系列}

----

### 函数调用

函数调用时会用实参去初始化形参，这时才为形参分配内存空间

原型声明：

+ 函数调用前需要声明原型，就是告诉编译器要调用什么格式的函数
+ 语法形式：类型标识符 被调用函数名（带有类型说明的形参表）

调用形式：函数名（实参列表）

嵌套调用：在一个函数体中去调用另一个函数

递归调用：函数直接或间接调用自身

~~~c++
//编写求n次方的函数
#include <iostream>
#include <stdlib.h>
using namespace std;
void exit (int value);
double GetPower(double x, int n){
double result;
if(x==0&&n!=0)
   result=0;
if(x!=0&&n==0)
   result=1;
if(x==0&&n==0)
   cout<<"Error:base number and exponent are both zero!";
   quit(1);
if(x!=0&&n!=0){
   result=1;
   for(int i=1;i<=n;i++)
      result*=x;
}
return result;
}
int main(){
double resu;
double basenum;
int exp;
cout<<"Please enter base number and exponent:";
cin>>basenum>>exp;
resu=GetPower(basenum,exp);
cout<<"The result is:"<<resu<<endl;
return 0;
}
~~~

~~~c++
//将八位二进制数转化为十进制数输出
include <iostream>
using namespace std;
double GetPower (double x,int n);//声明函数原型
int main(){
    int result=0;
    char inputchar;
    cout<<"Please enter binary number:"<<endl;
    for(int i=0;i<=7;i++){
        cin>>inputchar;
        if(inputchar=='1')
        result+=static_cast<int>(GetPower(2,i));
    }
    cout<<"The decimal number is:"<<result<<endl;
    return 0;
}
double GetPower (double x, int n){
    double resu=1.0;
    while(n--)
        resu*=x;
    return resu;
}
~~~

~~~c++
//用公式求圆周率,不能整数除整数！！！
#include <iostream>
using namespace std;
int main(){
    double x=1/5.0,y=1/239.0,result;
    result=16*Arctan(x)-4Arctan(y);
    cout<<Pi equals<<" "<<result<<endl;
    return 0;
}
double Arctan (double a){
    double arctanres;
    arctanres=a-1/3.0*GetPower(a,3)+1/5.0*GetPower(a,5)-1/7.0*GetPower(a,7);
    return arctanres;
}
double GetPower (double m,int n){
    double powerres=1.0;
    while(n--)
        powerres*=m;
    return powerres;
}
~~~

---

嵌套调用：

~~~c++
//输入两个整数求平方和
#include <iostream>
using namespace std;
unsigned func1(int m){
    unsigned resu1;
    resu1=m*m;
    return resu1;
}
int func2(int a,int b){
    int resu2;
    resu2=func1(a)+func1(b);
    return resu2;
}
int main(){
    int x,y,result;
    cout<<"Please enter two number:"<<endl;
    cin>>x>>y;
    result=func2(x,y);
    cout<<"The quadratic sum is:"<<result<<endl;
    return 0;
}
~~~

递归调用：

~~~c++
//求阶乘
#include <iostream>
using namespace std;
int func(int n){
    int resu;
    if(n!=0)
        resu=n*func(n-1);
    else
        resu=1;
    return resu;
}
int main(){
    int x,result;
    cout<<"Please enter a number:"<<endl;
    cin>>x;
    result=func(x);
    cout<<"The factorial is:"<<" "<<result<<endl;
    return 0;
}
~~~

~~~c++
//用递归法计算从n个人中选k个人的组合数
include <iostream>
include <stdlib.h>
using namespace std;
void exit (int value);
int func(int n,int k){
    int resu;
    if(n<k){
        cout<<"Error:n should be larger than k!"<<endl;
        exit(1);
    }
    if(n==k){
        if(n==0){
            cout<<"The number should not be less than 1!"<<endl;
            exit(1);
        }
        else
            resu=1;
    }
    if(n>k){
        if(k==0)
            resu=1;
        else
            resu=func(n-1,k)+func(n-1,k-1);
    }
    return resu;
}
int main(){
    int x,y,result;
    cout<<"Please enter k and n:"<<endl;
    cin>>k>>n;
    result=func(x,y);
    cout<<"The number of combination is:"<<result<<endl;
    return 0;
}
~~~

---

### 函数参数传递

实参与形参：

+ 形参在函数被调用时才分配内存空间
+ 实参可以是常量、变量或表达式
+ 实参类型必须与形参相符，如不符则编译器隐含转换或报错

---

函数参数传递方式：

+ 值传递只是单向传递参数值

+ 引用传递是双向传递

+ 常引用做参数可保证实参数据安全（因为传引用的开销比较传值小，且不希望双向传递）

---

引用类型：

+ 引用相当于是变量的别名
+ 定义一个引用时，必须进行初始化，使其指向一个已存在的对象
+ 引用初始化之后就不能更改为指向其他对象
+ 引用往往作为形参，实现参数双向传递

~~~c++
 //引用类型
#include <iostream>
using namespace std;
void func(int &a,int &b){
    int c;
    c=a;
    a=b;
    b=c;
}
int main(){
    int x,y;
    cout<<"Please enter two numbers:"<<endl;
    cin>>x>>y;
    func(x,y);
    cout<<"x="<<x<<"y="<<y<<endl;
    return 0;
}
~~~



### 含有可变参数的函数

用于编写参数个数和长度都不确定的形参表，从而得到含有可变参数的函数

两种方法可得到含有可变参数的函数：

+ 若所有实参类型相同，可以传递名为initiallizer_list的标准库类型
+ 若实参类型不同，可以编写可变参数的模板

initializer_list:

+ 是一种是标准库类型
+ 用来表示某种特定类型值的数组
+ 该类型定义在同名的头文件中
+ 语法形式：initializer_list <类型标识符> 对象名；
+ 其对象中的元素是常量，无法改变
+ 含有initializer_list形参的函数可拥同时有其他形参

### 内联函数

+ 内联函数声明时使用inline关键字，意思就是建议编译器用函数体中的语句去替换函数调用表达式
+ 由编译器决定函数是否当内联函数处理

+ 内联函数体内不能有循环语句和switch语句
+ 只能先定义再调用，不能像普通函数先声明再调用再定义
+ *对内联函数不能进行异常接口声明*

~~~c++
//内联函数
#include <iostream>
using namespace std;
const double PI=3.14159;
inline double func(double r){
    return PI*r*r;
}
int main(){
    double x=2.0;
    double area=func(x);
    cout<<area;
}
~~~

 ### constexpr函数

+ 函数声明时使用constexpr关键字修饰
+ 所有参数为constexpr时，返回值一定是constexpr，且函数体中只能有一条return语句
+ 是编译期间可计算的函数
+ 可用来初始化常量表达式，语法形式：constexpr 类型标识符 常量表达式=常量表达式函数

### 带默认参数值的函数

+ 在函数定义或声明时，给形参确定默认值
+ 不能同时在定义和声明中给出默认值，哪个在前就在哪个给出默认值
+ 调用时有实参就用实参，没有实参就用默认形参值
+ 书写形式：有默认参数值的形参放在函数参数列表的右半边
+ 实参与形参按从左至右的次序依次结合

~~~c++
//求长方体体积
#include <iostream>
using namespace std;
double GetVolume(double length,double width=2.0,double height=3.0){
    return length*width*height;
}
int mian(){
    double resu1,resu2,resu3;
    resu1=GetVolume(2);
    resu2=GetVolume(2,3);
    resu3=GetVolume(2,3,4);
    cout<<resu1<<" "<<resu2<<" "<<resu3<<endl;
    return 0;
}
~~~

### 函数重载

+ 定义：功能相近的函数，在相同作用域内用同样的函数名声明
+ C++多态性的重要机制，通过静态多态性机制来实现（编译阶段多态性）
+ 区分重载函数的两个标准：形参类型和个数
+ 编译器根据实参与形参的匹配程度来确定调用哪个函数
+ 不要将不同功能的函数声明为重载函数

### C++的系统函数

在系统库中已经定义好的函数，包含相应的头文件即可调用

## 第四章 类和对象

对象：用来描述现实中对象，具有属性和行为

类：同一类对象的共同属性和行为，将数据和函数封装起来，提供对外接口

构造函数：定义对象时，初始化对象

析构函数：删除对象时，释放资源

类的组合：把已有类的对象作为新类的成员

结构体

联合体

枚举类

---

### 面向对象程序设计基本特点

抽象：

+ 对同一类对象的共同属性和行为进行概括
+ 包括两个方面：数据描述、实现过程
+ 数据抽象：描述某类对象的属性
+ 代码抽象：描述某类对象的行为
+ 通过类来实现抽象

封装：

+ 将抽象出来的数据和代码封装在一起，视为一个整体
+ 目的：增加安全性和简化编程，只需要通过外部接口以特定访问权限使用类的成员
+ 通过类声明中的{}实现封装

继承：在已有类的基础上，扩展形成新的类

多态：

+ 同一函数名可以实现不同的功能
+ 目的：减少标识符个数，达到行为和标识统一

---

### 类和对象的定义

 类是同一类对象的抽象，对象是类的实例

通过定义类的对象，才能通过对象去使用类中定义的功能

类的定义：

+ 可以为数据成员设置类内初始值来初始化数据成员
+ 如果构造函数未对数据成员初始化，构造对象时可用类内初始值来初始化对象

+ 类的访问方式：
  + 公有类型成员：
    + 用public关键字声明
    + 是类与外部的接口
    + 任何外部函数都可以访问公有类型函数和成员
  + 私有类型成员
    + 用private关键字声明
    + 只允许本类中的函数访问
    + 类的访问方式默认为私有类型
  + 保护类型成员
    + 用protected关键字声明
    + 与私有类型成员类似，区别在于继承和派生时对派生类影响不同

+ 类的成员函数：
  + 可以在类中声明函数原型，在类外给出函数体实现，但是类外函数体的函数名前要加类名来限定
  + 可以在类中声明函数原型，在类中给出函数体实现，形成内联成员函数
  + 允许声明重载函数和带默认参数值的函数

+ 内联成员函数：
  + 简单函数可以声明为内联形式，以提高运行效率
  + 函数体中不能有循环语句和switch语句
  + 两种声明方式：
    + 将函数体放在类的声明中
    + 使用inline关键字声明，在类外给出函数体实现

对象的定义：

+ 语法形式：类名 对象名；
+ 类中成员之间直接使用成员名互相访问
+ 从类外访问类的共有类型成员需要通过类的对象来访问，语法形式：对象名.成员名
+ 通过对象只允许访问类的公有类型成员

~~~c++
//类与对象
#include <iostream>
using namespace std;
class Clock{
    public:
    void setTime(int x=0,int y=0,int z=0);
    void showTime();
    private:
    int hour;
    int minute;
    int second;
};
void Clock::setTime(int x,int y,int z){
    cout<<"Please enter hour,minute and second:"<<endl;
    cin>>x>>y>>z;
    hour=x;
    minute=y;
    second=z;
}
void Clock::showTime(){
    cout<<"Time is: "<<hour<<":"<<minute<<":"<<second<<endl;
}
int main(){
    Clock myClock;
    myClock.setTime(13,19,20);
    myClock.showTime();
    return 0;
}
~~~

### 构造函数

 构造函数是类中的特殊函数，用于描述初始化对象的算法

作用：在对象被创建时，用特定的值构造对象，将对象初始化为特定的状态

构造函数的形式：

+ 函数名与类名相同
+ 不能定义返回值类型，也不能有return语句
+ 可以有形参，也可以没有形参
+ 可以是内联函数、重载函数、带默认参数值的函数

构造函数的调用：在对象创建时自动调用

默认构造函数：

+ 调用时不需要实参的构造函数
  + 无形参的构造函数
  + 全部形参都有默认值的构造函数
+ 两种默认构造函数不能同时出现在类中

隐含生成的构造函数：

+ 程序中未定义构造函数时由编译器生成一个默认构造函数
+ 参数列表为空，不为数据成员设置初始值
+ 如果类的数据成员未设置类内初始值，则用默认方式初始化对象，但基本数据类型默认初始化的值是不确定的（就是不知道对象会初始化成什么样子）
+ 如果类的数据成员设置了类内初始值，则用类内初始值初始化对象
+ 如果程序中定义了构造函数，还想让编译器隐含生成构造函数，可使用"函数名（）=default"

 ~~~c++
 //构造函数、默认构造函数、构造函数重载
 #include <iostream>
 using namespace std;
 class Clock{
     public:
     Clock(int x,int y,int z);
     Clock();//自己写的默认构造函数
     void showTime();
     private:
     int hour,minute,second;
 };
 Clock::Clock(int x,int y,int z):hour(x),minute(y),second(z){
     
 }//通过初始化列表对类的数据成员进行初始化
 Clock::Clock():hour(0),minute(0),second(0){
     
 }//默认构造函数的实现
 void Clock::showTime(){
     cout<<"Time is: "<<hour<<":"<<minute<<":"<<second<<endl;
 }
 int main(){
     Clock myClock(12,12,12);
     Clock yourClock;
     myClock.showTime();
     yourClock.showTime();
     return 0;
 }
 ~~~

委托构造函数：

+ 一个构造函数委托另一个函数完成初始化功能
+ 对于形参和初始化列表不同的构造函数，减少函数体重复
+ 保持代码实现的一致性，若修改某个构造函数初始化算法，其他委托该构造函数来始化的其他构造函数的算法也会同步修改

复制构造函数：

+ 一种特殊的构造函数，要符合构造函数的要求
+ 作用：用已存在的对象去初始化同类型的新对象
+ 复制构造函数的形参为本类对象的引用
+ 对象作为形参一般使用常引用，用const修饰

+ 调用复制构造函数的三种情形：
  + 定义对象时，用已有对象初始化，发生复制构造
  + 函数的形参是类的对象，调用函数时实参对象初始化形参对象，发生复制构造
  + 函数返回值是类的对象，返回主调函数时会初始化一个临时无名的对象，发生复制构造

+ 隐含的复制构造函数：
  + 若程序中没有定义复制构造函数，编译器会自动产生一个默认复制构造函数
  + 作用：将两个对象数据成员一一对应复制

+ 可以用"类名（const 类名&对象名）=delete"来指示编译器不生成默认复制构造函数
+ 通过自己写复制构造函数，可以按自己的方法来发生复制构造

  ~~~c++
  //复制构造函数
  #include <iostream>
  using namespace std;
  class Clock{
      public:
      Clock(int x,int y,int z);
      Clock(const Clock &a);
      void showTime();
      void func1(const Clock &b);
      void func2();
      private:
      int hour,minute,second;
  };
  Clock::Clock(int x,int y,int z):hour(x),minute(y),second(z){
      
  }
  Clock::Clock(const Clock &a):hour(a.hour),minute(a.minute),second(a.second){
    cout<<"Calling the copy constructor"<<endl;  
  }
  void Clock::showTime(){
      cout<<"Time is: "<<hour<<":"<<minute<<":"<<second<<endl;
  }
  void Clock::func1(const Clock &b){
      b.showTime;
  }
  void Clock::func2(){
      Clock c;
      return c;
  }
  int main(){
      Clock myClock(12,00,00);
      Clock theirClock(13,00,00);
      Clock yourClock(myClock);
      myClock.showTime();
      myClock.func1(theirClock);
      yourClock.showTime();
      //youClock.func2();
      return 0;
  }
  ~~~

### 析构函数

对象消亡的时候，需要释放资源

作用：由析构函数完成对象被删除前的清理工作

调用：对象生存期结束时，会自动调用析构函数

隐含生成的析构函数：

+ 若程序中未声明析构函数，编译器自动产生一个默认的析构函数
+ 其函数体为空

析构函数：

+ 原型：~类名()；
+ 析构函数没有参数，没有返回类型

### 类的组合

组合的概念：

+ 已有类的对象作为新类的成员
+ 在已有抽象的基础上实现更复杂的抽象

 组合类构造函数需要将部件类对象初始化所需要的初始化参数传递给它

组合类的构造函数：

+ 既要初始化本类中的基本类型数据成员
+ 也要给对象成员传递初始化参数
+ 声明形式：类名::类名(对象成员所需形参，本类成员形参)：对象1(初始化参数)，对象2(初始化参数)，本类数据成员(初始化参数){函数体实现}；

 构造组合类对象时的初始化次序：

+ 首先对构造函数初始化列表中的成员按在组合类中定义次序进行初始化
+ 对于对象成员：
  + 由组合类构造函数传递初始值
  + 调用部件类构造函数完成初始化
  + 初始化顺序按对象成员定义次序，先声明先初始化
  + 若组合类构造函数没有给对象成员传递初始值，则调用部件类的默认构造函数进行初始化
  + 若组合类构造函数没有给对象成员传递初始值，而部件类没有默认构造函数，编译器则会报错，故创建类时最好写一个默认构造函数

+ 处理完初始化列表后，再执行组合类构造函数的函数体

~~~c++
//类的组合
#include <iostream>
using namespace std;
enum CPU_Rank { P1 = 1, P2, P3, P4, P5, P6, P7 };
class CPU {
public:
 CPU(CPU_Rank rank,int frequency, float voltage);
 CPU(const CPU& cpu);
 ~CPU();
 void run();
 void stop();
private:
 CPU_Rank rank;
 int frequency;
 float voltage;
};
CPU::CPU(CPU_Rank rank,int frequency, float voltage):rank(rank),frequency(frequency),voltage(voltage) {
 cout << "构造了一个CPU！" << endl;
}
CPU::CPU(const CPU& cpu):rank(cpu.rank),frequency(cpu.frequency),voltage(cpu.voltage) {
 cout << "复制构造一个CPU！" << endl;
}
CPU::~CPU() {
 cout << "析构了一个CPU！" << endl;
}
void CPU::run() {
 cout << "CPU开始运行！" << endl;
}
void CPU::stop() {
 cout << "CPU停止运行！" << endl;
}
//RAM类
enum RAM_Type{DDR4,DDR3,DDR2};
class RAM {
public:
 RAM(int capacity, RAM_Type type, int frequency);
 RAM(const RAM& ram);
 ~RAM();
 void run();
 void stop();
private:
 int capacity;
 RAM_Type type;
 int frequency;
};
RAM::RAM(int capacity, RAM_Type type, int frequency):capacity(capacity),type(type),frequency(frequency) {
 cout << "构造一个RAM！" << endl;
}
RAM::RAM(const RAM& ram):capacity(ram.capacity),type(ram.type),frequency(ram.frequency) {
 cout << "复制构造一个RAM！" << endl;
}
RAM::~RAM() {
 cout << "析构了一个RAM！" << endl;
}
void RAM::run() {
 cout << "RAM开始运行！" << endl;
}
void RAM::stop() {
 cout << "RAM停止运行！" << endl;
}
//CDROM类
enum CDROM_Interface{SATA,USB};
enum CDROM_Install_type{ external,build_in };
class CDROM {
public:
 CDROM(CDROM_Interface interface, CDROM_Install_type install_type, unsigned int cache_size);
 CDROM(const CDROM& cdrom);
 ~CDROM();
 void run();
 void stop();
private:
 CDROM_Interface interface;
 CDROM_Install_type install_type;
 unsigned int cache_size;
};
CDROM::CDROM(CDROM_Interface interface, CDROM_Install_type install_type, unsigned int cache_size):interface(interface),install_type(install_type),cache_size(cache_size) {
 cout << "构造一个CDROM！" << endl;
}
CDROM::CDROM(const CDROM& cdrom) :interface(cdrom.interface), install_type(cdrom.install_type), cache_size(cdrom.cache_size) {
 cout << "复制构造一个CDROM！" << endl;
}
CDROM::~CDROM() {
 cout << "析构了一个CDROM！" << endl;
}
void CDROM::run() {
 cout << "CDROM开始运行！" << endl;
}
void CDROM::stop() {
 cout << "CDROM停止运行！" << endl;
}
//COMPUTER类
class COMPUTER {
public:
 COMPUTER(CPU c, RAM r, CDROM cd, unsigned int s, unsigned int b);
 ~COMPUTER();
 void run();
 void stop();
private:
 CPU my_cpu;
 RAM my_ram;
 CDROM my_cdrom;
 unsigned int storage_size;
 unsigned int bandwidth;//带宽
};
COMPUTER::COMPUTER(CPU c, RAM r, CDROM cd, unsigned int s, unsigned int b):my_cpu(c),my_ram(r),my_cdrom(cd),storage_size(s),bandwidth(b) {
 cout << "构造了一个COMPUTER！" << endl;
}
COMPUTER::~COMPUTER() {
 cout << "析构了一个COMPUTER！" << endl;
}
void COMPUTER::run() {
 my_cpu.run();
 my_ram.run();
 my_cdrom.run();
 cout << "COMPUTER开始运行！" << endl;
}
void COMPUTER::stop() {
 my_cpu.stop();
 my_ram.stop();
 my_cdrom.stop();
 cout << "COMPUTER结束运行！" << endl;
}
int main() {
 CPU Gen1(P6,100,2.5);
 RAM myram(16, DDR4, 3200);
 CDROM mycdrom(SATA, build_in, 512);
 COMPUTER mycomputer(Gen1, myram, mycdrom, 512, 10);
 mycomputer.run();
 mycomputer.stop();
 return 0;
}
~~~

### 前向引用声明

+ 类应该先声明后使用
+ 若在类的声明之前要引用该类，需要进行前向引用声明
+ 前向引用声明只是为程序引入一个标识符，不涉及类的具体细节
+ 在提供完整的类声明之前，只能使用被声明的符号，不能声明和使用该类的对象，也不能涉及类的其他细节

### 结构体

+ 结构体是特殊的类，用struct关键字声明
+ 类的默认访问权限是private，结构体默认访问权限是public
+ 结构体使用情形：
  + 只有数据成员，没有什么函数成员
  + 数据成员全都是共有类型是成员

+ 结构体的定义：struct 结构体名称{数据成员}
+ 结构体的初始化：struct 结构体对象名{数据成员初始值}

### 联合体

+ 用union关键字声明
+ 所有成员共用同一组内存，任何两个成员不会同时有效
+ 联合体的定义：union 联合体对象名称{数据成员}
+ 无名联合体定义：union {数据成员}

~~~c++
//使用联合体保存成绩信息，并输出
#include <iostream>
using namespace std;
class Examinfor{
    public:
    Examinfor(string name,char grade);
    Examinfor(string name,bool pass);
    Examinfor(string name,int mark);
    void show();
    private:
    string name;
    enum {GRADE,PASS,MARK} mode;
    union {
        char grade;
        bool pass;
        int mark;
    };
};
Examinfor::Examinfor(string name,char grade):name(name),mode(GRADE),grade(grade){
    
}
Examinfor::Examinfor(string name,bool pass):name(name),mode(PASS),pass(pass){
    
}
Examinfor::Examinfor(string name,int mark):name(name),mode(MARK),mark(mark){
    
}
void Examinfor::show(){
    cout<<name<<":";
    switch(mode){
        case GRADE:cout<<grade;break;
        case PASS:cout<<(pass?"PASS":"FAIL") ;break;
        case MARK:cout<<mark;break;
        default:break;
    }
    cout<<endl;
}
int main(){
    Examinfor course1("Chinese",'A');
    Examinfor course2("Math",true);
    Examinfor course3("English",100);
    course1.show();
    course2.show();
    course3.show();
    return 0;
}
~~~

### 枚举类

之前的简单枚举类型只是整数集的子集，此处为强类型枚举

枚举类定义：

+ 语法形式：enum class枚举类型名:底层类型{枚举值列表}
+ 其中底层类型默认为int型
+ 也可在定义时指定枚举元素值

枚举类的优势：

+ 强作用域，其作用域限制在枚举类中，不同枚举类中可有相同枚举元素名
+ 转换限制，枚举类对象不可与整型隐式转换，无法直接比较不同的枚举类也无法直接与整数比较（这里枚举类对象就是前面的枚举变量）
+ 可指定底层类型

---

## 第五章 数据的共享与保护

变量和对象定义的位置不同，则作用域、可见性、生存期都不同

+ 作用域：在什么地方起作用
+ 可见性：即使在作用域内也不一定可见
+ 生存期

静态数据成员：属于整个类的数据成员

静态函数成员：用来处理静态数据成员的函数

友元： 类外需要频繁获取类中的数据，调用类中公有类型函数成员去获取数据的开销比较大，通过friend关键字声明为友元，给类外的函数或其他类预授权，使其可以访问该类的私有成员，提高访问效率

通过const关键字，限制对共享数据的修改（常类型）

编译预处理指令

多文件结构

---

### 标识符作用域与可见性

  作用域分类：

+ 函数原型作用域
+ 局部作用域（块作用域）
+ 类作用域
+ 文件作用域
+ 命名空间作用域

函数原型作用域：

+ 函数原型中参数的作用域
+ 范围：声明函数原型时，形参表括号的范围内
+ 声明函数原型时可以只给出形参类型，因为函数原型作用域范围很小，作用于范围内不使用变量名，离开括号作用域就结束了，但给出变量名可读性更好

局部作用域：

+ 函数的形参，在块中声明的标识符的作用域
+ 范围：自声明处起，到其所在块的括号处结束

类作用域：

+ 类的成员的作用域
+ 范围：包括类体和成员函数体
+ 在类作用域以外访问类的成员：
  + 静态成员：可通过类名、对象名、对象引用来访问
  + 非静态成员：可通过类名、对象名、对象引用、对象指针来访问

文件作用域：

+ 不在前面几个作用域中的声明具有文件作用域
+ 范围：自声明处起，到文件末尾结束

---

可见性：

+ 从标识符可见性的角度来谈的概念
+ 表示从内层作用域向外层作用域能看见什么
+ 如果标识符在某处可见，则可在该处引用此标识符
  + 若某个标识符在外层作用域声明，且内层作用域未声明同名标识符，则外层标识符在内层可见
  + 若内层作用域与外层作用域声明了同名的标识符，则外层标识符在内层不可见

### 对象的生存期

对象从产生到结束的时间段，生存期内，对象将保持它的值，直到被更新

此处的对象既可以指对象成员定义次序也可以指数据成员

分为静态生存期和动态生存期：

+ 静态生存期：

  + 静态生存期与程序运行期相同

  + 文件作用域中声明的对象、在块作用域中用static关键字声明的对象具有静态生存期

+ 动态生存期：
  + 开始于程序运行到声明点，到标识符作用域结束处结束
  + 块作用域中未用static关键字声明的对象具有动态生存期

### 类的静态数据成员与静态函数成员

静态数据成员：

+ 用关键字static声明，具有静态生存期
+ 属于整个类的数据成员，为该类所有对象所共享
+ 必须在类外定义和初始化，用"::"指明所属的类

静态函数成员：

+ 用关键字static声明，用来处理静态数据成员
+ 前面声明的数据成员和函数成员都是属于某个对象的，需要通过对象来访问，而静态数据成员属于整个类，需要有函数能单独处理静态数据成员，这就是静态函数成员
+ 可通过类名、对象名调用静态函数成员
+ 用来处理静态数据成员的函数
+ 与非静态函数成员的区别在于：非静态函数成员知道调是哪个对象调用它，静态函数成员不知道是哪个对象调用它
+ 要想处理非静态数据成员，就得把要处理的对象当作参数传递给静态函数成员

### 类的友元

友元是一种破坏封装和数据隐藏的机制，应尽量不使用

通过声明为友元，一个模块可以引用另一个模块中被隐藏起来的信息

友元关系是单向的

包括友元函数和友元类：

+ 友元函数：
  + 在类中用friend关键字声明的非成员函数
  + 友元函数的函数体中可通过对象名访问类中的私有类型成员和保护类型成员
  + 作用是增加灵活性，可以平衡封装和效率 
+ 友元类：
  + 在类中用friend关键字声明的类
  + 友元类中的所有成员都能访问对方类中的私有类型成员和保护类型成员

### 共享数据的保护

常类型：

+ 常对象：
  + 声明形式：const 类名 对象名
  + 定义时必须要初始化，不能被更新
  + 只能调用类的常函数成员
+ 常成员：
  + 用const关键字声明的类成员
  + 包括常数据成员和常函数成员
    + 常函数成员：
      + 用const关键字声明的函数成员
      + 常函数成员不更新对象的数据成员
      + 声明形式：类型说明符 函数名(形参表) const；
      + const关键字可用于重载函数的区分
      + 通过常对象只能调用常函数成员，但普通对象也能调用常函数成员
    + 常数据成员：
      + 用const关键字声明的数据成员
      + 只能在初始化处赋值，之后不能被更新
+ 常引用：
  + 用const关键字声明的引用
  + 声明形式：const 类型说明符 &引用名
  + 被引用的对象不能被更新
  + 既能获得较高的执行效率，也能保证实参的安全性
+ 常数组：
  + 声明形式：类型说明符 const 数组名[大小]
  + 数组元素不能被更新
+ 常指针：指向常量的指针
  + 不能通过指针去改变所指对象的值

### 多文件结构和编译预处理命令

C++程序组织结构：

+ 一个工程可以划分多个源文件
  + 类声明文件（.h文件）
  + 类实现文件（.cpp文件）
  + 类使用文件（主函数所在的.cpp文件）
+ 利用工程来组织各文件
+ 类实现文件和类使用文件分别编译后，加上已编译好的系统文件，连接生成可运行文件

外部变量：

+ 既能在定义变量的源文件，也能在其他文件中使用
+ 文件作用域中定义的变量默认为外部变量
+ 在其他文件中时使用外部变量要用extern关键字声明

外部函数：

+ 不在类中声明的函数（非成员函数）
+ 都具有文件作用域，可在不同的编译单元中调用
+ 调用前需进行引用性声明，即声明函数原型

将变量和函数限制在编译单元内：

+ 在匿名命名空间内定义的变量和函数不会暴露给其他编译单元
+ 声明形式：namespace{成员变量和成员函数}

标准C++库：

+ 可重用软件模块的集合
+ 标准C++类与组件分为；
  + 输入输出类
  + 容器类与抽象数据类型
  + 存储管理类
  + 算法
  + 错误处理
  + 运行环境支持

---

编译预处理指令：

+ #include包含指令：
  + 将源文件嵌入到当前源文件中该点处
  + #include<文件名>表示按标准模式搜索，文件位于C++系统目录的include子目录下
  + #include"文件名"表示先在当前目录搜索，再按标准模式搜索
+ #define宏定义指令
  + 定义符号常量，大多情况被const定义语句替代
  + 定义带参数宏，已被内联函数取代
+ #undef
  + 用来删除由#define定义的宏
+ 条件编译指令
  + #if 常量表达式 程序正文 #endif：常量表达式非零时编译程序正文
  + #if 常量表达式 程序正文1 #else 程序正文2 #endif：常量表达式非零时编译程序正文1，为零编译程序正文2
  + #if 常量表达式1 程序正文1 #elif 常量表达式2 #else 程序正文3 #endif：常量表达式1非零，编译程序正文1；常量表达式2非零，编译程序正文2；否则编译程序正文3
  + #ifdef 标识符 程序段1 #else 程序段2 #endif：标识符定义过且未被删除，编译程序段1；否则编译程序段2
  + #ifndef 标识符 程序段1 #else 程序段2 #endif：标识符未被定义，编译程序段1；否则编译程序段2

~~~c++
//作用域、可见性
#include <iostream>
using namespace std;
void func(){
    int x=4;
    cout<<"x="<<x<<endl;
    cout<<"y="<<y<<endl;
}
int x=1,y=2;
int main(){
cout<<"Begin"<<endl;
cout<<"x="<<x<<endl;
cout<<"y="<<y<<endl;
cout<<"Evaluate x and y in main()"<<endl;
int x=3,y=4;
cout<<"x="<<x<<endl;
cout<<"y="<<y<<endl;
cout<<"Step into func()"<<endl;
func();
cout<<"Back into main()"<<endl;
cout<<"x="<<x<<endl;
cout<<"y="<<y<<endl;
return 0;
}
~~~

~~~c++
//静态成员、多文件结构
//头文件(.h文件)
class Client {
public:
	static void ChangeServerName(char name);
	static int GetClientNumber();
	static char ShowServerName();
private:
	static char ServerName;
	static int ClientNumber;
};
//实现文件(.cpp文件)
#include "client.h"
void Client::ChangeServerName(char name) {
	Client::ServerName = name;
	Client::ClientNumber ++;
}
int Client::GetClientNumber() {
	return Client::ClientNumber;
}
char Client::ShowServerName() {
	return Client::ServerName;
}
//主函数文件(.cpp文件)
#include <iostream>
#include "client.h"
using namespace std;

int Client::ClientNumber = 0;
char Client::ServerName = 'a';

int main() {
	Client c1;
	c1.ChangeServerName('b');
	cout << c1.GetClientNumber() << endl;
	cout << Client::ShowServerName() << endl;//调用函数要加括号，否则不会调用函数并胡乱输出
	Client c2(c1);
	c2.ChangeServerName('c');
	cout << c2.GetClientNumber() << endl;
	cout << Client::ShowServerName() << endl;
	return 0;
}
~~~

## 第六章 数组 指针 字符串

数组可用来存储相同类型的数据或对象，并以顺序的方式来访问，适合处理大规模的数据

指针是用来存放内存地址的数据类型，可以是数据地址或函数地址，可用来访问数据和调用函数

面向对象的数组vetcor

深拷贝：通过指针可获得动态内存分配的地址，若将指针赋给类的数据成员，发生复制构造时，浅拷贝就无法完成复制构造

用字符数组和String类处理字符串，不同类型数据都有变量去存放常量，而前面内容只介绍了字符串常量

### 数组的定义与使用

数组是若干相同类型变量的集合体

组成数组的变量称为数组元素

数组元素之间具有顺序关系

数组的定义：

+ 声明形式：类型说明符 数组名 [ 常量表达式 ]
+ 数组名的构成方法与一般变量名相同

数组元素的使用：

+ 数组必须先定义后使用
+ 可以逐个引用数组元素（和引用普通变量差不多）

~~~c++
//数组
#include <iostream>
using namespace std;
int main(){
    int a[10],b[10];
    for(int i=0,i<10,i++){
        a[i]=2*i+1;
        b[9-i]=a[i];
    }
    for(int i=0,i<10,i++){
        cout<<"a["<<i<<"]="<<" ";
        cout<<"b["<<i<<"]="<<endl;
    }
    return 0;
}
~~~

### 数组的存储与初始化

一维数组的存储：

+ 数组元素在内存中顺序存储，逻辑上相邻对应物理地址上相邻
+ 数组名是数组首元素的地址，是一个常量不能被赋值

一维数组的初始化：

+ 两种初始化方式：
  + 列出全部元素的初始值
  + 只给出前几个元素的初始值
+ 列出全部元素初始值时，可以不指定数组长度（即下标个数可以省略）

---

二维数组的存储：

+ 按行存放，在内存中顺序存储
+ 数组名是数组首元素的地址，数组名带一个下标（数组名[i]）是各行首元素的地址，都是常量不能被赋值

二维数组的初始化：

+ 两种初始化方式：
  + 在一个花括号内列出全部元素的初始值
  + 分行列出二维数组元素的初始值
    + 将各行元素用花括号括起来
    + 各行内可只对前几个元素初始化
+ 列出全部初始值时第一维下标个数可以省略
+ 局部作用域中的非静态数组如果没初始化，会存放垃圾数据
+ 局部作用域中的静态数组会默认初始化为零
+ 如果只对部分元素初始化，剩下元素会自动初始化为零

~~~c++
//求Fibonacci数列前二十项，将结果存放于数组中
#include <iostream>
using namespace std;
int mian(){
    int F[20]={1,1};
    for(i=2;i<20;i++)
        F[i]=F[i-1]+F[i-2];
    for(i=0;i<20;i++){
        if(i%5==0)
            cout<<endl;
        cout.width(12);
        cout<<F[i];
    }
    return 0;
}
~~~

### 数组作为函数参数

数组元素只能作实参，与单个变量是一样的

数组做函数参数：

+ 形参和实参都应该是数组名，且类型相同
+ 传送的是数组首地址
+ 对形参数组的改变会影响到实参数组
+ 若果不希望形参数组影响到实参数组，可以传递常数组

~~~c++
//使用数组名作为函数参数
#include <iostream>
using namespace std;
void CalcuRow(int A[][5],int nRow){
    for(int i=0;i<nRow;i++)
        for(int j=1;j<5;j++)
            A[i][0]+=A[i][j];
}
int main(){
    int B[3][5]={{1,2,3,4,5},{2,3,4,5,6},{3,4,5,6,7}};
    for(int i=0;i<3,i++){
        for(int j=0;j<5;j++){
            cout.width(12);
            cout<<B[i][j];
        }
        cout<<endl;
    }
    CalcuRow(B,3);
    for(i=0;i<3;i++)
        cout<<"数组B的第"<<i+1<<"行元素之和为:"<<B[i][0]<<endl;
    return 0;
}
~~~

### 对象数组

若干相同类型对象的集合，数组元素都是同一个类的对象

对象数组的定义与访问：

+ 声明形式：类名 数组名[元素个数]
+ 访问类成员语法形式：数组名[元素下标].类成员名

对象数组的初始化：

+ 每个数组元素初始化时，都会调用类的构造函数（对象数组的元素是类的对象）
+ 定义对象数组时，如果没有给出对象的初始值，则调用默认构造函数初始化

对象数组元素的构造与析构：

+ 定义对象数组时，若类中未声明构造函数，则调用类的默认构造函数
+ 各元素对象初始值相同时，可在类中声明带有默认参数值的构造函数
+ 各元素对象的初始值不同时，可以在类中声明带形参的构造函数
+ 每一个元素对象被删除时，都会调用析构函数

~~~c++
//对象数组定义、初始化、访问类成员
#include <iostream>
using namespace std;
class Point{
    public:
    Point(int x,int y);//带形参的构造函数
    Point();//无形参的默认构造函数
    ~Point();
    void Move(int xnew,int ynew);
    void ShowPoint();
    static void ShowCount();
    public:
    int x,y;
    static int count;
};

int Point::count=0;//静态成员变量要在类外给出初始值

Point::Point(int x,int y):x(x),y(y){
    cout<<"构造了一个点类对象"<<endl;
    count++;
}
Point::Point():x(0),y(0){
    cout<<"构造了一个点类对象"<<endl;
    count++;
}
Point::~Point(){
    cout<<"析构了一个点类对象"<<endl;
}
void Point::Move(int xnew,int ynew){
    cout<<"Move the point to:("<<xnew<<","<<ynew<<")"<<endl;
    x=xnew;
    y=ynew;
}
void Point::ShowPoint(){
    cout<<"点的横坐标为:"<<x<<";"<<"点的纵坐标为:"<<y<<endl;
}
void Point::ShowCount(){
    cout<<"对象的数量是："<<count<<endl;
}
int main(){
    Point::ShowCount();
    Point A[2];
    Point B[2]={Point(1,2),Point(3,4)};
    Point::ShowCount();
    A[0].ShowPoint();
    A[1].ShowPoint();
    B[0].ShowPoint();
    B[1].ShowPoint();
    A[0].Move(5,6);
    A[1].Move(7,8);
    B[0].Move(9,10);
    B[1].Move(11,12);
    A[0].ShowPoint();
    A[1].ShowPoint();
    B[0].ShowPoint();
    B[1].ShowPoint();
    return 0;
}
~~~

### 基于范围的for循环

语法形式：for(类型说明符 & e : 数组名){对数组元素e的处理}

### 指针的概念、定义和指针运算

内存空间访问方式：

+ 通过变量名访问
+ 通过地址访问

指针的概念：

+ 指针：内存地址，用于间接访问内存单元
+ 指针变量：用于存放地址的变量
+ 也就是说，指针是指内存空间中存放的地址，指针变量是指与该内存空间结合起来的变量名
+ 定义指针变量与定义普通变量都是将变量名与内存空间结合起来，只不过指针变量的内存空间只允许存放合法途径获得的地址

指针变量定义：

+ 语法形式：类型说明符* 指针变量名
+ 只能用合法获得的地址去初始化指针变量
+ 此处类型说明符是用来确定指针变量存储的地址中存放的数据类型
+ 定义指针的目的是为了通过地址访问数据，因此必须要知道地址中存放的数据类型

指针变量的使用：

+ 语法形式：*指针变量名=与类型说明符对应的数据（给指针所指向的内存空间中放数据）
+ 先找到指针变量中存储的地址所对应的内存空间，再将数据放入此内存空间中 
+ 存放的数据类型由定义指针变量时的类型说明符决定

与地址相关的运算：

+ 指针运算符*：找到地址变量中存放的地址所对应的内存空间
+ 地址运算符&：取出与变量结合的内存空间对应的地址

### 指针变量的初始化和赋值

指针变量的初始化：

+ 语法形式：类型说明符* 指针变量名=初始地址
+ 可用变量地址做指针变量初始值
  + 变量必须在指针变量初始化前已声明
  + 变量类型与指针类型要一致
+ 可用已有合法值的指针去初始化新指针
+ 不能用非静态变量初始化静态指针
  + 因为静态对象生存期大于非静态，非静态变量生存期结束后，指针就被迫成了无指向，不利于内存空间安全管理

指针变量的赋值运算：

+ 语法形式：指针名=地址；
  + 地址中存放的数据类型要与指针类型一致
  + 向指针变量赋的值必须是地址常量或地址变量，而不能是普通整数
+ 必须用合法获得的地址来赋值
  + 通过地址运算符&求得的已定义变量或对象的起始地址
  + 动态内存分配成功时返回的地址
+ 整数0或"nullptr"赋值给指针表示空指针
+ 允许声明和定义void类型的指针，该指针只能存放地址，而不能访问地址的数据

~~~c++
//指针定义、赋值、使用、无类型指针
#include <iostream>
using namespace std;
int main(){
    int i;
    int* ptr1=&i;//用已定义的变量的地址初始化指针
    void* ptr2=&i;
    int* ptr3=static_cast<int*>(ptr2);//用已有合法值的指针初始化新指针，将void类型指针强制类型转换为int型指针
    i=10;
    cout<<"i="<<i<<endl;//通过变量名访问内存空间
    cout<<"*ptr1="<<*ptr1<<endl;//通过指针访问内存空间
    cout<<"*ptr3="<<*ptr3<<endl;
    return 0;
}
~~~

指向常量的指针：

+ 声明形式：const 类型说明符* 指针变量名
+ 不能通过指向常量的指针去改变所指对象的值
  + 指向常量的指针既可以指向变量也可以指向常量
  + 只不过不能通过指针去改变所指对象的值
  + 指针本身是可以改变的，可以去指向其他的对象
  + 如果指向常量的指针指向的是变量，仍然可以通过变量名改变变量的值

指针类型的常量：

+ 声明形式：类型说明符* const 指针变量名；
+ 指针本身的值不能改变（指针变量中存放的地址是个常量）
+ 指向某个对象之后，不能修改为指向其他对象

### 指针的算术运算与关系运算

指针类型的算术运算：

+ 指针加上或减去整数n
  + 意思是当前指向位置的前方或后方第n个数据的起始位置
+ 自增（++）、自减（--）运算
  + 当前指向位置的下一个或前一个数据的起始位置
+ 运算的结果取决于指针指向的数据类型（指针算术运算不是按字节算，而是按数据个数算）
+ 只有当指针指向连续存储的同类型数据时，指针的算术运算才有意义（不然算数运算后都不知道指向什么东西，内存也不安全）

指针类型的关系运算：

+ 只有指向相同数据类型的指针之间可进行关系运算
+ 指向不同数据类型的指针之间、指针与一般整型变量之间不能进行关系运算
+ 指针和整数0之间可进行等于或不等于的关系运算

 ~~~c++
 //编写转置函数，实现输入输出
 #include <iostream>
 using namespace std;
 void Turnover(int A[][],int n){
     int B[n][n]={0};
     for(int i=0;i<n;i++)
         for(int j=0;j<n;j++)
             B[j][i]=A[i][j];
     for(int i=0;i<n;i++)
         for(int j=0;j<n;j++)
             A[i][j]=B[i][j];
 }
 int main(){
     int C[3][3]={{1,2,3},{4,5,6},{7,8,9}};
     Turnover(C,3);
     for(i=0;i<3;i++){
         for(j=0;j<3;j++)
             cout<<C[i][j]<<"    ";
         cout<<endl;
     }
     return 0;
 }
 ~~~

### 用指针访问数组元素

定义指向数组元素的指针：

+ 定义与赋值

  + 定义相同类型的数组与指针，并将数组的起始地址赋值给指针

  + 语法形式：类型说明符 数组名[数组元素个数]，*指针名；

    ​                    指针名=数组名；（或  指针名=&数组名[0])

  + 此时直接通过“cout<<指针名”就可以输出数组元素

  + 等效形式：

    + *指针名=数组名[0]；

      *(指针名+1)=数组名[1];

      *(指针名+i)=数组名[i];
  
    + 数组名[i]=*(指针名+i)= *(数组名+i)=指针名[i]

### 指针数组

数组的元素是指针类型（也就是地址）

声明形式：类型说明符* 数组名[数组元素个数]

可以用指针数组表示二维数组：

+ 不同行之间存放的地址无连续关系,而二维数组是按行存放，且各行是连续存放的
+ 指针数组的数组元素是二维数组元素各行组成的一维数组的起始地址
+ 指针数组的数组元素可以是 元素个数不相同的数组的起始地址

~~~c++
//用指针数组存放二维数组，并将所有元素并输出
#include <iostream>
using namespace std;
int line1[3]={1,2,3};
int line2[3]={4,5,6};
int line3[3]={7,8,9};
int main(){
    int* pline[3]={line1,line2,line3};
    for(i=0;i<3;i++){
        for(j=0;j<3;j++)
            cout<<pline[i][j]<<"    ";
        cout<<endl;
    }
    return 0;
}
~~~

### 指针作为函数参数

使用指针做函数参数的情形：

+ 需要数据双向传递时（引用也可以实现数据双向传递）
+ 需要传递一组数据时，只传首地址的运行效率比较高

调用指针做形参的函数，相当于把主调函数的数据访问权限传给该函数，会直接修改主调函数中的数据

如果不想修改主调函数中的数据，可以用指向常量的指针作为形参

~~~c++
//将输入的浮点数整数部分和小数部分分开
#include <iostream>
using namespace std;
void SplitFloat(float x,int* intpart,float* floatpart){
    *intpart=static_cast<int>(x);
    *floatpart=x-*intpart;
}
int main(){
    int n;
    float x,f;
    cout<<"Please enter a float number:"<<endl;
    cin>>x;
    SplitFloat(x,&n,&f);//调用指针做形参的函数，相当于将变量所在内存空间的访问权限传送给该函数
    cout<<"Intpart is:"<<n<<";Floatpart is:"<<f<<endl;
    return 0;
}
~~~

### 指针类型的函数

函数返回值是指针类型（一个地址），该函数就是指针类型的函数

定义形式：存储类型 数据类型 *函数名(){函数体语句}

不能将非静态的局部地址用作函数的返回值

+ 不能将子函数中定义的局部变量的地址返回给主函数
+ 非静态局部变量作用域和生存期仅限于本函数体内，将失效的地址返回给主调函数不利于内存空间安全管理

正确使用指针类型函数的情形：

+ 可以将主函数中定义的变量或数组元素的地址返回
+ 在子函数中通过动态内存分配获得的内存地址返回给主函数，但是要注意不能忘记释放，造成内存泄露

~~~c++
//将主函数中定义的数组元素地址返回
#include <iostream>
using namespace std;
int *func(int *ptr,int num){
    for(i=0,i<3,i++)
        if(ptr[i]==11)
            return &ptr[i];
}
int main(){
    int A[3]={10,11,12};
    int *ptr2=func(A,3);//用函数返回的地址初始化新指针，一般都这样调用指针类型的函数
    cout<<*ptr2<<endl;
    return 0;
}
~~~

### 指向函数的指针

指针里存放的是函数地址，就是指向函数的指针

函数指针指向的是程序代码存储区

函数指针的定义形式：存储类型 数据类型 (*函数指针名)(形参表);

+ 第一个括号说明是一个指针类型
+ 第二个括号说明是指向函数的指针
+ 前面内容说明函数的返回类型
+ 函数原型在定义中都有体现

函数指针的用途是实现函数回调：

+ 通过函数指针调用函数，在处理相似事件时，可以灵活地将不同的函数的指针作为参数传递给调用函数
+ 调用者不用关心谁是被调用者，只需知道存在一个具有特定原型和限制条件的被调用函数

函数重载可以实现对不同类型数据的相同运算，函数指针可实现对相同类型数据的不同运算（将多个函数集中到一个函数中）

~~~c++
//编写一个函数，实现对两个整数的不同运算
#include <iostream>
using namespace std;
int sum(int x,int y){
    return x+y;
}
int max(int x,int y){
    return (x>y? x:y);
}
int min(int x,int y){
    return (x<y? x:y);
}
int compute(int (*func)(int x,int y),int a,int b){
    return func(a,b);//将函数指针作为形参，就可以直接函数体中调用函数，函数地址赋给指向函数的指针后，指针名可直接当作函数名使用
}
int main(){
    int x=5,y=6;
    cout<<compute(&sum,x,y)<<endl;//也可以直接用函数名做实参，函数名就是函数代码的首地址
    cout<<compute(&max,x,y)<<endl;
    cout<<compute(&min,x,y)<<endl;
    return 0;
}
~~~

### 对象指针  

 指针变量中存放的是对象的地址，就是对象指针

对象指针定义形式：类名 *对象指针名；

通过指针访问对象成员

+ 语法形式：对象指针名->成员名
+ 相当于(*对象指针名).成员名

this指针：

+ 指向当前对象自己的指针
+ 隐含于类的每一个非静态成员函数中
+ 用来指明成员函数所操作的对象
+ 对象调用成员函数时，隐含的将当前对象的地址传给了成员函数的this指针，这样成员函数就知道要对哪个对象产生操作

### 动态分配与释放内存

静态内存分配的不足：

+ 前面介绍的数组不能用变量来表示数组元素的个数，必须在定义时就确定数组规模
+ 当不知道数组规模时，分配内存空间少了不够用，多了则浪费内存空间

动态申请内存操作符new：

+ 动态申请内存语法形式：new 类型名T(初始化参数列表)
+ 在程序运行期间，动态申请用于存放T类型对象的内存空间，并按照初始化参数列表初始化对象（申请空间之前会调用构造函数来构造对象）
+ 若申请成功，则返回T类型指针（申请的内存空间的首地址）；若申请失败，则抛出异常

释放内存操作符delete：

+ 释放内存语法形式：delete 指针名；
+ 释放指针所指向的内存，此处指针是指用于接收new操作返回的指针
+ 释放内存之前会调用析构函数来析构对象

### 申请和释放动态数组

分配和释放动态数组：

+ 分配：new 类型名T[数组长度]；
  + 数组长度可以是任何整数类型表达式，在运行时计算
+ 释放：delete[] 数组名
  + 释放指针所指向的数组，指针是new分配得到的数组首地址
  + 如果没有方括号，就只会释放数组首元素的地址

动态创建多维数组：

+ 语法形式：new 类型名T[第一维长度] [第二维长度]；

+ 通过这种方式只能动态创建列数固定行数不固定的数组

+ 若申请成功，返回指向新分配内存空间首地址的指针

+ 需要用指向数组的指针来接收new操作返回的指针

+ 动态创建多维数组返回的指针是指向数组的指针，指针算术运算会跳跃整行元素的内存空间

+ 例子：char (*A)[3];//创建多维动态数组，需要指向数组的指针来接收new操作返回值,此处数组元素的个数不能是变量

  ​            A=new char[2] [3];

  ​            delete[] A;

+ 释放：delete[] 数组名

将动态数组封装成类：

+ 简洁且便于管理
+ 可在访问数组元素前检查下标是否越界

~~~c++
//将动态数组封装成类
#include <iostream>
#include <cassert>
using namespace std;
class Point {
public:
	Point(int x, int y);//带形参的构造函数
	Point();//无形参的默认构造函数
	~Point();
	void Move(int xnew, int ynew);
	void ShowPoint();
	static void ShowCount();
public:
	int x, y;
	static int count;
};

int Point::count = 0;//静态成员变量要在类外给出初始值

Point::Point(int x, int y) :x(x), y(y) {
	cout << "构造了一个点类对象" << endl;
	count++;
}
Point::Point() : x(0), y(0) {
	cout << "构造了一个点类对象" << endl;
	count++;
}
Point::~Point() {
	cout << "析构了一个点类对象" << endl;
}
void Point::Move(int xnew, int ynew) {
	cout << "Move the point to:(" << xnew << "," << ynew << ")" << endl;
	x = xnew;
	y = ynew;
}
void Point::ShowPoint() {
	cout << "点的横坐标为:" << x << ";" << "点的纵坐标为:" << y << endl;
}
void Point::ShowCount() {
	cout << "对象的数量是：" << count << endl;
}
class ArrayOfPoints{
    punlic:
    ArrayOfPoints(int size):size(size){
        points=new Point[size];
    }
    ~ArrayOfPoints(){
        cout<<"Deleting"<<endl;
        delete[] points;
    }
    Point& element(int index){//返回值类型设为引用类型，才能对访问的数组元素进行修改，否则就仅仅是一个访问数组元素的函数
        assert(index>=0&&index<size);//下标越界检查
        return points[index];
    }
    private:
    Point *points;//动态创建对象数组，需要用指向对象的指针来接收new操作返回值
    int size;//数组元素个数，用于下标越界检查
};
int main(){
    int count;
    cin>>count;
    ArrayOfPoint points(count);
    points.element(0).Move(5,6);
    points.element(0).ShowPoint();
    return 0;
}
~~~

### 智能指针

C++11智能指针：

+ unique_ptr：不允许多个指针共享资源，可用标准库中move函数转移指针
+ shared_ptr：多个指针共享资源
+ weak_ptr：可以复制shared_ptr，但其释放和构造对资源不产生影响

### vector对象

vector是一个类模板，确定类型参数后，就会生成封装了相应类型动态数组的类

vector的作用：

+ 封装任何类型的动态数组，自动创建和删除
+ 数组下标越界检查

vector对象的定义：

+ 语法形式：vector <元素类型> 数组对象名(数组长度)；
+ vector<int> arr(5);意思是创建大小为5的int类型数组

vector对象的使用：

+ 对数组元素的引用。形式上与引用普通数组元素相同，都是通过下标的方式
  + 语法形式：vector对象名[下标表达式]
  + vector数组对象名不表示数组首地址
+ 用size函数获得数组长度（也就是数组元素个数）
  + 语法形式：vector数组对象名.size();

### 浅层复制与深层复制

浅层复制：

+ 实现对象间数据元素的一一对应复制
+ 如果类中存在动态内存分配获得的指针类型数据成员，用已有对象去初始化新对象时，调用默认复制构造函数，会使得两个对象的指针类型成员指向相同的内存空间，此时浅层复制就不够用了

深层复制：

+ 通过添加复制构造函数实现深层复制
+ 在复制构造函数中通过动态内存分配返回新的指针，赋值给对象的指针类型成员，并将两个对象的指针类型成员所指向的内存空间中的数据一一对应复制

~~~c++
//深层复制
#include <iostream>
#include <cassert>
using namespace std;
class Point {
public:
	Point(int x, int y);//带形参的构造函数
	Point();//无形参的默认构造函数
	~Point();
	void Move(int xnew, int ynew);
	void ShowPoint();
	static void ShowCount();
public:
	int x, y;
	static int count;
};

int Point::count = 0;//静态成员变量要在类外给出初始值

Point::Point(int x, int y) :x(x), y(y) {
	cout << "构造了一个点类对象" << endl;
	count++;
}
Point::Point() : x(0), y(0) {
	cout << "构造了一个点类对象" << endl;
	count++;
}
Point::~Point() {
	cout << "析构了一个点类对象" << endl;
}
void Point::Move(int xnew, int ynew) {
	cout << "Move the point to:(" << xnew << "," << ynew << ")" << endl;
	x = xnew;
	y = ynew;
}
void Point::ShowPoint() {
	cout << "点的横坐标为:" << x << ";" << "点的纵坐标为:" << y << endl;
}
void Point::ShowCount() {
	cout << "对象的数量是：" << count << endl;
}
class ArrayOfPoints {
public:
	ArrayOfPoints(int size):size(size) {
		points = new Point[size];
		cout << "构造了ArrayOfPoints对象" << endl;
	}
	ArrayOfPoints(const ArrayOfPoints& A);//复制构造函数
	~ArrayOfPoints() {
		cout << "析构了ArrayOfPoints对象" << endl;
		delete[] points;
	}
	Point& element(int index) {//返回值类型设为引用类型，才能对访问的数组元素进行修改，否则就仅仅是一个访问数组元素的函数
		assert(index >= 0 && index < size);//下标越界检查
		return points[index];
	}
private:
	Point* points;//动态创建对象数组，需要用指向对象的指针来接收new操作返回值
	int size;//数组元素个数，用于下标越界检查
};
ArrayOfPoints::ArrayOfPoints(const ArrayOfPoints& A) {
	size = A.size;
	points = new Point[size];
	for (int i = 0; i < size; i++)
		points[i] = A.points[i];
	cout << "复制构造了ArrayOfPoints对象" << endl;
}
int main() {
	ArrayOfPoints point1(2);
	ArrayOfPoints point2(point1);
	point1.element(0).Move(5, 6);
	point1.element(1).Move(7, 8);
	for (int i = 0; i < 2; i++) {
		point1.element(i).ShowPoint();
		point2.element(i).ShowPoint();
	}
	return 0;
} 
~~~

### 移动构造

 将源对象资源的控制权全部交给目标对象

移动构造函数：

+ 语法形式：类名(类名 && 对象名)；
+ 使用场景：临时对象即将消亡，但对象资源接下来还要利用
+ 函数体中可以用形参对象的指针数据成员初始化新对象的指针数据成员，再将形参对象指针数据成员设为空指针

移动构造的案例：

+ 函数返回值是对象时，函数执行完后函数体中定义的对象就消亡了，返回结果之前会调用复制构造函数，复制构造一个临时无名的对象

+ 添加移动构造函数之后，直接通过移动构造将函数体中对象的资源给临时无名的对象，不用通过复制构造创建无名对象，效率更高

### C风格字符串

字符串常量：

+ 各字符连续、顺序存放，每个字符占一个字节，以'\0'结尾
+ 相当于一个隐含创建的字符常量数组
+ "字符串"是字符数组的首地址，可以赋给字符类型常指针

用字符数组存储字符串：

+ 语法形式：char 字符数组名[数组长度]="字符串";

  ​                   char 字符数组名[]="字符串";

  ​                   char 字符数组名[数组长度]={'字符1','字符2','\0'};                    

+ 缺点：
  + 操作麻烦
    + 执行连接、拷贝、比较等操作需要显式调用库函数
    + 当字符串长度不确定时，需要动态创建字符数组，后面还需要delete释放
  + 可能会产生数组下标越界错误
    + 字符串长度可能大于分配的空间
    + 可能会越界访问数组元素

~~~c++
//章节例题
//编写矩阵转置函数，实现不同阶数矩阵输入与输出
#include <iostream>
using namespace std;
void Swap(int &x,int &y){
    int z=x;
    x=y;
    y=z;
}
int main(){
    int count;
    cout<<"输入矩阵的维数:"<<endl;
    cin>>count;
    int **ptr;//指向指针的指针，指针变量中存放的是指针
    ptr=int *A[count];//指针类型要和动态数组的元素类型相同。动态数组对应指针；动态对象数组对应指向对象的指针；动态指针数组对应指向指针的指针；动态多维数组对应指向数组的指针（此种方式只能创建行数不固定的数组）
    for(int i=0;i<count;i++)
        ptr[i]=new int[count];
    cout<<"输入"<<count*count<<"个矩阵元素："<<endl;
    for(int i=0;i<count;i++)
        for(int j=0;j<count;j++)
            cin>>Ptr[i][j];
    for(int i=0;i<count;i++)
        for(j=0;j<i;j++)
            Swap(ptr[i][j],ptr[j][i]);
    for(int i=0;i<count;i++){
        for(j=0;j<count;j++)
            cout<<ptr[i][j]<<"     ";
        cout<<endl;
    }
    return 0;
}
~~~

  ## 第七章 继承与派生

### 继承的基本概念和语法

继承与派生概述：

+ 继承：
  + 保持已有类的特性而构造新类的过程
  + 目的：实现设计与代码的重用
+ 派生：
  + 在已有类的基础上增加新特性而产生新类的过程
  + 目的：对原有类进行改造，以解决原有类无法解决的新问题
+ 基类：被继承的已有类
+ 派生类：派生出的新类
+ 直接基类：直接参与派生出新类的基类
+ 间接基类：基类的基类或更高层的基类

单继承：

+ 语法形式：class 派生类名：继承方式 基类名{成员声明;};

多继承：

+ 语法形式：class 派生类名：继承方式1 基类名1，继承方式2 基类名2{成员声明;};

派生类的构成：

+ 吸收的基类成员
  + 默认情况下，派生类包含基类中除构造和析构函数外的所有成员
  + C++11规定可用using语句继承基类的构造函数
+ 改造的基类成员
  + 派生类中声明和基类成员同名的新成员，会隐藏外层的同名成员
+ 添加的新成员
  + 派生类增加新成员使派生类在功能上有所发展

### 继承方式简介及公有继承

不同继承方式对派生类的影响：

+ 派生类成员对基类成员的访问权限
+ 通过派生类对象对基类成员的访问权限

三种继承方式：

+ 公有继承
+ 私有继承
+ 保护继承 

公有继承：

+ 继承的访问控制：
  + 基类的公有和保护成员在派生类中的访问属性不变
  + 基类的私有成员在派生类中不可直接访问
+ 访问权限：
  + 派生类成员可直接访问基类的公有和保护成员，但不能直接访问基类的私有成员(只能通过对外接口访问)
  + 通过派生类对象只能访问基类的公有成员

### 私有继承和保护继承

私有继承：

+ 继承的访问控制：
  + 基类的公有和保护成员在派生类中的访问属性都为私有类型
  + 基类的私有成员在派生类中不可直接访问
+ 访问权限：
  + 派生类成员可直接访问基类的公有和保护成员，但不能直接访问基类的私有成员(只能通过对外接口访问)
  + 通过派生类对象不能直接访问基类的任何成员

保护继承：

+ 继承的访问控制：
  + 基类的公有和保护成员在派生类中的访问属性都为保护类型
  + 基类的私有成员在派生类中不可直接访问
+ 访问权限：
  + 派生类成员可直接访问基类的公有和保护成员，但不能直接访问基类的私有成员(只能通过对外接口访问)
  + 通过派生类对象不能直接访问基类的任何成员

保护类型成员的特点与作用：

+ 特点：对于类成员来说，与公有成员性质相同；对类的对象来说，与私有成员性质相同
+ 作用：既能实现数据隐藏(通过对象无法直接访问)，又方便继承(派生类成员可直接访问)。

继承方式影响总结：

+ 三种继承方式下，派生类成员都可以直接访问基类的公有和保护成员，而不能直接访问基类的私有成员
+ 只有公有继承时，派生类对象可直接访问基类的公有成员

### 类型转换

派生类对象转换为基类对象：

+ 仅限于公有继承条件下
+ 只存在派生类对象转换为基类对象，反之不可
+ 派生类对象可被当作基类对象使用，派生类对象可隐含转换为基类对象
+ 转换为基类对象后，只能访问基类的成员和派生类的虚函数成员
+ 派生类对象可初始化基类的引用
+ 派生类的指针可隐含转换为基类的指针

通过基类对象名、指针只能访问基类的成员

### 派生类的构造函数

默认情况下：

+ 基类的构造函数不被继承
+ 派生类需要定义自己的构造函数

C++11规定：

+ 可用using语句继承基类的构造函数
+ 但只能初始化从基类继承的成员
+ 一般用在派生类很少或不增加数据成员的情况下
+ 语法形式：using 基类名::基类名;

若不继承基类的构造函数：

+ 派生类新增的成员由派生类构造函数初始化
+ 派生类继承的成员通过调用基类构造函数初始化
+ 派生类构造函数需要给基类构造函数传递参数

单继承时派生类构造函数：

+ 语法形式：派生类名::派生类名(基类所需的形参，派生类成员所需形参):基类名(参数表),本类成员初始化列表{其他初始化};

多继承时派生类构造函数：

+ 语法形式：派生类名::派生类名(基类所需的形参，派生类所需的形参):基类名1(参数表)，基类名2(参数表)本类成员初始化列表{其他初始化};

派生类与基类的构造函数：

+ 当基类有默认构造函数时
  + 派生类构造函数可以不向基类构造函数传递参数
  + 若不给基类构造函数传递参数，构造派生类对象时会调用基类的默认构造函数
+ 如需执行基类中带参数的构造函数
  + 派生类构造函数应给基类构造函数传递初始化参数

多继承且有对象成员时派生类构造函数：

+ 语法形式：派生类名::派生类名(形参表):基类名1(参数)，基类名2(参数)，包括对象成员在内的本类成员初始化列表{其他初始化};

派生类构造函数执行顺序：

+ 首先调用基类构造函数
  + 按照继承时声明的顺序调用不同基类的构造函数
+ 其次对初始化列表中的成员进行初始化
  + 按照在类中定义的次序进行初始化
  + 对象成员初始化会自动调用部件类的构造函数，由初始化列表提供参数
+ 执行派生类构造函数的函数体中的内容

### 派生类的复制构造函数

若派生类没有声明复制构造函数：

+ 编译器会在需要时生成一个隐含的复制构造函数
+ 先调用基类的复制构造函数再为派生类的新增成员执行复制

若派生类定义了复制构造函数：

+ 派生类复制构造函数要为基类的复制构造函数传递参数，并且传递的是派生类对象的引用
+ 复制构造函数只能接受一个参数，用来初始化派生类新定义的成员并给基类复制构造函数传递参数                                  
+ 派生类复制构造函数的形参类型为派生类对象的引用，实参为派生类对象的引用
+ 基类复制构造函数的形参类型为基类对象的引用，实参既可以是派生类对象的引用也可以是基类对象的引用

### 派生类的析构函数

析构函数不被继承，派生类如果需要，要自己声明析构函数

派生类析构函数声明形式与无继承关系时的析构函数相同（因为析构函数是无参数的）

系统会自动调用基类的析构函数

派生类析构函数执行顺序：

+ 先执行派生类析构函数的函数体
+ 再调用基类的析构函数

### 访问从基类继承的成员

当派生类与基类中有相同成员时：

+  若未特别限定，通过派生类对象访问的是派生类中的同名成员
+ 如果想通过派生类对象访问被隐藏的基类同名成员，需要用基类名和作用域操作符（::)来限定

二义性问题：

+ 如果从不同基类中继承了同名成员，且派生类中没有定义同名成员，通过“派生类对象名.成员名”访问成员就会存在二义性问题
+ 解决方式：用类名限定

### 虚基类

继承中出现的问题：

+ 当派生类从多个基类派生，而这些基类又有共同基类，则访问此共同基类中的成员时将产生冗余，并可能存在二义性问题

虚基类：

+ 声明形式：class 派生类名：virtual 继承方式 基类名；
+ 作用：
  + 解决多继承时对同一个基类继承多次而产生的二义性问题
  + 为最远的派生类提供唯一的基类成员，而不重复产生多次复制
+ 在第一级继承时就要将共同基类设计为虚基类

虚基类及其派生类构造函数：

+ 建立对象时所指定的类称为最远派生类
+ 虚基类的成员由最远派生类的构造函数调用虚基类的构造函数进行初始化 
+ 对于直接或间接继承虚基类的所有派生类，都必须在构造函数的初始化列表中为虚基类的构造函数传递参数，如果没有列出则表示调用虚基类的默认构造函数
+ 建立对象时，只有最远派生类的构造函数调用虚基类的构造函数，其他派生类对虚基类构造函数的调用会被忽略

~~~c++
//基类和派生类构造及析构函数
#include <iostream>
using namespace std;
class BaseClass{
    public:
    BaseClass(int x):Number(x){
        cout<<"构造了一个BaseClass对象"<<endl;
    };
    ~BaseClass(){
        cout<<"析构了一个BaseClass对象"<<endl;
    };
    int GetNumber(){
        return Number;
    }
    private:
    int Number=0;
};
class DerivedClass:public BaseClass{
    public:
    DerivedClass(int x):BaseClass(x){
        cout<<"构造了一个DerivedClass对象"<<endl;
    }
    ~DerivedClass(){
        cout<<"析构了一个DerivedClass对象"<<endl;
    }
}
int main(){
    DerivedClass myclass;
    mynumber=myclass.GetNumber();
    cout<<mynumber<<endl;
    return 0;
}
~~~

~~~c++
//多继承、虚基类
class Vehicle {
public:
	Vehicle(int MaxSpeed, int Weight) :MaxSpeed(MaxSpeed), Weight(Weight) {
		cout << "创建了一个Vehical对象" << endl;
	}
	~Vehicle() {
		cout << "析构了一个Vehical对象" << endl;
	}
	void Run() {
		cout << "车子运行" << endl;
	}
	void Stop() {
		cout << "车子停止" << endl;
	}
private:
	int MaxSpeed;
	int Weight;
};
class Bicycle : virtual public Vehicle {
public:
	Bicycle(int MaxSpeed, int Weight, int Height) :Vehicle(MaxSpeed, Weight), Height(Height) {
		cout << "构造了一个Bicycle对象" << endl;
	}
	~Bicycle() {
		cout << "析构了一个Bicycle对象" << endl;
	}
private:
	int Height;
};
class Motorcar :virtual public Vehicle {
public:
	Motorcar(int MaxSpeed, int Weight, int SeatNum) :Vehicle(MaxSpeed, Weight), SeatNum(SeatNum) {
		cout << "构造了一个Motorcar对象" << endl;
	}
	~Motorcar() {
		cout << "析构了一个Motorcar对象" << endl;
	}
private:
	int SeatNum;
};
class Motorcycle :public Bicycle,public Motorcar{
public:
	Motorcycle(int MaxSpeed, int Weight,int Height,int SeatNum) :Vehicle(MaxSpeed, Weight),Bicycle(MaxSpeed, Weight,Height),Motorcar(MaxSpeed, Weight,SeatNum) {
		cout << "构造了一个Motorcycle对象" << endl;
	}
	~Motorcycle() {
		cout << "析构了一个Motorcycle对象" << endl;
	}
};
int main() {
	Motorcycle mymotorcycle(120,200,160,25);
    mymotorcycle.Run();
	mymotorcycle.Stop();
	return 0;
}
~~~

## 第八章 多态性

### 运算符重载的规则

运算符重载是根据新类型数据的实际需要，对原有运算符进行适当的改造

运算符重载规则：

+ 只能重载C++中已有的运算符
+ C++中除若干运算符外，几乎所有运算符都可以重载
+ 不能重载的运算符包括"." ".*" "::" "?:"
+ 重载后运算符的优先级和结合性都不会变

两种重载方式：

+ 重载为类的非静态成员函数
+ 重载为非成员函数

### 双目运算符重载为成员函数

运算符重载为类的非静态成员函数：

+ 语法形式：函数类型 operator 运算符（形参）{函数体语句}
+ 参数个数=原操作数个数-1（后置++、--除外）//其中一个操作数变为了调用函数成员的对象

双目运算符重载规则：

+ 前操作数为类的对象，将操作符重载为类的函数成员，后操作数为实参
+ 重载后，“操作数1 运算符 操作符2”相当于”操作数1.运算符(操作数2)“

~~~c++
//将复数类加减法运算重载为成员函数
#include <iostream>
using namespace std;
class Complex{
    public:
    Complex(double real=0.0,double imag=0.0):real(real),imag(imag){}
    Complex operator +(const Complex &a){
        return Complex(real+a.real,imag+a.imag);
    }
    Complex operator -(const Complex &b){
        return Complex(real-b.real,imag-b.imag);
    }
    void Show(){
        cout<<"("<<real<<","<<imag<<")"<<endl;
    }
    private:
    double real,imag;
};
int main(){
    Complex c1(7,8),c2(5,6),c3;
    cout << "c1=";
	c1.Show();
	cout<< endl;
	cout << "c2="; 
	c2.Show();
	cout<< endl;
	c3 = c1 + c2;
	cout << "c1+c2=";
	c3.Show();
	cout<< endl;
	c3 = c1 - c2;
	cout << "c1-c2=";
	c3.Show();
	cout<< endl;
	return 0;
}
~~~

### 单目运算符重载为成员函数

前置单目运算符重载规则：

+ 操作符后面的数为类的对象，操作符为类的函数成员，无形参
+ 重载后，“运算符 操作数“相当于”操作数.运算符()"

后置单目运算符++和--重载规则：

+ 操作符前面的数为类的对象，操作符为类的函数成员
+ 要与前置运算符区分，后置运算符重载为成员函数要多一个int型形参
+ 重载后，“操作数 运算符”相当于“操作数.运算符(int)”

~~~c++
//将前置++和后置++重载为时钟类的成员函数
#include <iostream>
using namespace std;
class Clock {
public:
	Clock(int hour = 0, int minute = 0, int second = 0);
	void ShowTime() const;
	Clock& operator ++();
	Clock operator++(int x);
private:
	int hour, minute, second;
};
Clock::Clock(int hour, int minute, int second) {
	if (0 <= hour && hour < 24 && 0 <= minute && minute < 60 && 0 <= second && second < 60) {
		this->hour = hour;
		this->minute = minute;
		this->second = second;
	}
	else
		cout << "Time Error!" << endl;
}
void Clock::ShowTime() const {
	cout << hour << ":" << minute << ":" << second << endl;
}
Clock& Clock::operator ++() {//前置运算符返回值为对象的引用，并且是修改过后的对象
	second++;
	if (second >= 60) {
		second -= 60;
		minute++;
		if (minute >= 60) {
			minute -= 60;
			hour = (hour + 1) % 24;
		}
	}
	return *this;
}//前置++表示对数字加一并输出运算后的数字，并且能对返回的数字进行操作
Clock Clock::operator ++(int x) {//后置运算符只是返回运算之前的数字，返回的是对象的一个副本
	Clock old = *this;//后置自增运算需分配内存来保存原先的数值，相对前置自增效率要低
	++(*this);//此处调用前置++运算有返回值与后面返回值是否会冲突？
    //我的理解是后置重载函数调用前置重载函数，但是并没有接收返回值，只是通过调用函数完成了一些操作
	return old;
}//后置++表示对数字加一并输出运算前的数字
int main() {
	Clock myclock(23, 59, 59);
	cout << "初始时间为：";
	myclock.ShowTime();
	cout << endl;
	cout << "后置自增的输出时间为：";
	(myclock++).ShowTime();//后置自增虽然输出为自增前的数字，但是还是对数字进行了加一
	cout << endl;
	cout << "后置自增后的时间为：";
	myclock.ShowTime();
	cout << endl;
	cout << "前置自增的输出时间为：";
	(++myclock).ShowTime();
	cout << endl;
	cout << "前置自增后的时间为：";
	myclock.ShowTime();
	cout << endl;
	return 0;
}
~~~

### 运算符重载为非成员函数

运算符重载为非成员函数规则：

+ 操作数为实参，运算符为非成员函数
+ 参数个数=原操作数个数（后置++和--需要增加一个int型形参用来与前置++和--区分）
+ 至少应该有一个自定义类型的形参
+ 如果在运算符的重载函数中需要操作某类对象的私有成员，可以将此重载函数声明为类的友元
+ 重载后：
  + ”操作数1 运算符 操作数2“相当于”运算符(操作数1,操作数2)"
  + "运算符 操作数"相当于"运算符(操作数)"
  + "操作数 运算符"相当于"运算符(操作数,0)"

~~~c++
//重载复数类的加减法和"<<"运算符为非成员函数
#include <iostream>
using namespace std;
class Complex{
    public:
    Complex(double real=0.0,double imag=0.0):real(real),imag(imag){}
    friend Complex operator +(const Complex &a,const Complex &b);
    friend Complex operator -(const Complex &a,const Complex &b);
    friend ostream & operator <<(ostream &out,const Complex &a);//插入运算符是二元运算符，故此处有两个形参
    private:
    double real,imag;
};
Complex operator +(const Complex &a,const Complex &b){
    return Complex(a.real+b.real,a.imag+b.imag);//非成员函数声明为友元才能通过对象直接访问类的私有成员
}
Complex operator -(const Complex &a,const Complex &b){
    return Complex(a.real-b.real,a.imag-b.imag);
}
ostream & operator <<(ostream &out,const Complex &a){//插入运算符左操作数和返回值都是ostream对象的引用，故可实现连续输出
    out<<"("<<a.real<<","<<a.imag<<")";
    return out;
}
int main(){
    Complex c1(1,2),c2(3,4),c3;
    c3=c1+c2;
    cout<<c3<<endl;//重载插入运算符之后，可直接输出Complex类的对象，之前是调用类中的Show函数实现输出
    c3=c1-c2;
    cout<<c3<<endl;
    return 0;
}
~~~

### 虚函数

用virtual关键字声明的函数，是实现运行时多态性的基础

虚函数必须是非静态成员函数，经过派生后，通过动态绑定可以实现运行过程中的多态性

除构造函数外的非静态成员函数都可以声明为虚函数

使用虚函数的目的：在调用虚函数时，会根据对象属于哪个类去调用相应类中的虚函数，即使派生类对象隐式转换为基类对象后，仍然会调用派生类中的虚函数(例题是通过基类指针访问派生类成员)

虚函数：

+ 声明形式：virtual 函数类型 函数名称(形参表);
+ 虚函数声明只能出现在类中的函数原型声明中，而不能出现在函数实现处
+ 在派生类中可以对基类的成员函数进行覆盖
+ 虚函数一般不声明为内联函数，函数体实现要放在类外（因为虚函数调用的动态的，而内联函数是编译时处理，是静态的）

virtual关键字：

+ 派生类可以不显示的用virtual声明虚函数，系统会与基类中的虚函数比较来判断是否为虚基类（函数名、参数、返回值三个方面）
+ 派生类的虚函数会隐藏基类中同名函数的所有重载形式，访问基类同名函数重载形式时需要用类名加以限定
+ 一般在派生类中仍用virtual关键字声明，程序可读性更好

### 虚析构函数

继承时存在的问题：

+ 动态申请内存创建派生类对象，并将返回的地址赋值给基类指针，删除对象时会调用基类的析构函数，而我们要实现的是根据对象去调用相应类中的析构函数

将基类和派生类析构函数声明为虚函数的目的：

+ 在调用析构函数时，会根据对象属于哪个类去调用相应类中的析构函数
+ 即使派生类对象指针转换为基类对象指针后，析构对象时仍会调用派生类的析构函数

### 虚表与动态绑定

虚表：

+ 每个多态类都有一个虚表（有虚函数的类就是多态类）
+ 虚表中有当前类的各个虚函数的入口地址
+ 每个对象有一个指向当前类的虚表的指针（虚指针）
+ 虚表在编译阶段建立

动态绑定的实现步骤：

+ 创建对象时，在构造函数中为对象的虚指针赋值
+ 通过对象调用虚函数时，通过对象的虚指针找到类的虚表
+ 在类的虚表中找到要调用的虚函数的入口地址，通过该地址调用虚函数

### 抽象类

纯虚函数：

+ 在基类中声明的虚函数，并且在基类中没有定义具体的操作内容
+ 要求在派生类中根据实际需要定义具体的操作内容
+ 声明形式：virtual 函数类型 函数名(形参表)=0；

抽象类：

+ 带有纯虚函数的类称为抽象类
+ 语法形式：class 类名{纯虚函数，其他成员}
+ 作用：
  + 将有关数据和行为组织在一个继承层次结构中，来保证派生类都具有某种行为
  + 对于暂时无法实现的函数可声明为纯虚函数，留给派生类实现
+ 抽象类只能作为基类使用，且不能定义抽象类的对象（因为类的纯虚函数成员还没实现）
+ 抽象类的派生类如果没有定义纯虚函数的具体操作内容，仍为抽象类，只能作为基类使用

### override与final

override：

+ C++11引入的显示函数覆盖，用来在编译期间捕获未覆盖的错误（编译器会检查是否符合覆盖条件）
+ 多态行为的基础：基类声明虚函数，在派生类中声明一个函数覆盖该虚函数
+ 覆盖条件：函数签名完全一致
+ 函数签名：函数名、形参表、const
+ 用在虚函数显示重载中，编译器会检查基类中是否存在虚函数与派生类中用override声明的虚函数签名一致，若不存在则会报错

final：

+ 用final声明的类不允许被继承
+ 用final声明的成员函数不能被派生类中的函数覆盖（派生类中不能声明与该函数签名一致的类）

~~~c++
//虚函数
#include <iostream>
using namespace std;
class Vehicle {
public:
	Vehicle(int MaxSpeed, int Weight) :MaxSpeed(MaxSpeed), Weight(Weight) {
		cout << "创建了一个Vehical对象" << endl;
	}
	~Vehicle() {
		cout << "析构了一个Vehical对象" << endl;
	}
	virtual void Run() {
		cout << "车子运行" << endl;
	}
	virtual void Stop() {
		cout << "车子停止" << endl;
	}
private:
	int MaxSpeed;
	int Weight;
};
class Bicycle : virtual public Vehicle {
public:
	Bicycle(int MaxSpeed, int Weight, int Height) :Vehicle(MaxSpeed, Weight), Height(Height) {
		cout << "构造了一个Bicycle对象" << endl;
	}
	~Bicycle() {
		cout << "析构了一个Bicycle对象" << endl;
	}
    virtual void Run() {
		cout << "自行车运行" << endl;
	}
	virtual void Stop() {
		cout << "自行车停止" << endl;
	}
private:
	int Height;
};
class Motorcar :virtual public Vehicle {
public:
	Motorcar(int MaxSpeed, int Weight, int SeatNum) :Vehicle(MaxSpeed, Weight), SeatNum(SeatNum) {
		cout << "构造了一个Motorcar对象" << endl;
	}
	~Motorcar() {
		cout << "析构了一个Motorcar对象" << endl;
	}
    virtual void Run() {
		cout << "汽车运行" << endl;
	}
	virtual void Stop() {
		cout << "汽车停止" << endl;
	}
private:
	int SeatNum;
};
class Motorcycle :public Bicycle,public Motorcar{
public:
	Motorcycle(int MaxSpeed, int Weight,int Height,int SeatNum) :Vehicle(MaxSpeed, Weight),Bicycle(MaxSpeed, Weight,Height),Motorcar(MaxSpeed, Weight,SeatNum) {
		cout << "构造了一个Motorcycle对象" << endl;
	}
	~Motorcycle() {
		cout << "析构了一个Motorcycle对象" << endl;
	}
    virtual void Run() {
		cout << "摩托车运行" << endl;
	}
	virtual void Stop() {
		cout << "摩托车停止" << endl;
	}
};
void func(Vehicle *myvehicle){
    myvehicle->Run();
    myvehicle->Stop();
}
int main() {
    Vehicle myvehicle(120,200);
    Bicycle mybicycle(120,200,160);
    Motorcar mymotorcar(120,200,25);
	Motorcycle mymotorcycle(120,200,160,25);
	func(&myvehicle);
    func(&mybicycle);
    func(&mymotorcar);
    func(&mymotorcycle)；//通过基类指针去访问派生类虚函数成员，会根据对象所属的类去调用相应类中的虚函数
	return 0;
}
~~~

## 第九章 群体类和群体数据的组织

### 函数模板

+ 语法形式：template <模板参数表>

  ​                   函数定义

+ 模板参数表内容：

  + 类型参数：class（或typename） 标识符
  + 常量参数：类型说明符 标识符
  + 模板参数：template <参数表> class 标识符 

+ 注意事项：

  + 函数模板并非能自动的处理所有类型数据
  + 只有能够进行模板中运算的类型才能作为类型实参
  + 自定义的类需要重载模板中的运算符才能作为类型实参

~~~c++
//函数模板
#include <iostream>
using namespace std;
template <class T>
void OutPutArray(const T *array,int count){
    for(int i=0;i<count;i++)
        cout<<array[i]<<"  ";
    cout<<endl;
}
int main(){
    int a[2]={1,2};
    double b[2]={3.0,4.0};
    char c[3]={'g','y','\0'};
    OutPutArray(&a,2);
    OutPutArray(&b,2);
    OutPutArray(&c,3);
    return 0;
}
~~~

### 类模板

类模板的作用：

+ 为类声明一种模式，使类的数据成员、函数成员的参数、函数成员的返回值可以取任意类型

类模板的声明：

+ 语法形式：template<模板参数表>

  ​                   class 类名{类成员声明}；

+ 在类模板外定义成员函数语法形式：template<模板参数表>

  ​                                                              类型名 类名<模板参数标识符列表>::函数名(形参表)

### 线性群体的概念

群体的概念：

+ 由多个数据元素组成的集合体
+ 可分为线性群体和非线性群体

线性群体：

+ 元素按位置排列有序，可区分为第一元素、第二元素等
+ 元素的逻辑次序与物理次序是对应的
+ 按照访问元素的方式分为：直接访问、顺序访问、索引访问

非线性群体：

+ 不用位置顺序来标识元素

### 数组类

数组类是一种直接访问的线性群体

分为：

+ 静态数组
  + 具有固定元素个数的线性群体，可通过下标直接访问元素
  + 在编译时就会确定数组长度，无法在运行时修改
+ 动态数组
  + 由任意数量位置连续且类型相同的元素组成
  + 元素个数可在程序运行时改变

~~~c++
//动态数组类模板
#include <iostream>
#include <cassert>
using namespace std;
template <class T>
    class Array{
        public:
        Array(int size=50);
        Array(const Array<T> &a);//所有的Array类型都需要<模板参数标识符列表>来修饰
        ~Array();
        Array<T> & operator =(const Array<T> &a);//重载赋值运算符
        T & operator [](int i);
        const T & operator [](int i) const;//重载下标运算符,通过对象下标直接访问数组元素
        operator T*();
        operator const T*() const;//重载指针转换运算符
        int GetSize() const;
        void Resize(int arraysize);
        private:
        T* list;//动态数组首地址
        int size;//数组长度
    };
template <class T>
    Array<T>::Array(int size){
        assert(size>=0);
        this->size=size;
        list=new T[size];
    }
template <class T>
    Array<T>::Array(const Array<T> &a){
        size=a.size;
        list=new T[size];
        for(int i=0;i<size;i++)
            list[i]=a.liat[i];
    }
template <class T>
    Array<T>::~Array(){
        delete[] list;
    }
template <class T>
    Array<T> & Array<T>::operator =(const Array<T> &a){
        if(&a!=this){
            if(size!=a.size){
                delete[] list;
                size=a.size;
                list=new T[size];
            }//若两个数组长度不相等，则重新动态创建新数组，这样数组长度就相等了
            for(int i=0;i<size;i++)
                list[i]=a.list[i];
        }
        return *this;//返回当前对象的引用
    }
template <class T>
    T & Array<T>::operator [](int i){
        assert(i>=0&&i<size);
        return list[i];//返回数组元素的引用，数组元素都是T类型
    }
template <class T>
    const T & Array<T>::operator[](int i) const{
        assert(i>=0&&i<size);
        return list[i];//返回数组元素的常引用，数组元素都是T类型
    }
template <class T>
    Array<T>::operator T*(){//转换函数不能有参数，由函数名指定返回类型，不能声明返回类型
        return list;//将Array类对象名转换为T类型指针，返回动态数组的首地址
    }
template <class T>
    Array<T>::operator const T*() const{
        return list;//将Array类对象名转换为T类型常指针，返回动态数组的首地址
    }
template <class T>
    int Array<T>::GetSize() const{
        return size;
    }
template <class T>//修改数组长度
    void Array<T>::Resize(int arraysize){
        assert(arraysize>0);//检查新数组长度是否非负
        if(arraysize==size)
            return;//若新数组长度与之前数组长度一样，什么都不做
        T* newlist=new T[arraysize];//动态创建新数组
        int n=(arraysize<size)?arraysize:size;//将arraysize和size中较小值赋给n
        for(int i=0;i<n;i++)
            newlist[i]=list[i];//将之前数组中的元素一一赋值给新数组中的元素
        delete[] list;//删除原数组
        list=newlist;//使指针list指向新数组
        size=arraysize;//更新数组长度
    }
int main(){//求2到n中的所有质数,将所有质数放入数组中并输出数组元素
    Array<int> a(10);
    int n,count=0;
    cout<<"输入上限值n:"<<endl;
    cin>>n;
    for(int i=2,i<=n;i++){//如果一个数不能整除比它小的任何素数，那么这个数就是素数
        bool isPrime=true;
        for(int j=0;j<count;j++)//比i小的质数有count个，a[0]~a[count-1]，当count为0时并不执行此循环
            if(i%a[j]==0){
                isPrime=false;
                break;//如果i可以整除比其小的质数，则i不是质数
            }
        if(isPrime){//将质数放入数组当中
            if(count==a.GetSize())
                a.Resize(count*2);//如果数组长度不够，将数组长度修改为2倍
            a[count++]=i;//后置自增返回的是自增之前的数
        }
    }
    for(int i=0;i<count;i++)//将数组元素输出
        cout<<setw(8)<<a[i];
    cout<<endl;
    return 0;
}
~~~

### 链表的概念与结点类模板

链表类是一种顺序访问的线性群体

链表：

+ 是一种动态数据结构，用来表示顺序访问的线性群体
+ 由一系列结点组成，结点可在运行时动态生成
+ 每个结点包括数据域和指向链表中下一个结点的指针
+ 如果每个结点指针域只有指向后继结点的指针，称为单链表

~~~c++
//结点类模板
#include <iostream>
using namespace std;
template <class T>
    class Node{
        public:
        T data;//数据域
        Node(const T &data,Node<T> *next=0);//构造函数,形参为T类型数据的常引用和结点类型的指针
        void InsertAfter(Node<T> *p);//在本结点后插入节点，形参为结点类型指针，即待插入结点的地址
        Node<T> *DeleteAfter();//删除本结点的后继节点，并返回其地址,返回值为结点类型的指针
        Node<T> *NextNode();//获取后继结点的地址
        const Node<T> *NextNode() const();//重载NextNode函数，返回值节点类型指向常量的指针,通过该指针无法修改后继结点的数据
        private:
        Node<T> *next;//指向后继结点的指针，即后继结点的地址
    };
template <class T>
    Node<T>::Node(const T &data,Node<T> *next)::data(data),next(next){
        
    }
template <class T>
    void Node<T>::InsertAfter(Node<T> *p){
        p->next=next;//使带插入节点指向当前结点的后继结点
        next=p;//使当前结点指向待插入结点
    }
template <class T>
    Node<T> *Node<T>::DeleteAfter(){
        Node<T> *ptr=next;//保存当前结点的后继结点地址，即待删除结点的地址
        if(next==0)
            return 0;//若当前结点无后继结点，则返回空指针
        next=ptr->next;//使当前结点指向待删除结点的后继结点
        return ptr;
    }
template <class T>
    Node<T> *Node<T>::NextNode(){
        return next;
    }
template <class T>
    const Node<T> *Node<T>::NextNode const(){
        return next;
    }
~~~

### 链表类模板

链表的基本操作：

+ 生成链表
+ 插入结点
+ 查找结点
+ 删除结点
+ 遍历链表
+ 清空链表

### 栈类模板

栈是只能从一端访问的线性群体，是一种后进先出的数据结构

栈的基本状态：栈空、栈满、一般状态

栈的基本操作：

+ 初始化
+ 入栈
+ 出栈
+ 清空栈
+ 访问栈顶元素
+ 检测栈的状态（满、空）

~~~c++
//栈类模板Stack.h，此处采用顺序存储方式
#include <iostream>
#include <cassert>
template <class T,int SIZE=50>
    class Stack{
        public:
        Stack();//构造函数
        void push(const T &a);//压栈函数
        T pop();//弹出栈函数
        void clear();//清空栈函数
        const T &peek() const;//读取栈顶元素，但不修改栈的状态
        bool isEmpty() const;//判断栈是否为空
        bool isFull() const;//判断栈是否为满
        private:
        T list[SIZE];
        int top;
    };
template <class T,int SIZE>
    Stack<T,SIZE>::Stack():top(-1){
        
    }
template <class T,int SIZE>
    void Stack<T,SIZE>::push(const T &a){
        assert(!isFull());
        list[++top]=a;
    }
template <class T,int SIZE>
    T Stack<T,SIZE>::pop(){
        assert(!isEmpty());
        return list[top--];
    }
template <class T,int SIZE>
    void Stack<T,SIZE>::clear(){
        top=-1;
    }
template <class T,int SIZE>
    const T & Stack<T,SIZE>::peek() const{
        assert(!isEmpty());
        return list[top];
    }
template <class T,int SIZE>
    bool Stack<T,SIZE>::isEmpty() const{
        return top==-1;//如果top等于-1，返回true，否则返回false
    }
template <class T,int SIZE>
    bool Stack<T,SIZE>::isFull() const{
        return top==SIZE-1;
    }
~~~

### 队列类模板

队列是只能从一端添加元素，从另一端删除元素的线性群体，是一种先进先出的结构

循环队列：用来解决在顺序存储时，出队一个元素，剩余元素都要移动（会产生开销）的问题

~~~c++
//队列类模板，此处采用顺序存储方式
#include <cassert>
template <class T,int SIZE=50>
    class Queue{
        public:
        Queue();//构造函数
        void insret(const T &newitem);//新元素入队
        T remove();//元素出队
        void clear();//清空队列
        const T &getFront() const;//访问队首元素
        int getLength() const;//求队列长度
        bool isEmpty() const;//判断队列是否为空
        bool isFull() const;//判断队列是否为满
        private:
        int front,rear,count;
        T list[SIZE];
    }；
template <class T,int SIZE>
    Queue<T,SIZE>::Queue():front(0),rear(0),count(0){
        
    }
template <class T,int SIZE>
    void Queue<T,SIZE>::insert(const T &newitem){
        assert(count!=SIZE);
        count++;
        list[rear]=newitem;
        rear=(rear+1)%SIZE;//用取余运算实现循环队列
    }
template <class T,int SIZE>
    T Queue<T,SIZE>::remove(){
        assert(count!=0);
        int temp=front;
        count--;
        front=(front+1)%SIZE;//队首指针的队尾指针都是按顺时针方向走的，即入队和出队相应指针都加1
        return list[temp];//return代表函数执行结束，故只能将return语句放在函数体的最后
    }
template <class T,int SIZE>
    void Queue<T,SIZE>::clear(){
        front=0;
        rear=0;
        count=0;
    }
template <class T,int SIZE>
    const T & Queue<T,SIZE>::getFront() const{
        return list[front];
    }
template <class T,int SIZE>
    int Queue<T,SIZE>::getLength() const{
        return count;
    }
template <class T,int SIZE>
    bool Queue<T,SIZE>::isEmpty() const{
        return count==0;
    }
template <class T,int SIZE>
    bool Queue<T,SIZE>::isFull() const{
        return count==SIZE;
    }
~~~

### 排序概述

排序：将数据元素的任意序列，重新排列成按关键字有序的序列

数据元素：数据的基本单位，可由若干数据项组成，通常作为一个整体考虑

关键字：数据元素中某个数据项的值，可用来标识数据元素

排序过程的基本操作：

+ 比较两个数的大小
+ 调整元素在序列中的位置

排序分为：

+ 内部排序：在计算机内存中进行排序
+ 外部排序：数据元素数量大，不能在内存中全部容纳，排序过程中需要对外存进行访问

几种简单的内部排序：

+ 插入排序
+ 选择排序
+ 交换排序

### 插入排序

基本思想：将待排序元素按关键字大小插入到已排序序列的适当位置上

~~~c++
//插入排序函数模板
template <class T>
    void insertionSort(T a[],int n){
    int i,j;
    T temp;
    for(int i=1;i<n;i++){
        int j=i;
        T temp=a[i];//移动元素位置之后a[i]值会变，需要将当前待插入的值保存起来
        while(j>0&&temp<a[j-1]){
            a[j]=a[j-1];//将元素位置后移
            j--;
        }
        a[j]=temp;//将待排序元素插入到空缺出来的位置，空缺位置的下标一定是j
    }
}
~~~

### 选择排序

基本思想：每次从待排序序列中选择关键字最小的元素，并放在已排序序列的末尾

~~~c++
//简单选择排序函数模板
template <class T>
    void mySwap(T &x,T &y){//交换函数
    T temp=x;
    x=y;
    y=temp;
}
template <class T>
    void selectionSort(T a[],int n){
    for(int i=0;i<n-1;i++){//从第一个元素开始与其后面的元素比较，找到最小元素
        int leastIndex=i;//空缺位置的下标i随着已排序元素的增多而增大
        for(int j=i+1;j<n;j++)
            if(a[j]<a[leastIndex])
                leastIndex=j;
        mySwap(a[i],a[leastIndex]);
    }
}
~~~

### 交换排序

基本思想：两两比较待排序序列中的元素，并交换不满足顺序要求的各对元素

~~~c++
//冒泡排序函数模板
template <class T>
    void mySwap(T &x,T &y){
    T temp=x;
    x=y;
    y=temp;
}
template <class>
    void bubbleSort(T a[],int n){
    int i=n-1;
    while(i>0){
        int lastExchangeIndex=0;
        for(int j=0;j<i;j++)
            if(a[j+1]<a[j]){
                mySwap(a[j],a[j+1]);
                lastExchangeIndex=j;
            }
        i=lastExchangeIndex;
    }
}
~~~

### 查找

顺序查找：

+ 从序列的首元素开始，逐个与待查找的关键字进行比较，直到找到相等的
+ 若整个序列没有与待查找关键字相等的元素，就是查找不成功

折半查找：

+ 对于已按关键字排序的序列，经过一次比较，可将序列分为两部分，只在可能存在待查找元素的那部分继续查找，重复此步骤直到结束

~~~c++
//折半查找函数模板
template <class T>
    int binSearch(const T list[],int n,const T &key){
    int low=0;
    int high=n-1;
    while(low<=high){
        int mid=(low+high)/2;
        if(key==list[mid])
            return mid;
        else if(key<list[mid])
            high=mid-1;
        else
            low=mid+1;
    }
    return -1;//如果退出while循环而无返回值，说明没找到，返回-1
}
天目路2号西区政务中心416室 刘老师
~~~

## 第十章 泛型程序设计与C++标准模板库

算法通过迭代器去访问容器中的数据，通过适配器对容器加以限制来形成特殊的数据结构

### 泛型程序设计基本概念

泛型程序设计：

+ 编写不依赖于具体数据类型的程序
+ 将算法从特定的数据结构中抽象出来
+ C++模板是泛型程序设计的关键基础

概念：

+ 用来界定具有一定功能的数据类型（将具有一定功能的不同类型数据统称为某个概念）
+ 对于两个不同的概念A和B，若概念A所需求的所有功能是概念B所需求的部分功能，称B是A的子概念

模型：

+ 符合某个概念的数据类型称为该概念的模型

用概念做模板参数名：

+ 为概念赋予名称，并用该名称作为模板参数名
+ 很多STL实现代码都是用概念来命名模板参数

### STL简介

标准模板库（STL）定义了一套概念体系，为泛型程序设计提供逻辑基础

STL中类模板和函数模板的参数都是用这个体系中的概念来规定的

使用STL模板时，类型参数既可以是标准库中已有类型，也可以是自定义类型（只要该自定义类型是所要求概念的模型）

STL的基本组件：

+ 包括容器、迭代器、函数对象、算法
+ 迭代器是算法和容器的桥梁。将迭代器作为算法的参数，通过迭代器来访问容器中的数据
+ 将函数对象作为函数的参数，而不是将其函数体作为算法的一部分。
+ 使用STL中提供的或自定义的迭代器和函数对象，配合STL的算法，可组合出各种功能

容器：

+ 作用：是容纳、包含一组元素的对象
+ 基本容器类模板
  + 顺序容器：包括数组、向量、双端队列、单链表、列表
  + （有序）关联容器：集合、多重集合、映射、多重映射
  + 无序关联容器：无序集合、无序多重集合、无序映射、无序多重映射

+ 容器适配器：栈、队列、优先队列
+ 使用容器需要包含对应的头文件

迭代器：

+ 作用：用来顺序访问容器中的每个元素
+ 使用自增运算符可获得指向下一个元素的迭代器
+ 使用指针运算符“*”访问迭代器所指向的元素，如果元素类型是类或结构体，可使用"->"运算符直接访问元素的第一个成员
+ 有些迭代器支持使用自减运算符获得指向上一个元素的迭代器
+ 指针就是一种迭代器，迭代器是泛化的指针
+ 使用独立于STL容器的迭代器，需要包含头文件< iterator >

函数对象：

+ 行为类似函数的对象，可以像调用函数一样调用
+ 函数对象是泛化的函数，任何普通函数和重载了"()"运算符的类的对象都可以作为函数对象使用
+ 使用STL的函数对象，需要包含头文件< functional >

算法：

+ 可用于不同的对象和内置的数据类型
+ STL包含70多个算法
+ 使用STL的算法，需要包含头文件< algorithm >

### 迭代器

迭代器是算法和容器的桥梁

+ 迭代器用作访问容器中的元素
+ 算法不能直接操作容器中的数据，而是通过迭代器间接操作

算法和容器独立

+ 增加新的算法，无需影响容器的实现
+ 增加新的容器 ，原有的算法也能适用

输入流迭代器和输出流迭代器

+ 输入流迭代器istream_iterator<T>
  + 以输入流为参数构造
  + 可用*(p++)获得下一个输入元素
+ 输出流迭代器ostream_iterator<T>
  + 构造时需要提供输出流
  + 可用(*p++)=x将x输出到输出流
+ 二者都属于适配器
  + 适配器是用来为已有对象提供新的接口对象
  + 输入流适配器和输出流适配器为流对象提供迭代器的接口

迭代器支持的操作：

+ 迭代器是泛化的指针，提供了类似指针的操作（如++，*，->运算符）
+ 输入迭代器：用来从序列中读取数据，如输入流迭代器
+ 输出迭代器：用来向序列中写入数据，如输出流迭代器
+ 前向迭代器：既是输入迭代器又是输出迭代器，且可对序列进行单向遍历
+ 双向迭代器：既是输入迭代器又是输出迭代器，且可对序列进行双向遍历
+ 随机访问迭代器：是双向迭代器，且可在序列中的任意两个位置跳转

迭代器的区间：

+ 两个迭代器表示一个区间：[p1,p2)
+ STL算法常以迭代器的区间作为输入，传递输入数据
+ 合法的区间：p1经过n次自增后满足p1=p2
+ 区间包含p1，但不包含p2

迭代器的辅助函数：

+ advance(p,n)：对p执行n次自增操作
+ distance(first,last)：计算两个迭代器之间的距离，即first需要自增多少次能与last相等

~~~c++
//综合运用几种迭代器
#include <algorithm>
#include <iterator>
#include <vector>
#include <iostream>
using namespace std;
template <class T, class InputIterator, class OutputIterator>
    void mySort(InputIterator first, InputIterator last,OutputIterator result){
    vector<T> s;//定义顺序容器vector类的对象s
    for(;first!=last;++first)
        s.push_back(*first);
    sort(s.begin(),s.end());
    copy(s.begin(),s.end(),result);
}
int main(){
    double a[5]={1.2,2.2,0.8,3.3,3.2};
    mySort<double>(a,a+5,ostream_iterator<double>(cout," "));
    cout<<endl;
    mySort<int>(istream_iterator<int>(cin),istream_iterator<int>(),ostream_iterator<int>(cout," "));
    cout<<endl;
    return 0;
}
~~~

### 容器的基本功能与分类

定义：容器类是容纳、包含一组元素或元素集合的对象

分类：

+ 根据容器中元素的组织方式：顺序容器，关联容器(有序和无序)
+ 根据与容器关联的迭代器类型：可逆容器，随机访问容器(可逆容器的子概念)

容器的通用功能：

+ 用默认构造函数构造空容器
+ 支持关系运算符：==、!=、<、<=、>、>=
+ begin()、end()：获得容器首尾迭代器，尾迭代器指向的是末尾元素的下一个位置
+ clear()：将容器清空
+ empty()：判断容器是否为空
+ size()：得到容器元素个数
+ s1.swap(s2)：将s1和s2两容器内容交换

+ 相关数据类型(S表示容器类型)：
  + S::iterator：指向容器元素的迭代器类型
  + S::const_iterator：常迭代器类型

对可逆容器的访问：

+ STL为每个可逆容器都提供了逆向迭代器
+ 逆向迭代器可通过以下成员函数得到：
  + rbegin()：指向容器尾的逆向迭代器
  + rend()：指向容器首的逆向迭代器
+ 逆向迭代器类型名的表示方式：
  + S::reverse_iterator：逆向迭代器类型
  + S::const_reverse_iterator：逆向常迭代器类型

随机访问容器：

+ 支持对容器元素进行随机访问
+ s[n]：获得容器s的第n个元素

### 顺序容器的基本功能

顺序容器：

+ STL中的顺序容器：向量、双端队列、列表、单项链表、数组（前四个可看作是长度可扩展的数组）
+ 元素线性排列，可以随时在指定位置插入元素和删除元素
+ 必须符合Assignablea概念（即具有公有的复制构造函数并可用“=”赋值）
+ 数组对象的大小固定，单向列表有特殊的添加和删除操作

顺序容器的接口(不适用于数组和单向列表)：

+ 构造函数
+ 赋值函数assign
+ 插入函数insert、push_back、push_front(只对list和deque)、emplace、emplace_front
+ 删除函数erase、clear、pop_front(只对list和deque)、pop_back、emplace_back
+ 首尾元素的直接访问front、back
+ 改变大小resize
+ 通过调用容器的接口实现对容器及内部数据元素的操作

~~~c++
//顺序容器基本操作
#include <iostream>
#include <list>
#include <deque>
template <class T>
    void printContainer(const char *msg,const T& s){//指向常量的指针，不能通过指针改变所指向对象的值
    cout<<msg<<":";//输出指针变量，表示输出指针所指向的数组元素
    copy(s.begin(),s.end(),ostream_iterator<int>(cout," "));
    cout<<endl;
}
int main(){
    deque<int> s;//定义双端队列类的对象s
    for(int i=0;i<5;i++){
        int x;
        cin>>x;
        s.push_front(x);
    }//初始化容器s
    printContainer("deque at first",s);
    //用s容器内容的逆序构造列表容器
    list<int> l(s.rbegin(),s.rend());
    printContainer("list at first",l);
    //将列表中相邻的元素互换位置
    list<int>::iterator iter=l.begin();
    while(iter!=l.end()){
        int v=*iter;
        iter=l.erase(iter);
        l.insert(++iter,v);
    }
    printContainer("list at last",l);
    //用列表容器l的值给s赋值
    s.assign(l.begin(),l.end());
    printContainer("deque at last",s);
    return 0;
}
~~~

### 顺序容器的特性

向量(vector)：

+ 特点：
  + 是一个可以扩展的动态数组
  + 随机访问、在尾部插入和删除元素快
  + 在中间、头部插入和删除元素慢
+ 向量的容量：
  + 容量：实际分配空间的大小
  + s.capacity()：返回向量容器s的当前容量
  + s.reserve(n)：若向量容器s的容量小于n，则对容器进行扩展，使其容量至少为n

双端队列(deque)：

+ 特点：
  + 在两端插入和删除元素快
  + 在中间插入和删除元素慢
  + 随机访问较快，但比向量容器慢

~~~c++
//先按照从大到小顺序输出奇数，再按照从小到大输出偶数
//先对序列进行从小到大排序，再将奇数从双端队列前端插入，将偶数从双端队列后端插入
#include <iostream>
#include <vector>
#include <deque>
using namespace std;
int main(){
    istream_iterator<int> i1(cin),i2;//分别用标准输入流和默认构造构建两个输入流迭代器
    vector<int> s1(i1,i2);//通过输入流迭代器从标准输入流中输入数据
    sort(s1.begin(),s1.end());//将输入的整数排序
    deque<int> s2;
    for(vector<int>::iterator iter=s1.begin();iter!=s1.end();++iter){
        if(*iter%2==0)
            s2.push_back(*iter);
        else
            s2.push_front(*iter);
    }
    copy(s2.begin(),s2.end(),ostream_iterator<int>(cout," "));
    cout<<endl;
    return 0;
}
~~~

双向链表(list)：

+ 特点：
  + 在任意位置插入和删除元素都很快
  + 不支持随机访问
+ 接合操作：
  + s1.splice(p,s2.q1,q2)：将s2中[q1,q2)移动到s1中p所指向的元素之前

~~~c++
//列表容器使用
#include <iostream>
#include <list>
using namespace std;
int main(){
    string names1[]={"Alice","Helen","Lucy","Susan"};
    string names2[]={"Bob","David","Levin","Mike"};//创建两个字符串数组
    list<string> s1(names1,names1+4);
    list<string> s2(names2,names2+4);//将数组地址作为参数构建列表对象
    s2.splice(s2.end(),s1,s1.begin());//将s1的第一个元素放到s2的最后
    list<string>::iterator iter1=s1.begin();
    advance(iter1,2);//iter1指向s1的第三个元素
    list<string>::iterator iter2=s2.begin();
    ++iter2;//iter2指向s2的第二个元素
    list<string>::iterator iter3=iter2;
    advance(iter3,2);//iter3指向s2的第四个元素
    s1.splice(iter1,s2,iter2,iter3);//将s2的第二、三个元素放在s1的第三个元素前面
    copy(s1.begin(),s1.end(),ostream_iterator<string>(cout," "));
    cout<<endl;
    copy(s2.begin(),s2.end(),ostream_iterator<string>(cout," "));
    cout<<endl;
    return 0;
}
~~~

单向链表(forward_list)：

+ 单向链表每个结点只有指向下一个结点的指针，没有简单的方法获得结点的前驱结点
+ 未定义insert、emplace、erase操作，而定义了insert_after、emplace_after、erase_after，意思是对迭代器所指向元素的后一个元素进行操作
+ 不支持size操作

数组(array)：

+  是对内置数组的封装，提供了更安全、更方便的使用数组的方式
+ 对象大小固定，定义数组容器的对象时，需要指定元素类型和容器大小
+ 不能动态改变数组容器的大小

顺序容器的比较：

+ 编写程序时，应根据容器需要执行的操作来选择容器类型
+ 若需要执行大量随机访问，且只在容器尾部添加新元素以扩展容器时，选择向量vector
+ 若需要执行少量随机访问，且需要在容器两端插入和删除元素时，选择双端队列deque
+ 若不需要随机访问，且需要在中间位置插入和删除元素，选择list或forward_list
+ 如果需要数组，array相较于内置数组类型，要更安全更易用

### 顺序容器的插入迭代器与适配器

顺序容器的的插入迭代器：

+ 用于向容器头部、尾部或中间指定位置插入元素的迭代器
+ 包括前插迭代器(front_inserter)、后插迭代器(back_inserter)、任意位置插入迭代器(inserter)

顺序容器的适配器：

+ 对顺序容器进行封装，以顺序容器为基础构建常用的数据结构
  + 栈(stack)：先入后出
  + 队列(queue)：先入先出
  + 优先级队列(priority_queue)：最大元素先出

栈和队列模板：

+ 栈模板：template<class T,class Sequence=deque< T>>

  ​                class stack;

+ 队列模板：template<class T,class FrontInsertionSequence=deque< T>>

  ​                   class queue;

+ 栈可以用任何一种顺序容器作基础容器，而队列只能使用前插顺序容器(双端队列或列表)作为基础容器

栈和队列共同支持的操作：

+ s1 op s2，op可以是==、!=、<、<=、>、>=，会对两个适配器的元素按字典序进行比较
+ s.size()：得到适配器s中的元素个数
+ s.empty()：判断适配器s是否为空
+ s.push(t)：将元素t压入到适配器s中
+ s.pop()：将一个元素从s中弹出，对于栈，弹出的是最后压入的元素；对于队列，弹出的是最先压入的元素
+ 不支持迭代器，不允许对任意元素进行访问

栈和队列：

+ 栈的操作
  + s.top()：返回栈顶元素的引用
+ 队列操作
  + s.front()：获得队头元素的引用
  + s.back()：获得队尾元素的引用

~~~c++
//利用栈反向输出单词,栈是先入后出
#include <iostream>
#include <stack>
using namespace std;
int main(){
    stack<char> s;
    string str;
    cin>>str;
    for(string::iterator iter=str.begin();iter!=str.end();++iter)
        s.push(*iter);//栈是没有push_back和push_front接口的，因为肯定是从尾部压入元素
    while(!s.empty()){
      cout<<s.top();
      s.pop();
    } 
    cout<<endl;
    return 0;
}
~~~

优先级队列：

+ 优先级队列也像栈和队列一样支持元素的压入和弹出，但弹出元素顺序与元素大小有关
+ 优先级队列的基础容器必须是支持随机访问的顺序容器
+ 优先级队列的操作：
  + 支持栈和队列的size、empty、push、pop几个成员函数
  + 优先级队列不支持比较操作
  + s.top()：返回最大元素的引用

~~~c++
//用优先队列模拟细胞分裂
#include <iostream>
#include <priority_queue>
using namespace std;
const int SPLIT_TIME_MIN=500;
const int SPLIT_TIME_MAX=2000;
class Cell;//前向引用声明,在提供完整类声明之前只能使用声明的类符号，不能使用类的对象和类的细节
priority_queue<Cell> cellQueue;//定义优先队列
class Cell{
   private:
    static int count;//细胞总数，类的静态成员，必须在类外定义和初始化
    int id;//细胞编号
    int time;//细胞诞生时间，也是细胞开始分裂时间
   public:
    Cell(int birth):id(count++){//类的构造函数
        time=birth+(rand()%(SPLIT_TIME_MAX-SPLIT_TIME_MIN)+SPLIT_TIME_MIN);
    }//细胞的诞生时间time取决于母细胞的诞生时间(母细胞的诞生时间作为实参传递给子细胞构造函数中的形参birth)
    int getId() const{return id;}//获得细胞编号
    int getSplitTime() const{return time;}//获得细胞开始分裂时间
    bool operator < (const Cell& s) const{//双目运算符重载为成员函数
        return time>s.time;//前操作数大于后操作数，返回true，否则返回false
    }
    void split() const{//函数体中调用了const函数，此函数也须声明为const
        Cell child1(time),child2(time);//母细胞的诞生时间作为实参传递给子细胞构造函数中的形参birth
        cout<<time<<"s:Cell#"<<id<<"split to"<<child1.getId()<<"and#"<<child2.getId()<<endl;
        cellQueue.push(child1);
        cellQueue.push(child2);
    }
};
int Cell::count=0;
int main(){
    srand(static_cast<unsigned>(time(0)));//通过取系统时间为随机数函数rand准备随机数种子
    int t;
    cout<<"Simulation time:";
    cin>>t;
    cellQueue.push(Cell(0));//将第一个细胞压入优先队列
    while(cellQueue.top().getSplitTime()<t){//将最小的细胞诞生时间与t比较，当最小的细胞诞生时间大于t时结束循环
        cellQueue.top().split();//诞生时间最小的细胞分裂
        cellQueue.pop();//弹出诞生时间最小的细胞(也就是最早诞生的细胞)
    }
    return 0;
}
~~~

### 关联容器基本功能与分类

关联容器的特点和接口：

+ 关联容器的特点：
  + 每个关联容器都有一个键(key)
  + 可根据键高效地查找元素
+ 接口：
  + 插入insert
  + 删除erase
  + 查找find
  + 定界lower_bound、upper_bound、equal_range
  + 计数count

四种关联容器：

+ 单重关联容器
  + 键值唯一，一个键值只对应一个元素
+ 多重关联容器
  + 键值不唯一，一个键值可对应多个元素
+ 简单关联容器
  + 容器只有一个类型参数，表示键类型
  + 容器的元素就是键本身
+ 二元关联容器
  + 容器有两个类型参数，分别表示键和附加数据的类型
  + 容器的元素类型是由键类型和元素类型复合而成的二元组

无序关联容器：

+ C++11新标准中定义了4个无序关联容器
  + unorder_set、unorder_map、unorder_multiset、unorder_multimap
+ 不是通过比较运算符来组织元素的，而是通过一个哈希函数和键类型的==运算符
+ 提供了与有序容器相同的操作
+ 可以直接定义关键字是内置类型的无序容器
+ 不能直接定义关键字类型为自定义类型的无序容器，如果需要，必须提供哈希模板

### 集合(set)

用来存储一组无重复的元素

+ 集合的元素本身是有序的，可高效查找指定元素
+ 可方便地得到指定大小范围的元素在容器中所处的区间

~~~c++
//将输入元素放入集合中，获得最大最小元素的中间值，并将集合元素分为两部分输出
#include <set>
#include <iterator>
#include <utility>
#include <iostream>
using namespace std;
int main(){
    set<double> s;
    while(true){
        double v;
        cin>>v;
        if(v==0)
            break;//输入元素为0时，停止循环
        pair<set<double>::iterator,bool> r=s.insert(v);//尝试将输入元素插入，insert接口的返回类型是pair<iterator,bool>
        if(!r.second)//如果输入元素已存在，提示重复
            cout<<v<<"is duplicated"<<endl;
    }
    set<double>::iterator iter1=s.begin();//获得首迭代器
    set<double>::iterator iter2=s.end();//获得尾迭代器
    double medium=(*iter1+*(--iter2))/2;//尾迭代器指向的是末尾元素的下一位置，故需要减一
    cout<<"<=medium:";
    copy(s.begin(),s.upper_bound(medium),ostream_iterator<double>(cout," "));//集合可通过数字得到中间位置的迭代器
    cout<<endl;
    cout<<">=medium:";
    copy(s.lower_bound(medium),s.end(),ostream_iterator<double>(cout," "));
    cout<<endl;
    return 0;
}
~~~

### 映射(map)

映射与集合同属于单重关联容器，区别在于

+ 集合的元素类型是键本身(简单关联容器)
+ 映射的元素类型是由键和附加数据构成的二元组(二重关联容器)
+ 在集合中按照键查找一个元素时，只是确定元素是否存在
+ 在映射中按照键查找一个元素时，不仅能确定存在性，还能得到相应的附加数据

~~~c++
//从五门课程中选择三门课，并输出学分总和
#include <iostream>
#include <map>
#include <string>
#include <utility>
using namespace std;
int main(){
    map<string,int> courses;
    courses.insert(make_pair("CSAPP",3));//插入的元素类型是由键和附加数据构成的二元组
    courses.insert(make_pair("C++",2));
    courses.insert(make_pair("CSARCH",4));
    courses.insert(make_pair("COMLIER",4));
    courses.insert(make_pair("OS",5));
    int n=3;//剩下可选次数
    int sum=0;//学分总和
    while(n>0){
        string name;
        cin>>name;
        map<string,int>::iterator iter=courses.find(name);//通过find查找失败会返回尾迭代器
        if(iter==course.end())//判断是否不存在输入的课程名称
            cout<<name<<" is not available"<<endl;
        else{
            sum+=iter->second;//累加学分，第一次使用迭代器的->运算符
            courses.erase(iter);//将已选课程从映射中删除
            n--;//可选次数减一
        }
    }
    cout<<"Total credit:"<<sum<<endl;//输出总学分
    return 0;
}
~~~

~~~c++
//统计一句话中每个字母出现的次数
#include <iostream>
#include <map>
#include <cctype>
using namespace std;
int main(){
    map<char,int> s;//定义映射来存放字符的出现次数
    char c;//存放输入的字符
    do{
        cin>>c;
        if(isalpha(c)){//判断是否为字母
            c=tolower(c);//将字母转换为小写
            s[c]++;//字母出现次数加一
        }
    }while(c!='.');
    for(map<char,int>::iterator iter=s.begin();iter!=s.end();++iter)
        cout<<iter->first<<" "<<iter->second<<endl;//通过first和second访问映射中的元素
    return 0;
}
~~~

### 多重集合与多重映射(multiset、multimap)

多重集合是允许有重复元素的集合，多重映射是允许一个键对应多个附加数据的映射

多重集合与集合、多重映射与映射用法差不多，主要差异在于键的唯一性

~~~c++
//上课时间查询
#include <iostream>
#include <map>
#include <utility>
#include <string>
using namespace std;
int main(){
    multimap<string,string> courses;
    typedef multimap<string,string>::iterator courseIter;//只是起替换作用
    courses.insert(make_pair("C++","2-6"));
    courses.insert(make_pair("COMPLIER","3-1"));
    courses.insert(make_pair("COMPLIER","5-2"));
    courses.insert(make_pair("OS","1-2"));
    courses.insert(make_pair("OS","4-1"));
    courses.insert(make_pair("OS","5-5"));
    string name;//课程名
    int count;//键的个数，即一门课在容器中的个数
    cin>>name;
    count=courses.count(name);//count接口用于返回容器中存在键的个数
    if(count==0)
        cout<<"Can not find this course!"<<endl;
    else{
        cout<<count<<"lesson(s) per week:";
        pair<courseIter,courseIter> range=courses.equal_range(name);//确定相同课程在容器中的范围，equal_range接口的返回类型是pair<iterator,iteraator>
        for(courseIter iter=range.first;iter!=range.second;++iter)
             cout<<iter->second<<" ";
        cout<<endl;
    }
    return 0;
}
~~~

### 函数对象

函数对象：

+ 一个行为类似于函数的对象
+ 可以没有参数，也可带若干参数
+ 作用是获取一个值或改变操作的状态
+ 普通函数是函数对象，重载了调用运算符"()"的类的实例是函数对象

~~~c++
//普通函数作为函数对象
#include <iostream>
#include <numeric>//数值算法头文件
using namespace std;
int mult(int x,int y){
    return x*y;
}
int main(){
    int a[]={1,2,3,4,5};
    const int N=sizeof(a)/sizeof(int);//数组占的总字节数除以整型变量字节数
    cout<<"The result of multipling is:"<<accumulate(a,a+N,1,mult)<<endl;//accumulate是算法，a是迭代器，1是累乘初始值，mult是函数对象
    return 0；
}
~~~

~~~c++
//重载函数调用运算符的类的实例作为函数对象
#include <iostream>
#include <numeric>//数值算法头文件
using namespace std;
class MultClass{
    public:
    int operator ()(int x,int y) const{
        return x*y;
    }
};
int main(){
    int a[]={1,2,3,4,5};
    const int N=sizeof(a)/sizeof(int);
    cout<<"The result of multipling is:"<<accumulate(a,a+N,1,MultClass())<<endl;
    return 0;
}
~~~

STL提供的函数对象：

+ 产生器
+ 用于算数运算的函数对象：
  + 一元函数对象
  + 二元函数对象
+ 用于关系运算、逻辑运算的函数对象(返回值为bool类型)：
  + 一元谓词
  + 二元谓词

~~~c++
//用STL标准函数对象multiplise作为函数对象
#include <iostream>
#include <numeric>//数值算法头文件
using namespace std;
int mult(int x,int y){
    return x*y;
}
int main(){
    int a[]={1,2,3,4,5};
    const int N=sizeof(a)/sizeof(int);//数组占的总字节数除以整型变量字节数
    cout<<"The result of multipling is:"<<accumulate(a,a+N,1,multiplies<int>())<<endl;//multiplies是算法，a是迭代器，1是累乘初始值，mult是函数对象
    return 0；
}
~~~

~~~c++
//利用STL中的二元谓词函数对象实现数组从大到小排序
#include <functional>
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main(){
    int Arr[]={1,2,3,4,5,6,7,8,9};
    const int N=sizeof(Arr)/sizeof(int);
    vector<int> s(Arr,Arr+N);//将数组元素放入向量容器中
    sort(s.begin(),s.end(),greater<int>());//sort是算法，greater是函数对象
    cout<<"The sequence after sorting:";
    copy(s.begin(),s.end(),ostream_iterator<int>(cout," "));
    cout<<endl;
    return 0;
}
~~~

### 函数适配器

+ 绑定适配器bind1st、bind2nd
  + 将n元函数对象的指定参数绑定为一个常数，得到n-1元函数对象
+ 组合适配器not1、not2
  + 将指定谓词的结果取反
+ 函数指针适配器ptr_fun
  + 将一般函数指针转换为函数对象，使之能作为其他函数适配器的输入
+ 成员函数适配器ptr_fun、ptr_fun_ref
  + 对成员函数指针使用，把n元成员函数适配为n+1元函数对象,函数对象的第一个参数为调用该成员函数的对象

~~~c++
//找到数组中第一个大于40的元素
#include <functional>
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
int main(){
    int Arr[]={10,20,30,40,50,60,70};
    const int N=sizeof(Arr)/sizeof(int);
    vector<int> s(Arr,Arr+N);
    vector<int>::iterator iter=find_if(s.begin(),s.end(),bind2nd(greater<int>(),40));//find_if算法只能用一元函数对象作为函数对象，而greater是二元函数对象，通过bind2nd函数适配器将greater函数对象与40绑定起来，从而变成一元函数对象，可作为参数传递给find_if算法
    if(iter==s.end())
        cout<<"No element greater than 40!"<<endl;
    else
        cout<<"The first element greater than 40 is:"<<*iter<<endl;
    return 0;
}
~~~

+ 组合适配器
  + not1和not2分别用于对一元谓词和二元谓词取反

~~~c++
//组合适配器使用
#include <functional>
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
bool g(int x,int y){
    return x>y;
}
int main(){
    int Arr[]={10,20,30,40,50,60,70};
    const int N=sizeof(Arr)/sizeof(int);
    vector<int> s(Arr,Arr+N);
    vector<int>::iterator iter;//只能定义一次，多次定义会报错
    iter=find_if(s.begin(),s.end(),bind2nd(ptr_fun(g),40));//通过ptr_fun适配器将函数名转化为函数对象
    if(iter==s.end())
        cout<<"No element greater than 40!"<<endl;
    else
        cout<<"The first element greater than 40 is:"<<*iter<<endl;
    iter=find_if(s.begin(),s.end(),not1(bind2nd(greater<int>(),15)));//通过not1适配器对函数对象取反
    if(iter==s.end())
        cout<<"No element greater than 15!"<<endl;
    else
        cout<<"The first element greater than 40 is:"<<*iter<<endl;
    iter=find_if(s.begin(),s.end(),bind2nd(not2(greater<int>()),15));//通过not2适配器对函数对象取反
    if(iter==s.end())
        cout<<"No element greater than 15!"<<endl;
    else
        cout<<"The first element greater than 15 is:"<<*iter<<endl;
    return 0;
}
~~~

~~~c++
//成员函数适配器实例
#include <functional>
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;
struct Car{
    int id;
    Car(int id){this->id=id;}
    void display() const{
        cout<<"car"<<id<<endl;
    }
};
int main(){
    vector<Car*> pcars;
    vector<Car> cars;
    for(int i=0;i<5;i++)
        pcars.push_back(new Car(i));//动态申请内存操作符new，若申请成功，则返回Car类型的指针
    for(int i=0;i<5;i++)
        cars.push_back(Car(i));//i是初始化参数
    cout<<"elements in pcars:"<<endl;
    for_each(pcars.begin(),pcars.end(),std::mem_fun(&Car::display));//将类的成员函数是配成函数对象，且该函数对象处理的数据类型是对象指针
    cout<<endl;
    cout<<"elements in cars:"<<endl;
    for_each(cars.begin(),cars.end(),std::mem_fun_ref(&Car::display));//将类的成员函数适配成函数对象，且该函数对象处理的数据类型是对象引用
    cout<<endl;
    for(size_t i=0;i<pcars.size();++i)
        delete pcars[i];//每动态申请一次内存，就要释放一次内存
    return 0;
}
~~~

### 算法

STL算法特点：

+ STL算法本身是一种函数模板
  + 通过迭代器获得输入数据
  + 通过函数对象对数据进行处理
  + 通过迭代器将结果输出
+ STL算法是通用的，独立于具体的数据类型、容器类型

STL算法分类：

+ 不可变序列算法
  + 不直接修改所操作的容器内容的算法
  + 用于查找指定元素、比较两个序列是否相等、对元素进行计数等
+ 可变序列算法
  + 可修改所操作的容器对象
  + 用于对序列进行复制、删除、替换、倒序、旋转、交换、分割、去重、填充、洗牌及生成序列
+ 排序和搜索算法
  + 对序列进行排序、合并两个有序序列、对有序序列进行搜索、有序序列的集合操作、堆算法
+ 数值算法
  + 求序列元素的和、部分和、相邻元素的差、两序列的内积

## 第十一章 流类库与输入输出

### I/O流的概念及流类库结构

流是一种抽象，负责在数据生产者与消费者之间建立联系，并管理数据流动

流对象与文件操作：

+ 程序建立一个流对象
+ 指定这个流对象与某个文件对象建立连接
+ 程序操作流对象
+ 流对象通过文件系统对所连接的文件对象产生作用

提前与插入：

+ 读操作在流数据抽象中被称为从流中提取
+ 写操作在流数据抽象中被称为向流中插入

### 输出流概述

最重要的三个输出流：

+ ostream
+ ofstream
+ ostringstream

预先定义的输出流对象：

+ cout：标准输出
+ cerr：标准错误输出，没有缓冲，发送给cerr的内容立即被输出
+ clog：标准错误输出，有缓冲，缓冲区满时被输出

构造输出流对象：

+ ofstream类支持磁盘输出
+ 如果在构造函数中指定一个文件名，当构造这个对象时该文件是自动打开的
  + ofstream myFile("filename");
+ 可以在调用默认构造函数后使用open成员函数打开文件
  + ofstream myFile;//声明一个静态文件输出流对象
  + myFile,open("filename");//打开文件，使流对象与文件建立联系
+ 在构造对象或用open打开文件时可以指定模式
  + ofstream myFile("filename",ios_base::out|ios_base::binary);

文件输出流成员函数的三种类型：

+ 与操纵符等价的成员函数
+ 执行非格式化写操作的成员函数
+ 其他修改流状态且不同于操纵符或插入运算符的成员函数

文件输出流成员函数：

+ open函数
  + 把流与一个特定的磁盘文件关联起来
  + 需要指定打开模式
+ put函数
  + 把一个字符写到输出流中
+ write函数
  + 将内存中的一块内容写到一个文件输出流中
+ seekp和tellp函数
  + 操作文件流的内部指针
+ close函数
  + 关闭与一个文件输出流关联的磁盘文件
+ 错误处理函数
  + 在写到一个流时进行错误处理

### 向文本文件输出

插入运算符：

+ 为所有标准C++数据类型预先设计的，用于传送字节到一个输出流对象

操纵符：

+ 插入运算符与操纵符一起工作，用来控制输出格式
+ 很多操纵符都定义在ios_base类、<iomanip>头文件中
+ 控制输出宽度
  + 在流中放入setw操纵符过调用width成员函数为每个项指定输出宽度
+ setw和width仅影响紧随其后的输出项，但其他流格式操纵符保持有效直到发生改变
+ dec、oct、hex操纵符设置输入和输出的默认进制

setiosflags操纵符：

+ 通过使用带参数的setiosflags操纵符来设置左对齐，setiosflags定义在头文件iomanip中
+ 参数ios_base::left是ios_base的静态常量，引用时必须加上ios_base::前缀
+ 可以使用resetiosflags操纵符关闭左对齐标志，直到resetiosflags恢复默认值时作用结束
+ setiosflags的参数是该流的格式标志值，可用按位或运算符进行组合

精度：

+ 浮点数输出精度的默认值是6
+ 可通过setprecision操纵符改变精度
+ 如果不指定fixed或scientific，精度值标志有效数字位数
+ 如果设置了ios_base::fixed或ios_base::scientific精度值表示小数点之后的位数

### 向二进制文件输出

二进制文件流：

+ 使用ofstream构造函数中的模式参量指定二进制输出模式
+ 以通常方式构造一个流，然后使用setmode成员函数，在文件打开后改变模式
+ 通过二进制文件输出流对象完成输出

### 向字符串输出

字符串输出流：

+ 用于构造字符串
+ 功能：
  + 支持ofstream类的除open、close外的所有操作
  + str函数可以返回当前已构造的字符串
+ 典型应用：将数值转换为字符串

### 输入流概述

重要的输入流类：

+ istream类最适合用于顺序文本模式输入，cin就是istream类的实例
+ ifstream类支持磁盘文件输入
+ istringstream

构造输入流对象：

+ 如果在构造函数中指定一个文件名，当构造这个对象时该文件是自动打开的
  + ifstream myFile("filename");

+ 可以在调用默认构造函数后使用open成员函数打开文件
  + ifstream myFile;//声明一个静态文件输出流对象
  + myFile,open("filename");//打开文件，使流对象与文件建立联系
+ 打开文件时可以指定模式
  + ifstream myFile("filename",ios_base::in|ios_base::binary);

使用提取运算符从文本文件输入：

+ 提取运算符(>>)对于所有标准C++数据类型都是预先定义好的
+ 是从输入流对象获取字节最容易的方法
+ ios类中有很多操纵符可用于输入流，但是只有少数几个对输入流对象有实际影响，其中最重要是进制操纵符dec、oct、hex

输入流相关函数：

+ open函数将流对象与特定磁盘文件相关联
+ get函数功能与提取运算符相似，不同点在于get函数读入数据时包括空白字符
+ getline函数的功能是从输入流中读取多个字符，并且允许指定输入终止字符，读取完成后，从读取的内容中删除终止字符
+ read函数功能是一个文件读取字节到指定的内存区域
  + 由长度参数确定要读的字节数
  + 当遇到文件结束或者在文本模式文件中遇到文件结束标记字符时结束读取
+ seekg函数用来设置文件输入流中读取数据位置的指针
+ tellg函数返回当前文件读指针的位置
+ close函数关闭 与文件输入流关联的磁盘文件

### 从字符串输入

字符串输入流：

+ 用于从字符串读取数据
+ 在构造函数中设置要读取的字符串
+ 功能：
  + 支持ifstream类的除open、close外的所有操作
+ 典型应用：将字符串转换为数值

### 输入/输出流

两个重要的输入/输出流：

+ iostream对象可以是数据的源或目的
+ 两个重要的I/O流类都是从iostream派生的，且都继承了istream和ostream类的功能，分别为
  + fstream类
    + 支持磁盘文件输入与输出
    + fstream类对象可在同一个磁盘上进行读写
    + fstream类对象拥有两个单个流的逻辑子流，分别用于输入和输出
  + stringstream类
    + 支持面向字符串的输入和输出
    + stringstream类对象可对同一个字符串的内容进行读写
    + stringstream类对象拥有两个单个流的逻辑子流，分别用于输入和输出

## 第十二章 异常处理

### 异常处理的思想与程序实现

异常处理的基本思想

+ 沿着函数调用的逆方向，向调用者抛出异常

异常处理的语法

+ 抛掷异常的程序段
+ 捕获并处理异常的程序段
+ 若有异常则通过throw创建一个异常对象并抛掷
+ 将可能抛出异常的程序段嵌在try块中，通过正常的顺序执行到达try语句，然后执行try块内的保护段
+ 如果在保护段执行期间没有引起异常，那么跟在try块后的catch子句就不执行
+ catch子句按其在try块后出现的顺序被检查，匹配的catch子句将捕获并处理异常(或继续抛掷异常)
+ 如果匹配的处理器未找到，则会自动调用库函数terminate，其默认功能是调用abort终止程序

异常接口声明

+ 函数显式声明可能抛出的异常，有利于函数的调用者为异常做准备
+ 可在函数声明中列出该函数可能抛出的所有异常类型
+ 若没有异常接口声明，则该函数可以抛出任何类型的异常
+ 如果函数不会抛掷任何类型异常，函数声明如下：
  + void fun() throw();

### 异常处理中的构造与析构

自动的析构：

+ 找到一个匹配的catch异常处理后
  + 初始化异常参数
  + 将从对应的try块开始到异常被抛掷处之间构造的所有自动对象进行析构
  + 执行当前catch中的语句
  + 依次处理后面的catch
  + 从最后一个catch后面的程序开始恢复执行

### 标准程序库异常处理

标准异常类的继承关系

+ exception是所有异常类的基类

标准异常类的基础：

+  exception：标准程序库异常类的公共基础
+ logic_error表示可以在程序中被预先检测到的异常
  + 这类异常在编写程序时可以避免
+ runtime_error表示难以被预先检测的异常

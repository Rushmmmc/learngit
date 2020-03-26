# Head First Java

[TOC]

## 导包

## 创建

## 使用

## 重写 重载

重写：重写是子类对父类的允许访问的方法的实现过程进行重新编写，返回值和形参都不能改变，即外壳不变，核心重写。

重载：在一个类里面，方法名字相同，参数不同，返回类型可以相同也可以不相同。

每个重载的方法都必须有独一无二的参数类型列表。

### 重写实例

```
class Animal{
public void	move(){
System.out.println("动物可以移动");
 }
}
class Dog extends Animal{
public void move(){
System.out.println("狗可以跑和走");
 }
}
public static void(String[] args){
Animal a = new Animal();
Animal b = new Dog();
a.move();
b.move();
}
```

![image-20200320004157270](C:\Users\Rush\AppData\Roaming\Typora\typora-user-images\image-20200320004157270.png)

结果：

### 重载实例

```
public class Overloading {
    public int test(){
        System.out.println("test1");
        return 1;
    }
 
    public void test(int a){
        System.out.println("test2");
    }   
 
    //以下两个参数类型顺序不同
    public String test(int a,String s){
        System.out.println("test3");
        return "returntest3";
    }   
 
    public String test(String s,int a){
        System.out.println("test4");
        return "returntest4";
    }   
 
    public static void main(String[] args){
        Overloading o = new Overloading();
        System.out.println(o.test());
        o.test(1);
        System.out.println(o.test(1,"test3"));
        System.out.println(o.test("test4",1));
    }
}
```

![image-20200320010322164](C:\Users\Rush\AppData\Roaming\Typora\typora-user-images\image-20200320010322164.png)

## 类和方法的定义

源文件：.java，带有类的定义。

类：表示程序的一个组件，小程序或许只有一个类，类带有一个或多个方法。

public class Dog	{	//	Dog类

​	void bark()	{ 	//	bark方法	

​	statement1;

​	statement2;	

​	

​	}



}





### 为何所有的东西都得包含在类中？

答：因为Java是面对对象语言，而C等语言是面对过程语言。

### C语言中可以使用 int x=1 while(x)... Java也可以吗？

答：不可以，Java中的integer与boolean两种类型并不相容。

boolean isHot = ture;

while(isHot) {}

## print和println的区别

System.out.print

System.out.println

不同：println相当于自动换行。

### 计算字符串数量的接口

计算字符串数组的字符串数量

如 String[] = wordListOne=...;

int oneLength = wordListOne.length;

### 使用随机数字的接口

随机数字（为double型）

Math.random()

要整数的话 强制转换（int)即可

### C语言和Java的字符串定义

注意

**C语言：char a[100] = "abc";**

**Java : String a = "abc";**

两者都需要双引号。

### Java字符串的增添

String s = "fido";

s = s + " " + "is a dog";

# 对象

## 继承

次级类会继承上级类的方法，子类会自动获得父类的功能。

#### 覆盖

让Amoeba这个类去覆盖rotate()与playsound()这两个父类的方法。

覆盖：由子类重新定义继承下来的方法，以改变或延伸此方法的行为。

## 建立对象

dog d = new dog(); **//建立对象**

d.bark(); **//通过操作和调用**

d.size = 40; **//通过操作数存取属性**

## Java没有全局变量

## 堆

存放对象的内存区域。

### 内存回收

当对象使用完Java会主动管理内存，当某个对象被Java虚拟机察觉不再会被使用时，该对象就会被标记为可回收的。如果内存开始不足，垃圾收集器就会启动来清理垃圾、回收空间。

### Java并无全局变量

任何变量只要加上public,static和final，基本上都会变成全局变量取用的常数。

## 什么是Java程序？

Java程序是由一组类所组成，其中有一个类会带有启动用的main()方法。

### Java中的事物都必须待在类中

因此，pi常数或random()方法也必须定义在Math这个类中，类似全局的事物在Java中算是例外。它们非常特殊，不会有多个实例或对象。

## 若有成百上千的类？

可以把所有文件包装进依据pkzip格式来存档的Java Archive-.jar文件。

在jar文件中可以引入一个简单文字格式的文字文件，它被称为manifest，里面有定义出jar中的哪一个文件带有启动应用程序main()的方法。

## 方法

对象可执行的动作称为方法，它代表对象的动作。

### Java的程序在执行期是一组会互相交谈的对象。

## primitive主数据类型

类型						位数							值域

boolean	     由Java虚拟机决定			ture或false

char 				16bits								0-65535

## integer数值

byte						8                                 -128~127

short			 		 16								-32768~32767

int						   32 								-很大~很大

long						64							     -更大~更大

## 浮点数

float						32								变化范围可变

double				    64								变化范围可变	

### 除这八种其余都是引用数据类型

## float f = 32.5f; 除非加上f，否则所有带小数点的值都会被Java当做double处理。

### 老生常谈规则

名称必须以字母、下划线或$符号开头，不能用数字开头。

要避开保留字。

### 保留字：编译器要辨别的关键字。

![1584494145068](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\1584494145068.png)



### 改变数组的大小

int[] nums;

nums = new int[7];

### Dog数组

Dog[] pets = new Dog[7];

pets[0] = new Dog();

pets[1] = new Dog();

### 实例变量应该标记为private,并通过getter与setter来存取。

## 强制转换

将String转换为int：Integer.parseInt("3")

## parselnt只对只有数字的字符串起作用，否则报错。

# 循环

## Java的for循环

### 类似C语言的

循环条件可以用类似integers.length等来描述

### for(int i : integers)

int [] integers = {1,2,3,4};

for(int i : integers) {

System.out.println(i);

}

# Collection

## 集合与数组的区别

数组的长度是固定的，集合的长度是可变的。

集合可以存储的对象的类型可以不一样。

## 遍历Collection对象

### 建立Collection对象

Collection c = new ArrayLIst();//ArrayList是Collection下的一个子类

#### Collection的功能

#### add

import java.util.Collection;

import java.util.ArrayList;

Collection c = new ArrayList();

c.add("abc1");

c.add("abc2");//add这个方法永远返回ture

Collection c2 = new ArrayList();

c2.add("abc1");

c2.add("abc2");

c1.addAll(c2);

c1.remove("abc");//只有至少一个元素被移除了，才返回ture.

### Remove

## Collection子接口

## List（元素有序，元素可重复） Set（无序，不可重复）。

### List下接口

#### ArrayList Vector LinkedList

### Set下接口

#### <span style='color:red'>HashSet TreeSet</span>
















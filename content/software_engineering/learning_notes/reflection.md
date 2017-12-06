Title: Java学习笔记-反射
Date: 2017-12-06 19:00:00
Modified: 2017-12-06 19:00:00
Category: 软件工程
Tags: Java学习笔记
Slug: 
Author: easyfun

###Java反射

JVM内存空间分布
	程序计数器（线程执行环境 ）
	Java虚拟机栈（线程执行环境 ）
	本地方法栈（线程执行环境 ）
	Java堆（线程共享）
	方法区（线程共享）
	运行时常量池（线程共享）
	直接内存（线程共享）

1. 类加载器的作用是什么？
加载Java的字节码（class）文件，在加载过程中会解析、验证字节码文件，载入方法区

2.反射实现的基础是什么？如何理解Class类？
Class类
Class类是描述类信息的类，例如类名称，父类

3.Class类里边包含的内容？
类名
父类名
方法列表
成员变量列表

4.Class实例化的方式？
	class OneClass {}
	OneClass obj=new OneClass();
	(1) obj.getClass()
	(2) OneClass.class
	(3) Class.forName("OneClass")，注意一定要用全类名

5.Class.forName的工作流程？
(1)用全类名在方法区查找相应的Class对象
(2)如果找到返回对应的Class对象
(3)如果没有找到，从磁盘或者远程服务器加载类，加载失败抛出ClassNotFound异常，加载成功返回对应的Class对象

6.反射概念的总结
用Class实例化具体类对象，从而设置具体类对象的成员变量，或者调用具体类的成员方法

7.反射在框架中的应用？
IOC，AOP，设置对象属性

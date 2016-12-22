# python考核

* 以下的代码的输出将是什么? 说出你的答案并解释。

```python
class Parent(object):
    x = 1

class Child1(Parent):
    pass

class Child2(Parent):
    pass

print Parent.x, Child1.x, Child2.x
Child1.x = 2
print Parent.x, Child1.x, Child2.x
Parent.x = 3
print Parent.x, Child1.x, Child2.x
```

* 以下的代码的输出将是什么? 说出你的答案并解释？

```python
def div1(x,y):
    print("%s/%s = %s" % (x, y, x/y))

def div2(x,y):
    print("%s//%s = %s" % (x, y, x//y))

div1(5,2)
div1(5.,2)
div2(5,2)
div2(5.,2.)
```

* 下面这段代码的输出是什么:

```python
def f(x,l=[]):
    for i in range(x):
        l.append(i*i)
    print(l) 

f(2)
f(3,[3,2,1])
f(3)
```

* 写出Python生成指定长度的斐波那契数列程序。

* 简述一下Unicode，UTF-8和GB2312的区别和联系。

* `*args`, `**kwargs是什么东西`? 我们为什么会用它？

* Python里面如何实现tuple和list的转换？

* for循环9*9乘法表

* 自定义模块，加载模式，使用模块的方法，数据（使用__name__属性）

* 使用subprocess模块完成病毒自我复制
```shell
1.判断当前病毒是否已经在运行，如果是，那么我就不再运行
2.病毒感染对象为python脚本(Python script)
3.可执行的可写的[ -w file -a -x file ]
4.感染病毒的脚本执行的时候会额外输出"I am evil！" 
5.病毒能够自我复制
6.如果已经被感染，就不再感染
```

* 使用subprocess模块完成批量添加用户
```shell
	/tmp/useraddlist1
	dabao 888 xuexi,it uplooking
	lucy 889 sales,it uplooking
	lily 899 pro,aa uplooking
```
* 虚拟环境的搭建，激活和退出；第三方包的安装  ​

* 获取访问日志中访问次数最多的ip地址

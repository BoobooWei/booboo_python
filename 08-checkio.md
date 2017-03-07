# checkio

## Non-unique Elements

```python
def checkio(x_list=[]):
    x_tuple = tuple(x_list)
    for i in x_tuple:
        if x_list.count(i) == 1:
            x_list.remove(i)
    print x_list
```

## roman-numerals 

罗马数字来源于古罗马编码系统。它们是基于字母表的特定字母的组合，所表示的数等于这些数字相加（或者是相减）得到的数。前十位的罗马数字是：

I，II，III，IV，V，VI，VII，VIII，IX和X。

罗马记数系统不是直接的十进制为基础，它没有零。罗马数字是根据这七个符号的组合：

符号值

```shell
I 1 (unus)
V 5 (quinque)
X 10 (decem)
L 50 (quinquaginta)
C 100 (centum)
D 500 (quingenti)
M 1,000 (mille)
```

更多额外的关于罗马数字的信息可以参考 维基百科的文章.

在这个任务里，你应该返回给出指定的整数值的范围从1到3999的罗马数字。

输入: 一个整数 (int).

输出: 一个字符串形式的罗马数字 (str).

范例:

```shell
checkio(6) == 'VI'
checkio(76) == 'LXXVI'
checkio(13) == 'XIII'
```

如何使用： 这是一个有教育意义的任务，它让你去探索不同的记数系统。由于罗马数字字体经常使用，它也可以被用于文本生成。建筑外表的年号和基石常写于罗马数字。这些数字在现代世界有许多其他的用途，你可以 在这 了解它......或者，也许你会遇到有一个来自古代罗马的客户;-)

前提: 0 < number < 4000

import sys

def checkio(a_num):
    num_dir = {1:'I',2:'II',3: 'III',4: 'IV',5: 'V',6 :'VI',7: 'VII',8 :'VIII',9: 'IX',10: 'X',20:'XX',30:'XXX',40:'XL',50: 'L',60:'LX',70:'LXX',80:'LXXX',90:'XC',100: 'C',200:'CC',300:'CCC',400:'CD',500: 'D',600:'DC',700:'DCC',800:'DCCC',900:'CM',1000: 'M',2000:'MM',3000:'MMM'}

    a_str = str(a_num)
    len_num = len(a_str)
    roman_list = []
    for i in range(0,len_num):
        xx_num = len_num-i-1
        ww = int(a_str[i])*10**xx_num
        if ww == 0:
                continue
        else:
            roman_list.append(num_dir[ww])

    print ''.join(roman_list)

checkio(3999)

# 笔试选择题考试成绩检测脚本

1. 学生的答题都是保存在文本文档中，以学号命名，一题占一行，区分大小写；
2. 答案保存为00文件

```shell
[root@mastera stutest]# ls
00  10  11  13  16  17  18  19  2  20  24  25  26  27  28  3  31  35  4  43  45  46  5  55  56  58  6  7  9  ule_check.py
```

检测脚本如下
```python
#!/usr/lib/python
# -*- coding: utf-8 -*-


names=locals()
		 
a_list=[]
with open('00','r') as f:
	for i in f.readlines()[:50]:
		a_list.append(i.strip())

file_list=[2,3,4,5,6,7,9,10,11,13,16,17,18,19,20,24,25,26,27,28,31,35,43,45,46,55,56,58]

for f_num in file_list:
	f_str='%d'%f_num
	names['b_list%s' % f_num]=[]
	with open(f_str,'r') as f:
        	for i in f.readlines()[:50]:
                	names['b_list%s' % f_num].append(i.strip())
	num = 50

	if len(names['b_list%s' % f_num]) != 50:
		print('{}没有成绩'.format(f_num))	
		continue
	for i in range(0,50):
		if names['b_list%s' % f_num][i]!=a_list[i]:
			num = num - 1
	print('{}的成绩为：{}'.format(f_str,num*2))
```

检测结果如下:

```shell
[root@mastera stutest]# python ule_check.py 
2的成绩为：36
3没有成绩
4没有成绩
5的成绩为：74
6的成绩为：50
7的成绩为：74
9的成绩为：68
10的成绩为：68
11的成绩为：64
13的成绩为：82
16的成绩为：56
17的成绩为：66
18的成绩为：68
19的成绩为：66
20的成绩为：64
24的成绩为：60
25的成绩为：72
26的成绩为：58
27的成绩为：46
28的成绩为：44
31的成绩为：70
35的成绩为：52
43的成绩为：76
45的成绩为：0
46的成绩为：10
55的成绩为：64
56的成绩为：60
58的成绩为：70

```
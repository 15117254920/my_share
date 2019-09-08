### 一、上堂回顾

#### 1.默写题目

> 1.定义一个数字类型的变量，并将其转换为字符串，最后删除该变量
>
> ```Python
> num = 10
> s = str(num)
> del num
> ```
>
> 2.向控制台打印字符串111,222，333，并使用"-"相连
>
> ```Python
> print("111-222-333")
> print("111","222","333",sep="-")
> ```
>
> 3.从控制台输入一个数，判断该数是否是奇数
>
> ```Python
> num = int(input(""))
> if num % 2 == 0:
>   print("偶数")
> else:
>   print("奇数")
>   
> if num % 2 == 1:
>   print("奇数")
> else:
>   print("偶数")
> ```
>
> 4.从控制台输入一个数，打印对应的星期英文【Mon,Tues,Wed,Thur,Fri,Sat,Sun】
>
> ```Python
> num = int(input(""))
> if num <= 0:
>     print("有误")
> elif num == 1:
>     print("Mon")
> else:
>     print("error")
> ```

#### 2.知识点回顾

> 1.关键字和标识符
>
> ​	定义合法标识符的规则：
>
> ​		只能由数字，字母，下划线组成
>
> ​		开头不能是数字
>
> ​		不能是其他特殊符号
>
> ​		不能是关键字和函数名
>
> ​		不能是空格和中文
>
> ​	规范：
>
> ​		具有描述性
>
> ​		遵循驼峰命名法和下划线相连
>
> 2.常量和变量
>
> ​	Python的数据类型：数字Number，String，list，布尔型Boolean，tuple，dict，set
>
> ​		特殊：函数，类
>
> ​	变量：
>
> ​		定义
>
> ​		作用：存储数据，参与运算
>
> ​		内存中的变量：定义变量的时候，会在内存中开辟一块空间，引用指向了一个实体，当一个实体没有引用指向的时候，则会被系统的垃圾回收机制回收，原来的开辟的空间会被释放
>
> ​		删除变量：del   变量名
>
> ​		变量的类型转换：int()   str()   float()
>
> 3.输入输出
>
> ​	print：基本用法【占位符格式化字符串】
>
> ​	input：结果都是字符串
>
> 4.运算符
>
> ​	算术运算符：%       **      //
>
> ​	赋值运算符：=：给变量进行赋值
>
> ​				复合：等价关系
>
> ​	关系运算符：结果都是布尔值
>
> 5.if
>
> ​	if    if-else    if-elif-else

#### 3.作业讲解

> ```Python
> import  random
>
>
> #5.从控制台输入两个数，输出较大的值
> num1 = int(input(""))
> num2 = int(input(""))
> if num1 > num2:
>     print("num1 = ",num1)
> elif num1 < num2:
>     print("num2 = ",num2)
> else:
>     print("相等",num1)
>
>
> #2.从控制台输入三个数，输出较大的值
> n1 = int(input(""))
> n2 = int(input(""))
> n3 = int(input(""))
> #思路：假设法【首先定义一个变量，将n1或者n2或者n3中的任何一个数赋值给该变量，假设该数就是最大值
> # ,如果发现有其他的数比该数还大，说明假设是不成立的，给max重新赋值】
> maxVal = n1
> if n2 > n1:
>     maxVal = n2
>
> if n3 > maxVal:
>     maxVal = n3
>
> print(maxVal)
>
> result = max(n1,n2,n3)
>
>
> #3.从控制台输入一个三位数，如果是水仙花数就打印“是水仙花数”，否则打印“不是水仙花数”
>
> 	#例如：153=1^3+5^3+3^3
> n4 = int(input(""))
> #第一步：获取各个位数上的数      %   //
> gw = n4 % 10
> sw = n4 // 10 % 10      #n4 % 100 //10
> bw = n4 // 100
> result = gw ** 3 + sw ** 3 + bw ** 3     #pow(gw,3)
> if n4 == result:
>     print("水仙花数")
> else:
>     print("bu")
>
>
> #1.x 为 0-99 取一个数,y 为 0-199 取一个数,如果 x>y 则输出 x， 如果 x 等于 y 则输出 x+y，否则输出y
> #获取随机数：第一步：导入import random   第二步：random.choice(range(0，n+1,5)),表示获取0~n-1之间的随机数
> a = random.choice(range(100))
> b = random.choice(range(200))
> if a > b:
>     print("a = %d" %(a))
> elif a == b:
>     print("a + b = %d"%(a + b))
> ```

### 二、运算符与表达式【第二部分】

#### 1.逻辑运算符

##### 1.1使用

> 作用：进行设置条件，运算的结果为布尔值
>
> 使用：一般结合关系运算符使用
>
> 逻辑与：and
>
> ​	表达式1  and 表达式2  ：只有当表达式1和表达式2同时成立的时候，则返回True
>
> 逻辑或：or
>
> ​	表达式1  or  表达式2  ：当表达式1或者表达式2中任意一个成立的时候，则返回True
>
> 逻辑非：not
>
> ​	not 表达式：真----》假  假----》真
>
> 代码演示：
>
> ```Python
> #逻辑与
> num1 = 10
> num2 = 20
> #使用算术表达式或者变量
> if num1 - 10 and num2:
>     print("yes")
>
> #结合关系运算符使用
> if num1 == num2 and num1 - num2:
>     print("yes")
>
> #结合赋值运算符使用
> #if num1 += 1 and num1:     #SyntaxError: invalid syntax   语法错误
> #   print("yes")
>
> #总结：逻辑运算符一般可以结合变量，算术表达式，关系表达式使用
>
> #逻辑或
> if num1 or num2:
>     print("yes")
>
> if num1 < num2 or num1 == num2:
>     print("成立")
>
> #逻辑非
> if not num1 > num2:
>     print("真")
>
>
> #练习1：从控制台输入一个数，如果该数能被3或者7整除的话，则输出该数，否则输出xxx
> """
> num = int(input("请输入一个数："))
> if num % 3 == 0 or num % 7 == 0:
>     print(num)
> else:
>     print("xx")
> """
>
> #练习：从控制台输入一个年份，判断该年是否是闰年
> """
> 闰年：
> 第一种情况：能被4整除，但是不能被100整除    同时成立
> 第二种情况：能被400整除
> """
> year = int(input("请输入一个年份"))
> #方式一：嵌套if语句
> if year % 400 == 0:
>     print("闰年")
> elif year % 4 == 0:
>     if year % 100 != 0:
>         print("闰年")
> else:
>     print("平年")
> #注意：理论上嵌套的层数没有限制，但是，为了代码的可读性，嵌套的层数不超过三层
>
> #方式二：逻辑运算符
> if (year % 4 == 0 and year % 100 != 0) or year % 400 == 0:
>     print("闰年")
> else:
>     print("平年")
>
> #说明：嵌套if语句和逻辑and可以进行相互转化
> ```

##### 1.2短路原则

> 【面试题】
>
> 出现的时机：在一个表达式中，逻辑运算符不止一个的时候，则很可能会出现短路原则
>
> 规律：
>
> ​	表达式1  or  表达式2.。。。
>
> ​	a.表达式从左往右进行计算，如果第一个逻辑运算符是or，而且表达式1的值为真，则整个表达式的结果为真【不严谨】
>
> ​	举例：表达式1  or  表达式2  or 表达式3   and   表达式4
>
> ​	b.表达式从左往右进行计算，如果第一个逻辑运算符是and，而且表达式1的值为假，则整个表达式的结果为假【不严谨】
>
> ​	举例：表达式1  and  表达式2  and 表达式3   or 表达式4
>
> ​	c.表达式从左往右进行计算，and的左边为真，or的左边为假，则不遵循短路原则
>
> 代码演示：
>
> ```Python
> #1.逻辑运算符全部是and：第一个and的左边是False
> def a():
>     print("A")
>     return  False
> def b():
>     print("B")
>     return  False
> def c():
>     print("C")
>     return  True
> def d():
>     print("D")
>     return  False
> def e():
>     print("E")
>     return  True
>
> #False and False and true and False and True
> """
> 1.整个表达式的值：False
> 2.a()结果为False，直接计算整个表达式的结果，将其他的表达式短路，打印A
> """
> if a() and b() and c() and d() and e():
>     print("ok")
>
> #2.逻辑运算符全部是and：第一个and的左边是True
> def a():
>     print("A")
>     return  True
> def b():
>     print("B")
>     return  True
> def c():
>     print("C")
>     return  False
> def d():
>     print("D")
>     return  False
> def e():
>     print("E")
>     return  True
>
> print("~~~~~~")
>
> #True and True and False and False and True
> """
> True and True and False and False and True
> True and False and False and True   ----->A   B
> False  and False and True     ---->C
>
> 1.整个表达式的值：False
> 2.按照上面的步骤执行，打印A  B   C
> """
> if a() and b() and c() and d() and e():
>     print("ok")
> print("~~~~~~")
>
> #3.逻辑运算符全部是or：第一个or的左边是True
> def a():
>     print("A")
>     return  True
> def b():
>     print("B")
>     return  False
> def c():
>     print("C")
>     return  True
> def d():
>     print("D")
>     return  False
> def e():
>     print("E")
>     return  True
>
> #True or False or True or False or True
> """
> 1.整个表达式的值：True
> 2.出现了短路，打印A
> """
> if a() or b() or c() or d() or e():
>     print("ok")
>
> print("~~~~~~")
>
> #4逻辑运算符全部是or：第一个or的左边是False
> def a():
>     print("A")
>     return  False
> def b():
>     print("B")
>     return  False
> def c():
>     print("C")
>     return  True
> def d():
>     print("D")
>     return  False
> def e():
>     print("E")
>     return  True
>
> #False or False or True or False or True
> """
> False or False or True or False or True
> False  or True or False or True  ----->A   B
> True  or False or True      ----->C
>
>
> 1.整个表达式的值：True
> 2.按照上面的步骤分析，打印A  B  C  ok
> """
> if a() or b() or c() or d() or e():
>     print("ok")
>
> print("~~~~~~")
>
> #5.逻辑运算符and和or混合使用
> def a():
>     print("A")
>     return  False
> def b():
>     print("B")
>     return  False
> def c():
>     print("C")
>     return  True
> def d():
>     print("D")
>     return  False
> def e():
>     print("E")
>     return  True
> def f():
>     print("F")
>     return  True
> def g():
>     print("G")
>     return  False
> def h():
>     print("H")
>     return  True
>
> #False and False and True and False or True and True or False and True
>
> """
> A           B       C        D         E       F           G      H
> False and False and True and False or True and True or False and True
> False or True and True or False and True  ------>A,短路了BCD
> True  and True or False and True     ----》E
> True or False and True  ----->F,短路了G
> #True and True  ---->H
> """
>
> if a() and b() and c() and d() or e() and f() or g() and h():
>     print("ok45343")
>
> #特殊情况：True or False and True，如果一个表达式中只有两个逻辑运算符，第一个为or，第二个and，
> # 而且表达式1的值是True，直接得到一个结果True，接着执行表达式2，但是表达式3不执行
>
>
> #注意：在实际项目开发中，如果需要出现多个and和多个or的时候，就是通过括号避免短路原则
> #混合使用，最多会出现4个
> ```

#### 2.成员运算符

> 注意：成员运算符一般在list中使用
>
> in:如果在指定列表中找到某个值，则返回True
>
> not in:如果在执行列表中找不到某个值，则返回True

#### 3.身份运算符

> is:判断两个变量是否引用自同一个实体
>
> is not:判断两个变量是否引用自不同的实体
>
> 注意：运算的结果为布尔值
>
> 代码演示：
>
> ```Python
> a = 10
> b = 10
>
> print(id(a))
> print(id(b))
>
> if a is b:
>     print("yes")
> else:
>     print("no")
>
> if a is not b:
>     print("yes")
> else:
>     print("no")
>
> if a == b:
>     print("成立")
> else:
>     print("不成立")
>
> if id(a) == id(b):
>     print("成立****")
> else:
>     print("不成立****")
>
> a1 = 10
> b1 = 20
> if a1 is b1:
>     print("yes~~")
> else:
>     print("no~~~")
>
> if a1 is not b1:
>     print("yes~~~")
> else:
>     print("no~~~")
>
> if a1 == b1:
>     print("成立")
> else:
>     print("不成立")
>
> if id(a1) == id(b1):
>     print("成立****")
> else:
>     print("不成立****")
> ```
>
> 总结：
>
> ​	身份运算符判断的是变量的地址【类似于id(xx)  == id(xx) 】
>
> ​	==:判断的是值【基本数据类型】

#### 4.运算符的优先级

> 注意：在实际应用中，尽量不要书写过于复杂的表达式，尽量分步操作，或者添加括号

### 三、循环语句之while语句

#### 1.概念

> 广义：一个现象周期性或者重复性的出现
>
> 狭义：在满足条件的情况下，反复执行某一段代码，在编程语言中这种现象被称为循环，这段被重复执行的代码就被称为循环体
>
> 问题：当反复执行某段代码的时候，需要在合适的时机将条件改为假，从而结束循环，否则循环将一直进行下来，从而形成死循环

#### 2.while语句

##### 2.1基本语法

> while 条件:
>
> ​	循环体
>
> 说明：while和if语句的区别：和if语句的语法类似，只不过if语句在条件成立的情况下只执行一次，而while语句在条件成立的情况下至少会执行一次
>
> 工作原理：当程序从上往下依次执行的过程中，如果遇到了while语句，首先会判断条件是否成立，如果成立则执行循环体，然后再去判断条件是否成立，。。。。。直到条件不成立时，整个while语句才结束，然后继续执行后面的代码
>
> 代码演示：
>
> ```Python
> ##需求：打印10遍hello world
> #核心：控制循环的次数
> #1.定义一个变量，用于控制循环的次数【初始化表达式】
> num = 0
> #2.设置循环判断的条件，需要跟变量有关【条件表达式】
> while num < 10:
>     #3.【循环体】
>     print("hello world")
>     #4.【循环之后的操作表达式】
>     num += 1   #num = num + 1
>
> #练习：打印0~9的整数
> n = 0
> while n < 10:
>     print(n)
>     n += 1
>
> #练习：求1~100之间所有整数的和
> n1 = 1
> #定义一个变量，用于记录得到的和
> total = 0
> while n1 <= 100:
>     #print(n1)
>     total += n1
>     n1 += 1
> print(total)
>
> #练习：求1~100之间偶数的和【while语句和if语句的结合使用】
> #方式一
> n2 = 0
> total1 = 0
> while n2 <= 100:
>     total1 += n2
>     n2 += 2
>
> #方式二
> n3 = 1
> total2 = 0
> while n3 <= 100:
>     if n3 % 2 == 0:
>         total2 += n3
>     n3 += 1
> ```

##### 2.2else语句

> while 条件:
>
> ​	循环体
>
> else:
>
> ​	执行语句
>
> 代码演示：
>
> ```Python
> #1.当循环条件成立:循环体执行完毕之后才执行else
> #注意：区别if语句中的else，如果条件成立，则else没有执行的机会
> a = 1
> while a < 3:
>     print("hello")
>     a += 1
> else:
>     print("else被执行了")
>
>
> #2.当循环条件不成立：直接去执行else
> b = 5
> while b > 10:
>     print("hello~~~~")
> else:
>     print("else被执行了~~~~~")
>
> #总结：不管while语句的条件是否成立，else都会被执行
> ```

##### 2.3死循环

> 在循环语句中，表达式永远为真的循环
>
> 代码演示：
>
> ```Python
> #3.死循环
> while 1:
>     print("fdg")
> while True:
>     print("fdhjgh")
> ```

##### 2.4嵌套循环

> 类似于嵌套if语句
>
> 语法
>
> while 表达式1：
>
> ​	while 表达式2：
>
> ​		循环体
>
> 代码演示：
>
> ```Python
> #需求：打印九九乘法表
> """
>                                                         行           列
> 1x1=1                                                   1               1
> 1x2=2 2x2=4                                             2               2
> 1x3=3 2x3=6 3x3=9
> .....
> 1x9=9 2x9=18    ......       7x9=63  8x9=72 9x9=81      9               9
>
> 规律：
> 1.列数随着行数的变化而变化
> 2.列数的最大值和行数相等
> 3.表达式的组成：列x行=乘积
> 行的取值范围：1~9
> 列的取值范围：1~行数
> """
> #外层循环:控制行
> #定义一个变量，表示行
> line = 1
> while line <= 9:
>     #内层循环：控制列
>     #定义一个变量，表示列
>     colum = 1
>     while colum <= line:
>         #打印
>         #如果打印的内容是同一行中的内容的时候，阻止换行
>         print("%dx%d=%d"%(colum,line,line * colum),end=" ")
>         colum += 1
>     #换行
>     print("")
>     line += 1
>
> #嵌套循环的原理
> n1 = 1
> while n1 <= 3:
>     n2 = 1
>     while n2 <= 5:
>         print("%d = %d" %(n1,n2))
>         n2 += 1
>     n1 += 1
>
> #练习：打印如下图形
> """
> *
> **
> ***
> ****
> *****
> """
> i = 1
> while i <= 5:
>     j = 1
>     while j <= i:
>         print("*",end="")
>         j += 1
>     i += 1
>     print("")
> ```

##### 2.5练习

> 代码演示：
>
> ```Python
> #1.计算100~1000之间能被6整除的数的和
> n1 = 100
> sum1 = 0
> while n1 <= 1000:
>     if n1 % 6 == 0:
>         sum1 += n1
>     n1 += 1
> print(sum1)
>
>
> #2.计算100~1000之间能被6整除的数的个数
> n1 = 100
> count = 0
> while n1 <= 1000:
>     if n1 % 6 == 0:
>         count += 1
>     n1 += 1
> print(count)
>
> #3.计算10的阶乘
> n2 = 1
> result = 1
> while n2 <= 10:
>     result *= n2
>     n2 += 1
> print(result)
> ```

#### 3.break和continue和pass

##### 3.1break

> 作用：跳出循环【直接跳出整个循环，继续执行循环后面的代码】
>
> 代码演示：
>
> ```Python
> #1.
> n1 = 0
> while n1 < 5:
>     print("n1= %d"%(n1))
>     if n1 == 3:
>         #注意：break一般单独使用，直接结束整个循环，
>         #break和if语句没有关系，if存在的意义就是为了条件的限制
>         break
>     n1 += 1
>
> #2.特殊情况：如果在while语句中使用break，则else分支不会被执行
> n2 = 0
> while n2 < 5:
>     print("n2= %d"%(n2))
>     if n2 == 3:
>         break
>     n2 += 1
> else:
>     print("else被执行了")
>
> print("~~~~~~~")
>
> #3.特殊情况：break应用在嵌套循环中:跳出最近的循环【跳出当前循环】，就近原则
> n1 = 1
> while n1 <= 3:
>     n2 = 1
>     while n2 <= 5:
>         print("%d = %d" %(n1,n2))
>         if n2 == 2:
>             break
>         n2 += 1
>     n1 += 1
>
> #应用场景：死循环     如果获取到了结果，后面的循环没有进行下去的必要，则可以使用break跳出循环
> ```

##### 3.2continue

> 作用：跳出当前正在执行的循环，然后继续下一次循环
>
> 代码演示：
>
> ```Python
> num = 0
> while num <= 5:
>     print(num)
>     if num == 2:
>         num += 1
>         #break
>         continue
>
>     num += 1
> #在实际应用中，break使用更广，区别于break和continue
>
> ```

##### 3.3pass

> pass是空语句，是为了保证代码结构的完整性
>
> pass不做任何事情，只是为了做占位符
>
> 代码演示：
>
> ```Python
> if 1:
>     pass
>
> a = 0
> while a < 10:
>     pass
> ```
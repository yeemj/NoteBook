### 1. 基本用法——三种输出形式

#### 	1.1 不使用引号

##### 		1.1.1 直接原样输出

~~~python
print(2021)  #整数数据
# 》》2021

print(3.1415926)  #浮点数数据
# 》》3.1415926

list1 = [1,2,3,4,5]  #列表1
list2 = ['Mon','Tues','Wed','Thur','Fri','Sat','Sun'] #列表2
print(list1)
# 》》[1,2,3,4,5]
print(list2)
# 》》['Mon','Tues','Wed','Thur','Fri','Sat','Sun']

tuple1 = (11,22,33)  #元组1
tuple2 = ('listening','speaking','reading','writing')  #元组2
print(tuple1)
#》》(11, 22, 33)
print(tuple2)
#》》('listening', 'speaking', 'reading', 'writing')

dic1 = {'猫':'cat','狗':'dog','猪':'pig'}  #字典
print(dic1)
#》》{'猫': 'cat', '狗': 'dog', '猪': 'pig'}

bool1 = False  #布尔值
print(bool1)
#》》False
~~~

##### 		1.1.2计算结果输出

~~~python
print(1+2)
#》》3
print(7*8)
#》》56
~~~

#### 	1.2 单引号输出（英文符号的单引号''）

- 直接输出单引号中所有的数据
  - 可用于文本数据类型——字符串的输出

~~~python
print('哆啦A梦许愿瓶1：有钱有闲')
#》》哆啦A梦许愿瓶1：有钱有闲

print('哆啦A梦许愿瓶2：满世界兜风')
#》》哆啦A梦许愿瓶2：满世界兜风
~~~

#### 	1.3双引号输出（英文符号的双引号""）

- 直接输出双引号中所有的数据

~~~python
print("哆啦A梦许愿瓶1：有钱有闲")
print("哆啦A梦许愿瓶2：'满世界兜风'")
print("'哆啦A梦许愿瓶3：睡着都笑醒'")
#》》哆啦A梦许愿瓶1：有钱有闲
#》》哆啦A梦许愿瓶2：'满世界兜风'
#》》'哆啦A梦许愿瓶3：睡着都笑醒'
~~~

在用法上和print的双引号输出没有什么区别，但是可以在双引号中包含单引号。

#### 	1.4 三引号输出（英文符号下的三个单引号'''  '''）

- 实现一条print语句换行输出

~~~python
print('''哆啦A梦的许愿瓶：
有钱有闲，
满世界兜风，
睡着都笑醒！''')

#》》结果如下：
-----------------
哆啦A梦的许愿瓶：
有钱有闲，
满世界兜风，
睡着都笑醒！
-----------------
~~~

换行输出的另外一种办法——使用转义字符\n（表示换行）

python中的转义字符[2Python中的转义字符 | yeemj's blog](https://yeemj.github.io/posts/8f920c3/)

~~~python
print('哆啦A梦的许愿瓶：\n有钱有闲，\n满世界兜风，\n睡着都笑醒！')
#》》与三引号换行输出有一样的效果
~~~

### 2. print()函数实质

~~~python
print(*objects, sep=' ', end='\n', file=sys.stdout)
~~~

参数表示
- objects --表示输出的对象。输出多个对象时，需要用 逗号 分隔。
- sep -- 用来间隔多个对象。
- end -- 用来设定以什么结尾。默认值是换行符 \n，可以换成其他字符。
- file -- 要写入的文件对象。

- 多个对象输出`*objects`

  ~~~python
  x = 98
  y = 'yeemj'
  print(x,y)
  #》》98，yeemj
  ~~~

  ~~~python
  print('yeemj''yeeqf')  #输出多个对象没有分隔
  #》》yeemjyeeqf
  print('yeemj','yeeqf')  #输出多个对象有空格分隔
  #》》yeemj yeeqf
  ~~~

  使用间隔符 `sep=' '`

  ~~~python
  print('yeemj','github','io')  #与上一个知识点多个对象输出是相同的道理
  #》》yeemj github io
  print('yeemj','github','io',sep = '.')
  #》》yeemj.github.io
  ~~~

  改变结尾值

  默认结尾符 `end = '\n'`，为换行符，故多个print函数结果为多行。

  ~~~python
  print('yeemj')
  print('github')
  print('io')
  #》》结果如下：
  -----------------
  yeemj
  github
  io
  -----------------
  print('yeemj',end = '  ')
  print('github',end = '  ')
  print('io')
  #》》yeemj  github  io   #数据呈现在一行——没有换行
  
  print('yeemj',end = '-')
  print('github',end = '-')
  print('io')
  #》》yeemj-github-io   #与sep的用法区分开
  ~~~

  写入文件对象

  file参数默认值为 `sys.stdout`，代表系统标准输出。

  改变该参数使print()函数输出到特定的文件中：

  ```python
  file1 = open(r"F:\text.txt","w")         # 打开文件，以便写入print('test',file = file1)            # 输出到文件
  file1.close()                         # 关闭文件
  #》》运行后，可以看到test输出到text.txt文件中。
  ```




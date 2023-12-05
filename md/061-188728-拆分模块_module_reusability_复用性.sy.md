---
show: step
version: 1.0
enable_checker: true
---

# 自制包内容

## 回忆上次内容

- 上次我们编写了一个加法运算程序

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701005206499)

- 输入单个变量没有问题
	- 但是 输入两个变量之后
	- 一相加 就非常离谱

- 这次我们完善了代码
	- 对用户可能出现的录入错误
		- 做了异常处理
	- 整个程序运行正常


- 可以把这程序拆分成
	- 输入 和 输出
	- 两个部分吗？
- 然后用import的方式导入模块？🤔

### 目前程序

```python3
try:
    a = input("How many apples do you have?\n")
    a = int(a)
    print("You got " + str(a) + " apples!")
    b = input("How many bananas do you have?\n")
    b = int(b)
    print("You got " + str(b) + " bananas!")
    total = a + b
    print("You got " + str(total) + " fruits!")
except ValueError:
    print("\33[41merror\33[0m",end="")
    print("your input is invalid!")
    quit()
```

- 可以把这程序拆分成两个部分吗？
- 然后用import的方式导入模块？🤔


### 任务目标

- 想要把原来的fruit.py
	- 拆成 两个py文件
-  input.py 
	-  负责输入 两个数字
	-  分别是
		-  苹果的数量
		-  香蕉的数量
-  output.py
	- 负责计算水果总量
	- 并输出最终水果总数 

### input 和 output

- input.py 

```python3
try:
    a = input("How many apples do you have?\n")
    a = int(a)
    print("You got " + str(a) + " apples!")
    b = input("How many bananas do you have?\n")
    b = int(b)
    print("You got " + str(b) + " bananas!")
except ValueError:
    print("\33[41merror\33[0m",end="")
    print("your input is invalid!")
    quit()
```

- output.py

```python3
try:
	import input
    total = input.a + input.b
    print("You got " + str(total) + " fruits!")
except ValueError:
    print("\33[41merror\33[0m",end="")
    print("your input is invalid!")
    quit()
```

- input.py 和 output.py 	
	- 这两个名字 可以吗？？	

### 命名问题

- 要先避免重名的问题
	- 先跳到游乐场去观察一下

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220214-1644817997994)

- 看起来没有默认的input和output模块
	-  不怕模块被重名了

### 函数名

-  不过input好像是输入函数的名字

```
a = input("How many apples do you have?\n") 
```

- input应该不能被用作模块的名字
	- 一旦被重新赋值
	- 就没法作为函数使用了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231127-1701091183542)

- 为了避免问题
	- 输入模块名修改为 get_fruits.py
	- output.py 这个名字可以放心用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231127-1701091210274)

- 最终的两个程序名为
	- 输入模块 get_fruits.py
	- 输出模块 output.py

- 而且要放进同一个文件中

### 建立文件夹

- pwd
	- print working directory
	- 输出当前工作路径
- mkdir fruits
	- 新建文件夹test
- cd fruits
	- 进入fruits文件夹

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231122-1700660950133)

- 准备编辑
	- 注意此时fruit.py 在 上一层目录中

### 拆分文件

- 同时编辑两个文件
	- get_fruits.py
	- output.py
	- 

```
vi get_fruits.py output.py
```

- 进入vim
	- :ls 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231122-1700661029652)

### 读取

- `:r ../fruits.py`
	- ../fruits.py
	- 上一层目录下的apple.py

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701005401407)

- 此文件可以单独运行没有问题

### 处理和展现

- `:r ../fruits.py`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231122-1700661425538)

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701005486182)

- 成功
	- 真的自制了一个输入模块
- 为什么要把一个完整的程序
	- 拆成两个模块呢？

### 复用性Reusability

- get_fruits.py作为 被导入的模块
	- 后期可以 计算水果总量
	- 后期也可以 计算哪种水果多
	- 后期还可以 计算水果数量差值

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221030-1667092305260)

- 代码 可以在不同的模块之间复用
- 以前用过什么 可复用的代码 吗？


### 复用的函数

- 很多函数 我们一直在复用
	- print
	- input
	- ord
	- chr
- 很多模块 我们也一直在复用
	- time
	- random
	- this
	- `__hello__`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221030-1667092402956)

- 可以感觉到 python 的可扩展性
	- 从 各种自定义的 python 模块
	- 到 python底层的  各种函数
- 因为 python 代码复用这么容易
	- 所以 才有 打一场人民战争的基础
- 如今我们也写了自己的python模块
- 这两个py文件
	- get_fruits.py
	- output.py
- 他们之间是什么关系呢？

### 结构

- 总共两个python文件
	- output.py 是主模块 
		- 用来导入输入模块
	- get_fruits.py 
		- 是被引用的模块

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220214-1644820554863)

- 运行output.py主模块的时候
	- 导入了 被引用的get_fruits.py
		- 先录入
	- 然后输出
- 如何理解 导入 呢？
- 英文
	- import 导入
	- export 导出
	- 词根port 本意为港口

### 总结

- 这次把 apple.py 拆分成了
	- 输入模块
	- 主模块
- 引用模块中变量的时候
	- from 模块(module)的名字空间(namespace)
	  - import 了 a和b
- 最终 
	- 拆分代码 成功！
- 拆成
	- 输入模块
	- 输出模块

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230529-1685370373197)

- 可以将程序 再拆分 吗？

- 然后 
	- 再由主控模块
	- 进行调用
	- 可以吗？🤔
- 下次再说👋🏻

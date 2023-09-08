---
show: step
version: 1.0
enable_checker: true
---

# 自制包内容

## 回忆上次内容

- 上次直接从模块中导入变量、函数
	- from show_time import pi
		- 导入show_time.pi 
		- 并作为pi变量使用
	- from show_time import pi as show_time_pi
		- 导入变量并重命名
- 还记得 上次那个苹果香蕉统计程序吗？
	- 能封装成文件模块
	- 再分别导入么？🤔

### 原始文件

- 先将apple.py恢复好

```python3
a = input("How many apples do you got?\n")
print("You got " + a + " apples!")
b = input("How many bananas do you got?\n")
print("You got " + b + " bananas!")
try:
    total = int(a) + int(b)
    print("You got " + str(total) + " fruits!")
except:
    print("\33[41m[error]\33[0m -- input should be numbers!")
```

- 试运行一下

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230529-1685369067227)

- 运行成功

- 然后:q 
	- 从vim退回到shell

### 建立文件夹

- pwd
	- print working directory
	- 输出当前工作路径
- mkdir test
	- 新建文件夹test
- cd test
	- 进入test文件夹

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230529-1685367320908)

- 进入文件夹test
	- 准备编辑
	- 注意此时apple.py 在 上一层目录中

### 任务目标

- 想要把原来的apple.py
	- 拆成 两个py文件
-  input.py 
	-  负责输入 两个数字
	-  分别是
		-  苹果的数量
		-  香蕉的数量
-  output.py
	- 负责计算水果总量
	- 并输出最终水果总数 
- 那python里面
	- 是否已经有 input和output 模块了呢？	

### 命名问题

- 要先避免重名的问题
	- 先跳到游乐场去观察一下

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220214-1644817997994)

- 看起来没有默认的input和output模块
	-  不怕模块被重名了
-  不过input好像是很重要的函数的名字

```
a = input("How many apples do you have?\n") 
```

- input应该不能被用作模块的名字
	- 输入模块名修改为 get_fruits.py
- output.py 这个名字可以放心用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220214-1644818767055)

- 最终的两个程序名为
	- get_fruits.py
	- output.py

### 拆分文件

1. <kbd>ctrl</kbd> + <kbd>d</kbd> 从游乐场退回到vim
2. :q 从vim 退出
3. 回到shell

```
vi -o get_fruits.py output.py
```

- 进入vim,如下图所示

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667052338279)

- 会分成上下两个窗口(window)
	- 然后可以分别查看和编辑

### 两个窗口都读取

- `:windo r ../apple.py`
	- 在两个窗口中都读取
		- ../apple.py
		- 上一层目录下的apple.py

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230529-1685368425095)

- 键入`:wa`
	- `:wa`的意思是
		- `w`rite `a`ll changed buffers
		- 把所有修改了的缓存都存盘

### 编辑

- <kbd>ctrl</kbd>+<kbd>j</kbd>、<kbd>ctrl</kbd>+<kbd>k</kbd>
	- 可以切换当前上下活动(active)窗口
- 修改代码 如下图所示

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230529-1685368522760)

- 将光标切到下方窗口
	- output.py处之后
	- 然后再用
		- `:wa|!python3 output.py`来运行

### 执行结果

- 输入部分都没有执行	
	- 就直接报错了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230614-1686702098092)

- 在output.py中
	- 添加导入部分
		- import get_fruits 

### 运行结果

- 运行输入部分的环节时
	- 没有问题 
- 运行输出部分的环节时
	- 出错了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667052539345)

- 输入没有问题
- 但是参数a、b
	- 好像没传过去？

### 调试程序

- 从get_fruits.py到output.py的过程中
	- 好像没有传递成功？
	- 到底 `a` 是多少呢？
		- 输出看看

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230529-1685368921688)

- 给正确数据

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667052674349)

- a 根本没有被声明！

### 找到a

- a 为什么不认
	- a 是 getfruits 这个模块(module)里的变量
	- 变量a 隶属于 getfruits这个名字空间(namespace)
- get_fruits.a 可以认么？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220214-1644819876216)

- 上码
- 再战

### 运行

- 这次认了
- 现在需要的就是赋值了

### 最终

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220520-1653042476643)

- 录入数据

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210815-1629037417277)

- 成功
	- 我们真的自制了一个输入模块
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
- 很多模块 我们也一直在服用
	- time
	- random
	- this
	- `__hello__`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221030-1667092402956)

- 可以感觉到 python 的可扩展性
	- 从 各种自定义的 python 模块
	- 到 python底层的  各种函数
- python 代码复用就是这么容易
	- 这才有了 打一场人民战争的基础
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
	- 要带上模块(module)的名字空间(namespace)
	  - get_fruits.a
	  - get_fruits.b
- 最终 
	- 拆分代码 成功！

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230529-1685370373197)

- 可以将程序 再拆分 吗？
- 拆成
	- 输入模块
	- 输出模块
- 然后 
	- 再由主控模块
	- 进行调用
	- 可以吗？🤔
- 下次再说👋🏻

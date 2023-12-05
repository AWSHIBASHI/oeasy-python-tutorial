---
show: step
version: 1.0
enable_checker: true
---

# 自制包内容

## 回忆上次内容

- 上次研究了 一行赋值多个变量
	- a = b = 5
	- a, b = 7, 8
- 还研究了 标识符的惯用命名法
	- python使用的是
		- snake_case 
			- 是蛇形命名法
			- 是 用下划线 分隔开小写字母的 命名方法	
		- 这样就可以 更合理地 命名变量了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701612939193)

- 我们可以做一个像样点的程序吗？？🤔

### 编写程序fruit.py

```python3
a = input("How many apples do you have?\n")
print("You got " + a + " apples!")
```

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004195119)

- 除了输入苹果数量之外
	- 我还想要输入一个香蕉数量
		- 并付给变量b

### 照猫画虎

- 想再来个变量b
- 在正常模式下键入
	- `:1,2t2`
	- :1,2
		- 把从 `第1行` 到 `第2行` 
	- t2
		- 复制到 `第2行` 后面

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004262010)

- 然后修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004328543)


### 运行起来

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230517-1684314667203)

- 运行成功
- 还想要对数量做个汇总

### 汇总函数

```python3
a = input("How many apples do you have?\n")
print("You got " + a + " apples!")
b = input("How many bananas do you have?\n")
print("You got " + b + " bananas!")
total = a + b
print("You got " + total + " fruits!")
```

- 保存并运行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004440429)

- 2 + 3 = 23
	- 就非常离谱了

### 深入调试

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004527599)

- 原来是 数据类型错误导致的
	- 加法运算符 实际运算为 拼接字符串操作


### 基本实验

- 在vim中执行底行命令
	- :!python3 
		- 注意这次没有 % 指代 当前缓存
		- 直接进入游乐场
	
- 两个`整数` 相加 
	- 结果是`求和`
- 两个`字符串` 相加 
	- 结果是`字符串拼接`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667041983654)

- 变量类型不同
	- 导致运算的逻辑不同
- 首先要做的就是
	- `确定类型` 

### 确定类型

- type()函数
	- 可以确定变量的类型
	- 比如 type("1")
- 那么
	- 能把接收 input()的变量类型
		- 输出出来么?

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230613-1686661671083)

- input()函数
	- 返回的类型是字符串型
	- 需要转化为整型变量int

### 修改代码

```python3
a = input("How many apples do you have?\n")
print("You got " + a + " apples!")
b = input("How many bananas do you have?\n")
print("You got " + b + " bananas!")
total = int(a) + int(b)
print("You got " + total + " fruits!")
```

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004698938)

- 类型错误
	- TypeError
	- 字符串 和 整数 无法相加

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231125-1700878028240)


### 转化函数

- 从 input()返回的
	- 是 字符串类型的变量
	- 需要 转化为 数字类型
	- 然后 再相加

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667042052812)

- 好了
	- 思路有了
- <kbd>ctrl</kbd> + <kbd>d</kbd> 退出游乐场
	- 返回vim
	- 整合到原来的 py 程序中吧

### 继续修改

```python3
a = input("How many apples do you have?\n")
print("You got " + a + " apples!")
b = input("How many bananas do you have?\n")
print("You got " + b + " bananas!")
total = int(a) + int(b)
print("You got " + str(total) + " fruits!")
```

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231122-1700659297722)

- 这也是` python之禅` 里面的一句话
  - Explicit is better than implicit
- 怎么理解呢？

### plicare

- plicare是
	- 拉丁语词根折叠
- ex往外折叠
	- explicit 
		- 展开了
		- 掰开了
		- 揉碎了
		- 说清楚了
- im往里折叠
	- implicit
		- 折叠了
		- 遮盖了
		- 掩藏了
		- 暗示了
- Explicit is better than implicit 
  - 明了胜于晦涩

### "1" + 2

- "1" + 2
  - 报错了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667043028745)

- 不接受 隐式的 类型转化
	- 字符串加法后面必须得是字符串
- 如果 要用整数加法 就要把前面
	- `显示地` 转化 为 整数类型
- `明了` 胜于 晦涩
	- `Explicit` is better than implicit

### 1 + "2"

- 这次说的更明确

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667043045467)

- +号的两端不能分别是 int 和 str 
	- 要么转前面
	- 要么转后面
	- 两边应该是同样类型的
- 明了胜于晦涩
	- 这句话确实
		- 真有禅机

- 这 python之禅 还说了些什么？
	- 这些都是谁写的呢？

### python 之禅

- python之禅 是 Tim Peters写的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210815-1629020881552)

- 在游乐场
	- `import this`

### 翻译

- python 之禅 by Tim Peters
  - 优美胜于丑陋（Python 以编写优美的代码为目标）
  - 明了胜于晦涩（优美的代码应当是明了的，命名规范，风格相似）
  - 简洁胜于复杂（优美的代码应当是简洁的，不要有复杂的内部实现）
  - 复杂胜于凌乱（如果复杂不可避免，那代码间也不能有难懂的关系，要保持接口简洁）
  - 扁平胜于嵌套（优美的代码应当是扁平的，不能有太多的嵌套）
  - 间隔胜于紧凑（优美的代码有适当的间隔，不要奢望一行代码解决问题）
  - 可读性很重要（优美的代码是可读的）
  - 即便假借特例的实用性之名，也不可违背这些规则（这些规则至高无上）
  - 不要包容所有错误，除非你确定需要这样做（精准地捕获异常，不写 except:pass 风格的代码）
  - 当存在多种可能，不要尝试去猜测而是尽量找一种，最好是唯一一种明显的解决方案（如果不确定，就用穷举法）
  - 虽然这并不容易，因为你不是 Python 之父（这里的 Dutch 是指 Guido ）
  - 做也许好过不做，但不假思索就动手还不如不做（动手之前要细思量）
  - 如果你无法向人描述你的方案，那肯定不是一个好方案；反之亦然（方案测评标准）
  - 命名空间是一种绝妙的理念，我们应当多加利用（倡导与号召）
- 这些并不是挂在墙上的名言
	- 而是可以指导实践的
- 如果录入字符串
	- 无法转化为数字呢？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004787439)

- 需要try
	- 试着来

### try

```python3
try:
    a = input("How many apples do you have?\n")
    print("You got " + a + " apples!")
    b = input("How many bananas do you have?\n")
    print("You got " + b + " bananas!")
    total = int(a) + int(b)
    print("You got " + str(total) + " fruits!")
except ValueError:
    print("your input is invalid!")
    quit()
```

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004852609)

- 其实a有问题的时候
	- 就该退出了
- 想要让报错信息更加明确一些

### 红色报错

- 其中红色的error
	- 是由下图中红框的部分制作出来的
	- 就像当年屠龙宝刀上的红色爱心一样

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

- 运行效果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231126-1701004900015)

### except

```
print("\33[41merror\33[0m",end="")
```

- 上面代码的作用是
	- 红色底色显示<font style="background:red;color:white">error</font>
		- \33[41m 是使用红色底色
		- \33[0m 是使用默认的黑底白字
	- end=""
		- 输出后并不回车

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231125-1700881353854)


### 直接退出

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

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231122-1700659713960)

- 还是先总结吧


## 总结

- 这次我们编写了一个加法运算程序

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
- 我们下次再说👋




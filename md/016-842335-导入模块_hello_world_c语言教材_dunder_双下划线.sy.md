---
show: step
version: 1.0
enable_checker: true
---

# Hello World!

## 回忆上次内容

- `hello world` 不是 从来就有的
	- 来自于 `unix`和`c`
	- 最初是Thompson 为了游戏而制作的个人项目
	- 后来逐步发展成了操作系统的源头

- 最早的 编程语言学习 
	- 是从那张打字机用纸的手写代码 起源的
- 输出用的函数名 `printf`(打印)	
  -	也是 从那个时候来的 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685518717156)

- 最早输出的是字符串 是 `"hello world"`
	- 也是 从那个时候来的 
	- 这就成了一个梗
- 都说计算机科技日新月异
	- hello world这个梗 
		- 为什么能一直流传到今天？🤔

### 商业背景

- unix 最初是 Thompson 的个人项目
	- Thompsom 是 贝尔实验室的员工
		- 贝尔实验室是 AT&T的 下属机构
			- AT&T 被诉垄断禁止进入计算机行业

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230210-1675993397507)

- 贝尔实验室 
	- 因为被诉垄断	
	- 并没有商业化unix的可能

### 遗传变异

- 软件本身的特性 就是 免费拷贝
	- unix的源代码 
		- 扩散到 各个大学和研究机构

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685519434061)

- 这种文化 是 自由软件运动的基础
	- 自由地共享源码
	- 分散的方式合作开

### 伯克利

- 1975的秋天
	- Thompsom 休了一个长假
	- 回到了母校加州大学伯克利分校
	- 开设了一门Unix课程

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230601-1685624941151)

- 不仅讲解理论
	- 还在晚上带着大家阅读一行行的Unix内核代码
	- 解释为什么这么做

### 硬件

- PDP 系列小型机
	- 伴随着unix 最初的岁月

- 操作系统当时属于新鲜事物
	- Bell 实验室从来没想过 卖操作系统
	- AT&T的垄断禁令给了unix 商业化 第二重的 封印

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230601-1685625011022)

- 伯克利发行版
	- 作为最先进的变种
	- 慢慢抢过unix风头
	- 逐渐主流化

### 流传

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230303-1677806312850)

- unix 和 c语言 的
	- hello world 梗
		- 一直流传到今天

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685519483960)

- 除了 商业机构 当时还没有意识到 
	- 软件版权 可以盈利 之外
- 还有 一个重要的原因

### 教材

- 1978 年
	- `Kernighan`和`Ritchie` 出版了 这本书
		- 很薄
		- 轻松的语言风格

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230226-1677417377645)

- 因为 `c`的目的 就是让人 像玩一样编程
	- 而不是 记忆各种cpu汇编指令

### 成书

- 有了教材 就有 更多人学
	- 有更多人学 
		- 就有 更多人参与其中
			- 有更多人可以答疑
			- 有更好的案例

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210220-1613787632360)

- 需要实践就到unix上面
	- 直接写代码
	- 进行编译
- 就像《说文解字》、《约翰逊字典》一样
	- 成为 文化的 源头
	- 正反馈 逐渐成型

### 风借火势 火借风威

- 蓬勃发展 的 计算机技术
	- 使得 `c`语言
		- 成为 系统语言的老大
		- 是非常核心的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230601-1685627261156)

- 编程语言和系统环境
	- 互为因果
	- 互相成就
- 成为了默认的第一选择

### 基础

- `linux`内核 
	- 也是用纯c编的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230601-1685625534687)

- `python`的源代码 
	- 就是用纯c编的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230601-1685625579557)

### python

- 虽说 `python` 是用纯`c` 编写的
	- 不过`python`一旦出现之后 
		- 就可以 简化好多东西
	- 比如 我们的python3(游乐场)里面
		- 有 很多的函数和模块

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220917-1663383962521)

- 为什么 python能认识print？
	- 而不认识pront？

### 内置 函数

- 首先运行 python3(游乐场)
	- 在游乐场中 键入 `dir()`
	- 可以看到 游乐场的自带模块

- dir() 这个函数 
	- dir的意思是 
		- directory文档目录
	- 这里列出的是 
		- 已经导入模块的目录
- 调用 这个函数 
	- 可以知道 当前游乐场 
		- 载入了哪些模块

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230226-1677417942228)

- 比如 `__builtins__`这个模块
	- 这 `__builtins__`模块里面 
		- 又有些`什么`呢？

### dir()

- `dir(__builtins__)`
	- 注意builtins前后都是两个下划线
		- 两个下划线叫做dunder
		- `__builtins__` 念作 `dunder builtins`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220923-1663933416018)

- `__builtins__` 是 游乐场自带的
	- 这里面 有好多内置的函数
	- 包括
		- exit()
		- dir()
		- help()
		- print()
- 为什么print() 
	- 直接就能用？

### `__builtins__`

- 因为`print` 是
	- `__builtins__`模块中 
		- 内建的 函数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220303-1646289345700)

- 如果我 想要查询
	- print函数 更详细的信息 
		- 应该如何呢？

### help(print)

- 什么不会 就help什么
	- `help(print)`
	- 把函数名 作为参数 传进去

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220303-1646288588886)

- 类似的 还可以
	- help(quit)
	- help(help)
	- help(dir)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230226-1677418149974)

- 如果我想要查询`__builtins__`模块
	- 更详细的信息 应该如何呢？

### `help(__builtins__)`

- `help(__builtins__)`
	- 注意 内置模块builtins左右
		- 还是 有dunder(两个下划线)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211211-1639232283926)

- 可以查询到`__builtins__`模块的帮助文件
	- 返回的 这些函数和子模块
		- 都隶属于 `__builtins__` 这个模块
		- 属于内置的模块

### 导入 外部模块

- 导入命令 是
	- import
		- port是港口 
			- export 是出口 是导出
			- import 是进口 是导入
	- import 后面接空格
- 导入的模块 是
	- `__hello__`
		- `dunder hello`
	- 注意hello两边 
		- 都有dunder(两个下划线)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230226-1677418325769)

- 把`__hello__`模块 导入到游乐场
	- 可以 输出那句经典的话

### 变化

- 注意！
	- 导入 `__hello__`模块后
		- 游乐场中的模块 增加了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230226-1677418465935)

- 想要深入了解 `__hello__`
	- 应该怎么办呢？

### 什么不会就 help什么

```
help(__hello__)
```

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220923-1663933594048)

- 非常简单的 一个模块
	- 练手用的
- dunder这个单词怎么来的呢？

### dunder来历

- dunder 
	- Double UNDERscore

- 最初提议

> Dunder (Double UNDERscore) Alias

>> Mark Jackson was the first to suggest dunder as a speech shorthand for double underscores (__) in a reply to a query from Pat Notz. Ned Batchelder later stressed the need for a way of pronouncing __:

>> An awkward thing about programming in  Python : there are lots of double underscores. [snip] My problem with the double underscore is that it's hard to say. How do you pronounce __init__? "underscore underscore init underscore underscore"? "under under init under under"? Just plain "init" seems to leave out something important. I have a solution: double underscore should be pronounced "dunder". So __init__ is "dunder init dunder", or just "dunder init".


- 在发明 dunder 之前
	- `__init__` 要念作 double underscore init
		- 其中的double underscore 有17个字符
		- 发音是6声
	- 而dunder 只有6个字符
	- 发音是2声
- 从此 dunder 这个单词
	- 就被发明出来了

## 总结

- 商业机构 
	- 一开始没有意识到 
		- 可以对软件的版权收费
- 代码在最开始的时候
	- 就是开放免费的
- unix源代码大规模扩散、变种、传播
	- 经典的教材 也让 c语言 成为 编程入门经典
	- 其中的 `hello world梗` 一直用到今天

- 1979年
	- AT&T公司 开始声明unix的版权
- 但是 1979年 的 world
	- 已经不是 1969年 的 world 了
	- unix 和 c 已经流传开了
	- 并成为自由软件的基础
	- 到处都在学习 
		- `Hello world!`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220923-1663933793795)

- 等等！
	- 计算机里面 不都是二进制的 0和1 吗
	- `hello`中的 `字母h` 是从哪里来的呢？🤔
- 我们下次再说！👋
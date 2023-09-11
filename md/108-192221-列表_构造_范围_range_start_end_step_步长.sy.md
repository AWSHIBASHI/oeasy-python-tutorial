---
show: step
version: 1.0
enable_checker: true
---

# 列表 - 构造 range

## 回忆

- 上次了解了一些新的单词
	- list 列表
	- append 添加
	- remove 删除
	- clear 清空
	- function 函数 
	- method 方法
- 我们可以把一些以前的对象转化为列表吗？🤔

### 增加

- 我们可以用 append 的方法
- 为空列表增加列表项

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630143773543)

- 也可以直接得到

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630143782218)

- 如果我要一个从 1 到 100 的呢？

### range

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668494003084)

- range 是一个内置的函数
  - 可以完成类似的内容
  - help(range)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630122804929)

- range的构造函数有三个参数
	- start 
		- 开始值
		- 默认为0
	- stop 
		- 结束值
	- step 
		- 步长值
		- 可选
		- 默认为1

### 动手

- 如果只有一个参数
	- 参数为 结束值(stop)
	- 从 0 开始到 stop 结束
- 前闭后开[0,stop)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630123347238)

- 这是一个 `5个元素的列表`
	- 每一个元素都是这个列表的列表项	 

- range函数支持小数么？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630123889061)

- 小数不支持
	- 为什么小数类型不支持呢？

### 定义

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211126-1637933085359)

- 这是 range 类型的定义

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211126-1637933137676)

- 这是尝试小数作为参数的报错
	- 说明他确实只能支持整数参数
- 小数就不能放进列表里面吗？

### 小数

- 方法是有的
	- 但是得多尝试

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668494361872)

- 很多时候就得多动手
  - 有同学可能实验不成功
  - 这时候要特别注意变量名的问题

### 问题

- list也要注意重命名的问题

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630123389239)

- 本来 list 是一个 class
  - 但如果你把他赋值成了一个空列表
  - list 就变成了一个对象的名字
  - 一个变量 variable
  - 他就无法执行 list 类的构造函数了
- list 这个单词太常用了
  - 类似的还有
    - str
    - random
    - float
- 还记得吗？

### str

- python 的小写形式的类名
	- 非常好用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630124458530)


- 不像 java 
	- 使用 LinkedList 这样的类名
- 但是 python 
	- 很容易把 list、str 当成变量使用
	- 这种错误还真的不好找来源
- 所以变量名语义明确很重要

### start

- range 可以设置 start 的位置
- 比如从 100 开始

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630123654076)

- 如果前后颠倒会如何？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630123735935)

- 因为默认步长是 1
	- 无法通过默认步长从 5 到 1
- 返回结果是空列表

### step

- 步长 step

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668494554037)

- 还是前闭后开的范围
- 累加的值不是一了
- 而是 step
- 步长超大会如何？

### 步长超大

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630124075072)

- 前闭还是有的
	- 后面步子太大了
	- 一下子加到了 21
	- 超过了 10
- 所以这个容器中只有一个列表项
  - 1
- 数值可以是负数么？

### 负数

- step 可以是负数
	- 递减等差数列

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630124083181)


- 开始和结束都可以是负数
- 这东西可以有什么应用么？

### 月份

- 可以把等宽字体的月份转化为列表么？
	- 注意这个月份是一个 unicode 字符
	- 可以通过 chr(12992)得到

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211105-1636100827632)

- 貌似可以
	- 但需要把数字转化成 unicode 编码对应的字符
	- 可以直接使用字符构成数组吗？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669033640119)

- 执行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669033654556)

- 月份附近还有什么好玩的呢？

### 附近的等宽字体

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669033691446)

- 好玩的东西真不少

### 物理单位

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669034373945)

- unicode 是个宝藏

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669034384668)

### ㍰

- 有机会能都看一遍就好了！！

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669034275373)

### 日期

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669034356284)



### 日期

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669034460955)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669034484899)

- 话说回来
	- 除了range函数
- 字符串可以变成列表么？

### 总结

- 这次了解了列表生成
	- 列表作为一个序列容器
- 可以通过range函数返回值得到
- 数值序列 range
  - start、stop、step
  - 负数
  - 前闭后开
- 还有其他元素可以转化为列表吗？🤔
- 下次再说 👋

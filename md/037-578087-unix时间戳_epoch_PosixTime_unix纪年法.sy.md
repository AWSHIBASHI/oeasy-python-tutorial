---
show: step
version: 1.0
enable_checker: true
---

# 输出时间

## 回忆上次内容

- time 是一个 `module`
	- ascii_time = time.asctime( time.localtime( time.time()))
	- 这一长句 可以 变成一些短句

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220318-1647598144662)

- 这分步的过程 
	- 就像工厂车间
	- 按部就班
- <span style="color:red">time</span>.<span style="color:green">time()</span>到底返回值 是什么含义呢？🤔

### time.time()的含义

- 还是得 返回来 看 帮助文件

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210813-1628837778251)

- 返回的是 一个`浮点数`
	- 浮 是 `浮`动的浮
	- 点 是 小数`点`的点
	- 数 是 `数`字的数
- 是一个小数点浮动的数
	- 简称小数
- 小数的值是
	- 从 Epoch到当前的时间
	- 总共 过了 多少秒

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220318-1647599035064)

- 那什么 又是Epoch呢？

### Epoch

- 发音是[ˈepək]
- Epoch 的意思 是 纪年方法 或者说 年号
	- 公元2022年 是 耶稣诞辰 纪年法
	- 万历十五年 是 大明万历皇帝 纪年法
	- 令和四年 是 日本德仁天皇 纪年法

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220925-1664115667284)

- 那python中的 Epoch年号
	- 又是 谁的年号呢？

### unix纪年法

- unix纪年法(unix时间戳)
	- 从1970年1月1日开始的
		- 1970 年 1 月 1 日 00:00:00
	- 格林威治天文台标准时间(Greenwich Mean Time)
		- 也就是1970-01-01T00:00:00Z
- 每过1秒这个数字就加1
	- 每过半秒这个数字就加0.5
	- 所以Epoch也叫做
		- seconds since the Epoch

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230120-1674220670778)

- 为什么是1970-01-01呢？

### 时间原因
- 1969年
	- c和unix的编写工作
		- 开始实施的
- 1970年初
	- `Kenneth Thompson`和`Dennis Ritchie`
		- 一拍脑门定下来了 这个 起始时间点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230120-1674220984220)

- 1971年
	- 第一版unix的正式发布
- 上游影响下游
	- 关于秒数的数据类型time_t
		- 已然在后来成了 标准c库的一部分
		- 被广泛运用在 类unix(Unix-like)的 软件系统中
		- 比如眼前这个debian的变种
			- ubuntu

### 别名

- 所以 Epoch 也叫做
	- Unix Time
	- Posix Time
	- UNIX Epoch Time

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220127-1643289652075)

- time.time()得到的 是一个浮点数
	- 但是我们要的是
		- 年份
		- 月份
		- 日期
		- 时分秒
		- 这些具体的信息
- 从闰年到闰秒要考虑一对难题
	- 太麻烦了
		- 有什么办法么？

### time.localtime()

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210813-1628837796010)

- 把 time.time()得到的 浮点数
	- 交给 time.localtime处理
- time 还是包名
  - 这次的函数名变成了 localtime
	  - 输入是unix时间戳
	  - 输出本地时间元组
		- 年份
		- 月份
		- 日期
		- 时分秒
		- 这些具体的信息

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210813-1628838009501)

- 如果不给time.localtime函数任何参数
	- 又会如何呢？

### 缺省参数

- time.localtime默认使用
	- 当前时间 作为参数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230120-1674221260562)

-  time.time() 刚才研究过
	- time.time() 就是
		- 当前时间的unix时间戳

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220311-1646960906335)

- 这两个结果是一样的
- 我们再看看最外层的asc_time

### time.asctime()

- time.asctime 函数
	- 输入参数为
		- time.localtime()输出的时间元组
	- 输出为一个字符串

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210813-1628837821286)

- asctime函数 接收时间元组产生 ascii 字符串
	- ascii 就是 ascii编码
	- asctime 就是 用ascii方式显示的 time

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220930-1664546111567)

- asctime函数也有默认缺省参数么？

### asctime的默认缺省参数

- 查询文档

- 如果不给 asctime函数 任何参数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230120-1674221383388)

- asctime默认使用 time.localtime() 作为参数
	- time.localtime()
		- 就是 当前时间的 时间元组

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220311-1646961145760)

### 最后输出

- 一路使用默认参数
	- 把函数嵌套 大大简化了
- 把最后的结果 交给 print()
	- 最终还能 得到当前的时间！🤪

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220311-1646961221721)

### 步骤分拆

- 当前函数的返回值 是 下一个函数的参数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665477919057)

- 可以刷新时间来报时吗？

### 手动延迟

- 需要手动刷新 得到 `asc_time`
	- 然后 输出 `asc_time`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220317-1647499282065)

- 但我想 自动刷新时间
	- 先去编个 py程序

### 编写程序

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220930-1664546772299)

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220311-1646961360615)

- 每次执行python3 test.py
	- 就刷新
	- 刷新完全靠手😓

## 总结

- time 是一个 `module`
	- import time 可以做 和时间相关的 事情
	- time.time() 
		- 得到 当前时间戳
	- time.localtime() 
		- 得到 本地时间元组
		- local为本地
	- time.asctime() 
		- 得到 时间日期字符串
		- asc 为 ascii
- 简略的写法为
    - asc_time = time.asctime()
- 在`time.asctime()`中
	- time 是导入的module
	- asctime 是 time这个module里的 函数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230120-1674221782677)

- 现在 想要自动刷新时间
	- 怎么办？🤔
- 我们下次再说！👋
---
show: step
version: 1.0
enable_checker: true
---

# ASCII 码表

## 回忆上次内容

- 上次 我们了解了`ASCII`码表
	- `ASCII` 码表就是
		- `A`merican `S`tandard `C`ode for `I`nformation `I`nterchange
	- 美国信息交换标准代码
- ASCII 码表范围
  - `48-57` 这个范围是 `数字`
  - `65-90` 这个范围是 `大` 写字母
  - `97-122` 这个范围是 `小` 写字母

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220925-1664108814250)

- 知道了这个范围之后
	- 可以玩点什么吗？？🤔

### 引入新包

- 首先进入游乐场
	- from random import randint
		- 从random包中 导入randint函数 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230601-1685584098347)

- 然后查找一下
	- randint 的帮助

### randint

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230601-1685622777725)

- randint 可以得到 
	- 两数之间的随机整数值

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685526051096)

- randint使用效果
	- 确实可以是0
	- 也可以是1


### 编写程序

- 随机生成一个0或者1

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685526469966)

- 如何生成满屏幕的0或者1呢？

### 死循环 while

- 使用一个while True循环
	- while True后面有一个冒号
	- 冒号下面是循环体
	- 循环体需要缩进

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685526576335)

- 运行结果
- <kbd>ctrl</kbd>+<kbd>c</kbd>
	- 结束屏幕循环

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685526601403)

- 不断刷新01但是都在一列
	- 能否满屏刷0和1呢？


### 满屏01

- 可以像上次一样
	- 使用print函数中的 end参数
		- 设置输出末尾的字符串

```
from random import randint
while True:
    r = randint(0,1)
    print(r,end="")
```

- :w|!python3 %
	- 保存并运行

- 如果想要
	- 从0到9
	- 十个数字变化呢？

### 满屏数字

```
from random import randint
while True:
    r = randint(0,9)
    print(r,end="")
```

- 试试效果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230531-1685527048051)

- 如果想要满屏都是
	- abcd变化呢

### 满屏abcd

```
from random import randint
while True:
    r = randint(ord("a"),ord("d"))
    print(chr(r),end="")
```

- 这个代码可以优化吗？

### 优化代码

- ord("a") 和 ord("d")
	- 是固定的值
	- 不用每次都要计算

```
from random import randint
while True:
    r = randint(97,100)
    print(chr(r),end="")
```

- 可以得到所有小写字母的满屏吗？

### 满屏小写

```
from random import randint
while True:
    r = randint(97,122)
    print(chr(r),end="")
```

- 可以得到满屏大写字母吗？

### 满屏大写字母

```
from random import randint
while True:
    r = randint(65,90)
    print(chr(r),end="")
```

- 可以得到满屏中文汉字吗？

### 满屏中文


```
from random import randint
while True:
    r = randint(0x4e00,0x9fff)
    print(chr(r),end="")
```


### 满屏表情


```
from random import randint
while True:
    r = randint(0x1f600,0x1f620)
    print(chr(r),end="")
```

## 总结

- 这次比较好玩
	- 使用了随机这个包
	- 然后造成了满屏各种各样好玩的东西刷屏 
- 字符 
	- 在计算机当中 
		- 是用`二进制`形式存储的
- 每个字符
	- 都有自己的字符序号
	- 字符序号 是一个数字
	- 这个数字 用二进制形式 存储在计算机中
		- 可以看看 这个数字的 `二进制`形态 么？🤔
- 我们下次再说👋



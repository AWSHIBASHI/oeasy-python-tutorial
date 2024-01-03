---
show: step
version: 1.0
enable_checker: true
---

# 列表 - 系统命令行参数

## 回忆

- 上次了解了列表的下标索引
	- 可以用中括号 索引到 相应的元素
	- 还可以 替换相应的元素
	- 索引本质是 `__getitem()__` 方法
- 还可以用 index函数 找到某对象的位置
	- 如果 列表中 有多个指定元素
	- 可以通过 index函数的start和end参数 来指定位置
- 列表的索引 还有 什么实际的应用 吗？🤔

### 命令的参数

- ls命令可以查询文件夹下的内容
	- 默认参数是pwd
	- 当前文件夹


![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701597008874)

- ls后面加空格可以增加参数
	- ls命令 
		- 加上参数Desktop
	- 查询 当前用户的桌面上 有什么

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701597093601)

- ls命令 还可以
	- 加上参数golang
	- 查询golang文件夹下有什么

### ls命令配合多个参数

- ls命令 可以有多个参数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701597201851)

- python3命令 
	- 可以有参数吗？

### 参数

- python3命令 也可以有参数
	- 首先是要执行的py文件

```
python3 test.py
python3 main.py
```

- python3 是命令
	- 可以运行 test.py
	- 也可以运行 main.py
- test.py 或者 main.py 就是 
	- python3 命令的参数
- 那python3命令也可以有多个参数吗？

### 多个参数

```
python3 write.py oeasy.txt
```

- python3命令 有两个 参数
	- write.py
	- oeasy.txt

```
python3 shopping.py apple 3
```
- python3 命令有两个参数
	- 一个是水果名字
	- 另一个是水果数量

```
python3 shopping.py banana 5
```

- 参数也可以是不同的水果名字和数量
- 这种参数有什么意义吗？

### 参数的意义

- 比如 我要计算苹果或者香蕉总量的价格
	- 那原来 需要把 这个苹果和香蕉的数量
		- 在py文件中写死
	- 然后执行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701598564639)

- 但是 如果现在用我用的是参数
	- 可以在命令行上动态地将参数传递给py文件

```
python3 shopping.py apple 5
```

- 计算 5个苹果的价格

```
python3 shopping.py banana 6
```

- 或者计算6根香蕉的价格
- 那我在py文件中
	- 如何得到系统shell中 
	- 给python3的参数呢？

### 搜索

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644561931313)

### 搜索结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644561939723)

### python程序

```
import sys
print(sys.argv)
```

- 尝试运行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704109875117)

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704109908883)

- 输出了一个参数列表
	- 列表中只有一个列表项
	- 就是当前文件的文件名
- 如果给他更多参数呢？

### 更多参数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704110019316)

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704110032710)

- 可以查询帮助吗？

### 帮助文档

- 去游乐场

```
import sys
help(sys)
```

- 查询结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499652394)

- 只能看到argv
	- 是个sys模块中的列表
	- 列表项为一个空字符串
- 可以操控这个列表吗？

### python程序 

```
import sys
args = sys.argv
print("len", len(args))
print("type", type(args))
print(args)
```

- :w|!python3 % apple 5

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704110338209)

- 可以去掉shopping.py吗？

### python程序

```python
import sys
args = sys.argv
args.remove(args[0])
print("len", len(args))
print("type", type(args))
print(args)
```

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704110395075)

- 可以让这个程序根据外部的参数来运算吗？

### 修改程序

```
import sys
args = sys.argv
fruit = sys.argv[1]
amount = int(sys.argv[2])
if fruit == "apple":
    sum = amount * 1
    print("Sum of",amount, "apples are", sum)
elif fruit == "banana":
    sum = amount * 0.5
    print("Sum of",amount, "bananas are", sum)
else:
    print("There is no price of",fruit)
```

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704110830663)

- 使用参数 这一功能
	- 是什么时候开始有的呢？

### 溯源

- https://citeseerx.ist.psu.edu/doc/10.1.1.47.4180

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701598255583)

- 这一功能
	- 出现在1990年代初
	- 在Guido还在cwi做abc的时候就有了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701598413524)

- python最初的目的是
	- 成为c和shell之间的桥梁

### 总结

- 这次研究了python文件运行时的系统参数
	- sys.argv
	- 通过sys.argv就可以接收从命令行来的参数了
	- 可以通过索引来获得第n个参数
	- 这就是索引(index)的作用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20240101-1704111222477)

- 但是调用实际过程中
	- 参数可能给
	- 也可能没给
- 这可怎么办呢？?🤔
- 下次再说 👋

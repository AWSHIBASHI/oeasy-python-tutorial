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

- ls后面加空格可以增加参数

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701597008874)

- ls命令 可以
	- 加上参数Desktop
	- 查询当前用户的桌面上有什么

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701597093601)

- ls命令 还可以
	- 加上参数golang
	- 查询golang文件夹下有什么

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701597201851)

- ls命令 可以有多个参数
- python3命令 可以有参数吗？

### 参数

- python3命令的参数
	- 就是要执行的py文件

```
python3 test.py
python3 main.py
```

- 那python3命令也可以有多个参数吗？

```
python3 shopping.py apple banana
python3 write.py oeasy.txt
```

- 这种参数有什么意义吗？

### 参数的意义

- 比如我要搜索苹果和香蕉的热度
	- 那需要把这个苹果和香蕉关键词写进py文件
	- 然后执行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701598564639)

- 但是如果我是用参数
	- 可以在命令行上动态地将参数传递给py文件

```
python3 index.py 苹果
python3 index.py 香蕉
python3 index.py 橘子
python3 index.py 榴莲
```

- 那我在py文件中
	- 如何得到系统中给python3的参数呢？

### 搜索

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644561931313)

- 搜索结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644561939723)

### python程序

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644562417290)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644562428883)

- 可以查询帮助吗？

### 帮助文档

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499652394)

- 只能看到argv
	- 是个sys模块中的列表
	- 列表项为一个空字符串

### python程序 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668498684591)

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668498738472)

- 可以去掉a.py吗？

### python程序

```python
import sys
args = sys.argv
args.remove(args[0])
print("type", type(args))
print("len", len(args))
print(args)
```

- 这一功能是什么时候开始有的呢？

### 溯源

- https://citeseerx.ist.psu.edu/doc/10.1.1.47.4180

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701598255583)

- 这一功能
	- 出现在1990年代初
	- 在Guido还在cwi做abc的时候就有了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701598413524)

- python最初的目的是
	- 成为c和shell之间的桥梁
- 可以进行调试吗？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668498923721)

### 调试

- 定义三个端点
	- 1 号断点在 第2行
	- 2 号断点在 第4行
	- 3 号断点在 第6行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499036007)

- 其实我们调试的时候
- 断点其实 也是一个列表(list)
	- mutable sequence

### 删除断点

- clear命令	
	- 可以删除断点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499196984)

- clear a.py:1
	- 删除 a.py第1行 断点
- clear 3 
	- 删除 当前第3个 断点

### 清除断点

- clear
	- 清空 断点列表

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499290442)

### 重设断点

- 把246行断点删除后
- 在135行上设置断点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499328103)

- 走流程

### continue

- c 就是continue 继续走到下一个断点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499399229)

- 我们退出了去总结吧

### 总结

- 这次研究了python文件运行时的系统参数
	- sys.argv
	- 通过sys.argv就可以接收从命令行来的参数了
	- 可以通过索引来获得第n个参数
	- 这就是索引(index)的作用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221122-1669084502707)

- 列表还有什么方法吗?🤔
- 下次再说 👋

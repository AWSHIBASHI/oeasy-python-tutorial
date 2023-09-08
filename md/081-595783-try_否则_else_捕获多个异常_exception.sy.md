---
show: step
version: 1.0
enable_checker: true
---

# try的完全体

## 回忆上次内容

- 上次我们细化了主控程序(main.py)
	- 将程序分成三个具体步骤

| get_fruits | process | output|
| --- | --- | --- |
| 输入水果数量| 对水果数量求和 | 输出最终结果 |

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230710-1688949895944)

- 使用了 try 结构
  - try
  - except
  - 发现异常就报错
- 输入部分 的 数据类型错误
  - 应该在 输入部分 来报错
- 具体怎么报呢？🤔

### 完善输入

- 输入的时候
	- 应该包括
		- 对于输入内容的验证
	- 于是 再修改代码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230611-1686492217408)

- 输入代码 分成了
	- 输入 a 
	- 输入 b 

### 运行结果

- 如果 输入错误数据
	- 会在get_fruits.py中报错

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230611-1686492047662)

- 如果 输入正确
	- 没有输出 确认信息

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221030-1667100980579)

### 继续修改

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220520-1653054458320)

- 测试通过

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230614-1686750899132)

- 这里面有个 else
	- 应该如何理解呢？

### 查询帮助

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211105-1636119107156)

- 在游乐场帮助 里面有关于
	- try 的比较明确的介绍

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230430-1682827786681)

### 举个例子

```
try:
    i = int("abc")
except ValueError:
    print(ValueError)
else:
    print("Nothing Wrong")
```

- 这里的参数"abc"
	- 是无法转化为整型数字的
		- 会抛出ValueError
	- 进入except子句
		- 执行输出
	- 然后跳过else子句
- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230530-1685456712271)

### 例子更新

```
try:
    i = int("123")
except ValueError:
    print(ValueError)
else:
    print("Nothing Wrong")
```

- 这里的参数"abc"
	- 是可以转化为整型数字的
- 整个try子句都执行完毕
	- 没有抛出任何的Error
	- 跳过except子句
- 直接进入else子句
	- 执行输出
		- Nothing Wrong！
- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230530-1685456799474)

- else的意思是否则
	- 就是没有发现异常时才执行的

### else

- else 是一个可选(optional)子句
	- 如果try中 发现了指定异常
		- 就从try中 发现错误的位置 跳出来
		- 执行except部分
		- 不执行else部分
	- 如果try中 没有发现 指定的异常 
		- 在执行完try中的内容 之后
		- 不执行 except 部分
		- 只运行 else 部分

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220402-1648895345557)

- 可以捕获不同类型的error吗？

### 不同类型的error

```
try:
    i = int("123")
    j = i / 0
except ValueError:
    print(ValueError)
except NameError:
    print(NameError)
except Exception as e:
    print(e)
else:
    print("Nothing Wrong")
```

- 如果不try
	- 会抛出ZeroDivisionError

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230624-1687613136927)

- 捕获到不同类型的错误
	- 会进入不同的except子句
	- 会有不同的错误处理方式
- 尝试捕获 前两种类型的Error
	- ValueError
	- NameError
	- 都没有被捕获
- 于是进入第三个捕获流程
	- except Excetion as e
	- 然后输出e的字符串形式

### 一网不捞鱼

- 一网不捞鱼
- 二网不捞鱼
- 三网捞个小尾巴尾巴尾巴尾巴尾巴尾巴……鱼

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230729-1690633742375)

- 由于第三网 捕获到了异常
	- 跳过else子句
- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230530-1685457025401)

- 如果ValueError被捕获
	- 还会进入第三个捕获流程吗？

### 捕获异常

```
try:
    i = int("abc")
    j = i / 0
except ValueError:
    print("1======",ValueError)
except NameError:
    print(NameError)
except Exception as e:
    print("2=======",e)
else:
    print("Nothing Wrong")
```

- 在运行过程中出现了ValueError
	- 在第一个尝试捕获异常的地方捕获到了异常
		- 进入except ValueError子句
		- 完成处理过程
			- 输出"1===========",ValueError
	- 跳过其他尝试捕获异常的子句
	- 跳过else子句
- 执行完毕

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230624-1687613834317)

- try 语句当中 
	- 除了 else 之外
	- 还有 finally

## 总结

- 我们了解了 try 的完全体
  - try
	- 尝试运行
  - except
	- 发现异常时运行的代码块
  - else
	- 没有发现异常时运行的代码块
- 注意！
	- 都要有英文半角的冒号
	- 都要通过 4 个字符的缩进控制范围

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230906-1693965309852)

- 最后还有个finally
	- 这个finally如何理解呢？
- 我们下次再说！👋

---
show: step
version: 1.0
enable_checker: true
---

# 列表 - 可迭代对象 - iterable

## 回忆

- 上次了解了列表生成
	- 列表作为一个序列容器
- 可以通过range函数返回值得到
- 数值序列 range
  - start、stop、step
  - 负数
  - 前闭后开

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231125-1700915693785)

- 还有其他元素可以转化为列表吗？🤔


### 字符串

- 试试

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630124739385)

- 直接把字符串当做 list 的参数就可以了
- 每个字符都是一个列表项
- 中文也是一样么？

### 字符串

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630126033608)

- 太方便了
- 那能把 list 转回 str 么？

### 尝试

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630125028365)

- 看起来不行
	- 不过没事
	- 有什么办法吗？

### eval

- eval 
	- 可以把字符串
	- 变成相应的数据类型

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221121-1669034685309)

- 这次把字符串引起的列表
	- 变成了列表
- 如何理解eval

### eval

- 将source衡量出来
	- evaluate

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231202-1701526257688)

- 可以根据本地和全局的变量
	- 进行衡量

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231202-1701526344554)

- 能把字符串切分么？

### 切分

- 让字符串
	- 调用自身的 split 方法
	- 返回的就是一个 list
	- 有点像 readlines
		- 通过`\n`把读到的东西
	- 切分成列表

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210828-1630125084974)


### 文件

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668478997139)

- 运行结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668479007016)

- 为什么文件f、字符串、range函数返回的结果对象
	- 都可以转化为列表呢？

### 查看说明文档

- list类构造函数的参数
	- 应该是一个iterable的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668495496298)

- 什么是iterable呢？

### iterate

- iterate
	- 迭代

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701570452880)

- 来自于
	- 反复说某话
	- 反复做某事

### iterative

- iterative
	- 迭代的

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701569904613)

### iteration

- iteration
	- 循环

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701572317259)

- 年复一年

### iterable

- iterable
	- 就是可以循环遍历的东西
	- 叫做可迭代对象
	- iterable object

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20231203-1701570679803)

- 文件对象里面
	- 有很多行
- 字符串对象里面有
	- 很多字符
- 字符串切分对象里面
	- 有很多字符串
- range函数返回
	- 很多数字

### 总结

- 这次了解了通过可迭代对象生成列表
- 字符串序列 s
  - 可以把每个字符转化为列表项
  - split 切分出 若干可迭代字符串
  - 作为 列表项
- 可迭代对象还包括
	- 文件对象
	- 字符串对象
	- range函数返回结果对象
- 如何选择每一个列表项呢？🤔
- 下次再说 👋
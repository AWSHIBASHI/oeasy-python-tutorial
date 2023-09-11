---
show: step
version: 1.0
enable_checker: true
---

# 列表 - 类型

## 回忆

- 上次了解了 
	- f.readlines()
	- list(f)
- 读文件的时候
  - readlines()按照行读出来
  - 生成一个列表 list
  - 列表 list 是一个容器

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220830-1661868383232)

- 但是这个列表 list 到底怎么用？🤔
- 还是在游乐场里面观察

### 空列表

- 观察定义

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230321-1679391118484)

- 如果没有给出参数
	- 那么这就是一个空列表

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230321-1679391155427)

- 如果我直接写
	- l = []
- 会如何呢？ 

### 直接赋值

- []好像也可以直接得到一个空列表
	- 并对l进行赋值

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668481796520)

- 那这个l可以有什么样的函数呢？

### l.append

- l.之后摁下<kbd>tab</kbd>

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668481897683)

- 第一个就是append
- 我们来试试

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668481961115)

- 作用是在列表尾部追加元素
- 如何理解append呢？

### append 词源

- append 来自于 
	- pend 悬挂

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230128-1674866570655)

- append 附加
	- 这里指 在尾部 
		- 附加 一个元素
- 可以找到帮助手册吗？

### 帮助手册

- help(list) 或者 help([])
	- 在帮助中查找append
	- /append

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210827-1630073691369)


- append 追加在文件尾部追加

- 后面这个clear怎么用呢？

### clear

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668483359867)

- 这和
	- l = []
	- 有区别吗？

### 区别

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668483455022)

- 这应该如何理解呢？

### 将空列表赋给l2

- 通过id函数得到列表的地址

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668483887905)


- 将空列表赋给l2
	- 让l2指向一个空列表的地址
	- 是一个新地址

### 将l2清空

- l2 依然指向l1的地址
	- l2 清空就是l1清空

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668484020777)

- 最终这两个列表
	- 地址没变
	- 被清空
- 空列表地址一定相等吗？

### 建立空列表

- 我建立了两个空列表

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220728-1658977621704)

- 他们虽然都是空列表
	- 但是是指向不同地址空间的两个空列表
- 如果我想让两个列表控件指向同一个地址呢？

### 赋值

- b = a = []这就话相当于
	1. a = []
	2. b = a

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220728-1658977893489)

- 当再次给a进行赋值的时候
	- a指向了一个新的地址
	- b还指向原来的地址


### 总结

- 这次了解了 list 列表的操作
  - 追加列表项 append
  - 清空列表 clear
- 列表可以增加和清空了
- 我可以删除指定元素吗？🤔
- 下次再说 👋

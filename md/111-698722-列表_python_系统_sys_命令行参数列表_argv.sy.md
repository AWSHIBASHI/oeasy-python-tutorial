---
show: step
version: 1.0
enable_checker: true
---

# 列表 - 系统命令行参数

## 回忆

- 上次了解了列表的索引
	- 可以用中括号加索引找到相应的元素
	- 还可以替换相应的元素
	- 索引本质是 `__getitem()__` 方法
- 还可以用 index函数 找到某对象的位置
	- 如果列表中还有多个指定元素
	- 可以通过index函数中的start和end参数来指定位置
- 列表的索引有什么实际的应用吗？🤔

### 参数

- 我想要这样调用shopping.py
	- python3 shopping.py apple banana
	- python3 write.py oeasy.txt
- 那我如何得到系统中给python程序的参数呢？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644561931313)

### 搜索结果

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
print(sys.argv)
sys.argv.remove("a.py")
print("type",type(sys))
print("len",len(sys))
print(sys.argv)
```

- 可以进行调试吗？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668498923721)

### 调试

- 定义三个端点
	- 1 号断点在 第2行
	- 2 号断点在 第4行
	- 3 号断点在 第6行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499036007)

- 其实我们调试的时候
- 断点也是一个列表

### 删除断点

- clear可以删除断点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499196984)


- clear a.py:1
	- 删除a.py第1行断点
- clear 3 
	- 删除当前第3个断点
- clear
	- 清空一切断点

### 清除断点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499290442)

### 重设断点

- 把246行断点删除后
- 在135行上设置断点

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499328103)

- 走流程

### continue

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221115-1668499399229)

- c 就是continue 继续走到下一个断点
- 我们退出了去总结吧

### 总结
- 这次研究了python文件运行时的系统参数
	- sys.argv
	- 通过sys.argv就可以接收从命令行来的参数了
	- 可以通过索引来获得第n个参数
	- 这就是索引(index)的作用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221122-1669084502707)

- 列表的索引还有什么用吗?🤔
- 下次再说 👋

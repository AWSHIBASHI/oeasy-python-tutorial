---
show: step
version: 1.0
enable_checker: true
---

# 牛说(cowsay)

## 回忆上次内容

- 上次我们
	- diy了 自己的小动物
	- 还可以 让小动物 变色、报时
	- 还可以 说些话
	- 这很亚文化
		- 很酷炫的亚文化
		- 不是吗？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230128-1674912364746)

- 但是这个小动物
	- 可以放到cowsay里面吗？

### 结合 cowsay🐄

- 先找到位置

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496255713)

- 复制小动物文件

### 复制动物

```shell
# 在确认 cowsay 已经安装的情况下
cd /usr/share/cowsay/cows
# 复制一个 cow 文件
sudo cp apt.cow oeasy.cow
#使用编辑器编辑
sudo vi oeasy.cow ~/Code/ooo.txt
```

- 进入目录 
	- 复制出一个 oeasy.cow
	- 给oeasy.cow 添加任意用户的 写权限
	- 然后同时编辑
		- 小动物 ooo.txt
		- oeasy.cow

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230128-1674912817144)

### 修改字符画

- 新的动物名 cat 可以用了
	- 图案 还是 原来的字符画

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496534047)

- 怎么使用diy的字符画呢？

### 替换字符画

- 在合适位置 <kbd>d</kbd><kbd>G</kbd>
	- 从当前位置 开始 
		- 将下面的 字符画删除
- :r ~/Code/xxx.txt
	- 读取(`r`ead) 自己diy的 小动物字符画
		- 并粘贴到 当前缓存中去

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/ooo.png)

- 话语的斜线 有点问题

### 修改

- 修改文字泡泡线

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496875972)

- 注意!
	- 前5行和最后一行
	- 都是有意义的
	- 是cowsay的结构

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665496842742)

- 是不能丢的东西

### 不能丢的东西

- 相关头尾不能丢
	- 还有中间的有些替换字符也要注意
	- 才能保证.cow文件可用

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211008-1633663823279)

- 如果要说的话比较多
	- 就需要角色要变小一点

### 角色大小选择

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205472280)

- 可以设置分辨率为四分之一大小

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20211118-1637205511652)

### 配合报时

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497615102)

- 使用新动物

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497623840)

### 渐变色

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497647880)

### 大功告成！

- 可以再配合一些亚文化的话语
	- 做成报时动画😁

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665497879185)

- 将我们diy的好东西
	- 录制成视频
	- 发个动态炫一下
- 玩的就是 asciiart!!!

## 总结

- 这次我们
	- diy了 自己的小动物
	- 可以 让小动物 变色、报时
	- 还发了 动态
- 回忆一下 
	- 最开始 研究报时 的 时候
	- 回到 本行行头 的 方法
    - print("\r"+ascii_time)
    - `\r` 与 `\n` 不同
- 从含义上 来看
    - `\n` - LF - LineFeed - 换行
    - `\r` - CR - CarriageReturn - 回车
- 换行 和 回车
	- 具体 有什么不同吗？🤔
- 我们下次再说！👋

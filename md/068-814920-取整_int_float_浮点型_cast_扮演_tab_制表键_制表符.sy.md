---
show: step
version: 1.0
enable_checker: true
---

# 转化为10进制

## 回忆上次内容

- 上次 把其他进制
	- 转化回 `十进制`
		- 用的是 int 函数
- int 来自于 integer
	- 同源词 还有
		- integrate
		- entire
		- 意思都是`完整`的
- `完整`的 和 `零散`的
	- 相对
- 可以把 `零散`的小数
	- 转化为 `完整`的整数吗？🤔

### 取整

- 可以 把一个浮点型的小数 取整

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672111185944)

- 取整 可能会造成
	- 运算结果的 不同

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672111302037)

- 3.3 是 一个浮点型 的 小数
	- 现在 把他当做 一个`整数`
- 这个过程叫做cast

### cast

- cast原意是投掷
	- cast a spell 施法 投一个咒语 
	- cast a vote 投票
	- cast 铸造 把铁水投入到磨具中
		- plaster cast 铸造石膏

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672112432439)

### 投影
- cast a shadow 投上一层阴影

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672112012814)

- 扮演成
	- 手经过 cast 成为鹿
	- 人扮演成其他的角色


### 演员表

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230113-1673613420531)

- 一部戏的全体演员

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672111375200)

- 数据类型的转化也是一种扮演

### cast

- 我们 让`3.3`
	- 扮演(cast)了 
		- `3`这样一个角色

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672112698082)

- 甚至可以让`π`
	- 扮演 
		- `3`这个角色

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672112779431)

### 字符串

- 还可以 让字符串`"3"`
	- 扮演 整数`3` 这个角色

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672112940412)

- 但无法让
	 - 字符串"3.3"
		- 扮演 整数`3` 这个角色

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221227-1672112912170)

- 居然能 让`3.9`
	- 扮演  整数`3` 这个角色？

### 查看文档

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230113-1673616653888)

- 把 浮点型(float)的 3.9
	- 小数部分 截掉(truncates)
	- 转化为 整型(int)的 3

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230113-1673616785675)

- cast
	- 将 某种数据类型的表达式 
		- 显式转换 为 另一种数据类型
- 可以将<kbd>tab</kbd>键 转化为整数吗？

### tab 键

- <kbd>tab</kbd> 是一个按键
	- 试着 求出<kbd>tab</kbd>键对应 的 ascii序号
	- 也就是`\t` 对应的数值

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210226-1614310534033)

- 求出这个数值对应的 
	- 2 进制
	- 8 进制
	- 10 进制
	- 16 进制
- 然后尝试
	- 用数值的方式输出<kbd>tab</kbd>
- 不要翻页

### 转化与输出

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221015-1665798025707)

- 可以找到 
	- <kbd>tab</kbd>序号的 各种形式
- 然后 输出

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220918-1663509882746)

- 可以来 一个循环吗？
- 就是 
	- 一顿操作猛如虎
	- 仔细一看原地杵 
		- 那种

### 绕回来

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221015-1665798175763)

- 可以 反过来 
	- 绕一圈 吗？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221015-1665798275508)

### 反向绕

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230113-1673618052887)

- 可以 把二进制形式转化为十六进制 吗？

### 转化

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230113-1673618115100)

- 东西 还是那个东西
	- 状态 可以随意流转的
	- 万变不离其宗

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230113-1673618180533)

- 转化过程中 始终要注意类型
	- 如果 不确定类型的话
		- 用type函数 确认一下

## 总结

- 这次在各种类型间不断转化
	- int 整型数字
	- float 浮点型数字
	- str 字符串
- 最后温习了 转义字符`\t` 类似的还有
	-  `\n`
	-  `\r`
- 还有 通过数字 得到ascii字符
	- `\ooo`
    - `\xhh`
- 如果 
	- 我想`只`输出 `\` 这个字符 
		- 可以吗？
	- `\` 叫什么字符来着？🤔
- 我们下次再说！👋

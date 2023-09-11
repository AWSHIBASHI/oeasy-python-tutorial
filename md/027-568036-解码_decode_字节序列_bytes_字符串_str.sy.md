---
show: step
version: 1.0
enable_checker: true
---

# 解码 decode

## 回忆上次内容

- code就是码
	- 最早也指电报码
	- 后来有各种码
		- 密码
		- 砝码
		- 条码
	- 都指的都是 
		- 把各种事物编个号
- encode就是编码
	- 编码就是给事物编个号

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230115-1673793285948)

- 给事物编号之后
	- 放到计算机的字节中
- 计算机编好码的字节
	- 如何找回原来对应的事物呢？🤔

### 解码

- 解铃换需系铃人
	- 解码是编码的逆运算

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220911-1662869944064)

- 上次把白菜编上号
	- 这次扫到码 
	- 就知道这个码对应大白菜
		- 并知道价格
- 这就是解码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220212-1644629532870)

- 这解码 用英文怎么说呢？

### 解码(decode)

- de 的意思是反向操作
	- defuse 解除保险炸弹引信
	- decolor 漂白
	- defame 中伤
	- destruct 破坏
	- demodulation 解调制

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230115-1673794052176)

- decode 就是和 encode 相反的
	- 把代码 还原为一个东西 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220911-1662870240665)

- 计算机也可以编码解码
	- 我们的大脑在编码解码

- 试试用 python 解码

### 编解码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210905-1630840207588)

- str(字符串)`'a'` encode(编码)之后 
	- 为 `b'\x61'`
- b'\x61' 是什么类型来着

### bytes类型

- bytes类型
	- 对应着 字节序列

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220212-1644629638535)

- bytes(字节序列) `b'\x61'` decode(解码)之后
	- 得到str(字符串)`'a'`

- 编码(encode) 和解码(decode) 互为逆运算
- 很像
	- 字符(chr)和 序号(ord)
- 一阴一阳之谓道

### 编码解码

- 可以先编码再解码
	- 也可以先解码再编码
- 绕来绕去
	- 也没做神马😁

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210905-1630840380086)

- 掌握这个基础是最起码
	- 基本功要练得硬桥硬马
- 实战方能稳扎稳打
	- 否则以后各种乱码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210917-1631860339560)

- 字节编码其实已经形成一个闭环

### 闭环

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221021-1666342050363)

- 字符的这三个东西形成了一个闭环
	- 字符本身
	- 字符序号数字
	- 字符的字节状态

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221021-1666342689996)

- 已经 可以将一个字节解码为字符 了
- 可以将 多个字节 解码为 字符 吗？

### 解码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220924-1664024847442)

```
help(bytes.decode)
```

- 查询帮助手册

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220924-1664024944238)

- 解码
	- 就是把计算机中的字节
		- 解回来 成为生活中的东西
- 解码 解得是
	- 已经 编好的码

### 图像编码

- 图像、声音、影片
	- 计算机中的一切都需要编码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220918-1663504473731)

- 编码之后才能存储、传输
	- 还原的时候需要解码
- 换一种 编码方式 再 编码
	- 叫做转码

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220918-1663504674762)

- 回到 字符编码
	- ascii编码为什么这样编呢？
- 是乱编的吗？

### 大小字母差值

- 那么大小写字母之间有什么关系呢
	- `0x61-0x7A`这个范围是小写字母
	- `0x41-0x5A`这个范围是大写字母

```python
#输出a的ASCII码
ord("a")
#输出A的ASCII码
ord("A")
#输出大小写之差
ord("a")-ord("A")
#差值的16进制形式
hex(ord("a")-ord("A"))
#差值的2进制形式
bin(ord("a")-ord("A"))
```

- 运行效果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230329-1680095205202)

- 大写字母和小写字母相差(`32`)<sub>`10进制`</sub>

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230329-1680095222435)

### ascii编码 

- 为什么不多不少
	- 就差 (`32`)<sub>`10进制`</sub> 呢？
	- 怎么那么寸呢？🤔

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230329-1680095296782/wm)


- 先去总结一下

### 总结

- decode
	- 就是解码
- 解码和编码互为因果
	- encode 编码
	- decode 解码
	- 互为`逆`过程

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221005-1664938405378)

- 大小写字母间
	- 序号全都相差(`32`)<sub>`10进制`</sub>
	- 中间 还穿插着符号
	- 为什么不都连在一起呢？🤔
- 我们下次再说👋🏻
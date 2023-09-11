---
show: step
version: 1.0
enable_checker: true
---

# 变量定义

## 回忆上次内容

- 变量相加
	- 整型数字变量可以相加
	- 字符串变量也可以相加
- 但是
  - 字符串和整型数字
  - 整型数字和字符串
  - 不能相加
- 怎么办？
	- 转格式
  - int("1")
  - str(2)
- 可是是如果输入的数量是字符串"abc"
  - int("abc")会发生什么？
  - 怎么办？😱

### 先试试看

- 虽然我有了心理准备

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667043384976)

- 但是 python 显然还没有准备好
	- 要让 python 知道什么时候会出错

### 简化问题

- python3 的意思是 不知道怎么把 `a` 转化为十进制数
  - 不但 python3 没有办法转化
  - 我也没有思路

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210815-1629030007773)

- 有的时候数字中确实可以有 `a` 的
  - 比如 `0xa` 这种形式
  - 这 `0xabc` 是可以转化为数字的
  - 而 `abc` 是不能转化的
- 如何进行区分呢 

### 思路

- 尝试转化的工作出现在倒数第二行
	- total = int(a) + int(b)
- 我们需要的是试着运行这一行

```bash
#!/usr/bin/python3
a = input("How many apples do you have: ")
print("You have got " + a + " apples!")
b = input("How many banana do you have: ")
print("You have got " + b + " bananas!")
total = int(a) + int(b)
print("You have got " + str(total) + " fruits in all!")
```


- 如果遇到了不能转化的情况
	- 既然给了用户输入的权利
	- 就要处理用户输错的可能性
	- 如果真错了
		- 给用户一个明确的能理解的并报错输出
- 怎么才能让 python3 试着运行呢？

### 搜索 try

- 搜索一下 python3 + try

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210815-1629030647815)

### try

- try 就是 试着来
	- 把需要试着来的代码部分放到 try 里面
![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210815-1629030666789)

- 试着成功了
	- 就继续运行try里面的代码直到完成
- 试着失败了
	- 就跳转到except部分向下执行
	- 就是处理异常情况

### 试着来

- 下面的源代码
	- 可以直接复制
	- 系统会将两个反斜杠`\\`
		- 转义成一个反斜杠`\`

```python
#!/usr/bin/python
a = input("How many apples do you got?\\n")
print("You got " + a + " apples!")
b = input("How many bananas do you got?\\n")
print("You got " + b + " bananas!")
try:
    total = int(a) + int(b)
except:
    print("\\33[41m[error]\\33[0m -- input should be numbers!")
print("You got " + str(total) + " fruits!")
```


- 注意
  - 冒号
	- 冒号要紧跟着 try、except
	- 冒号是英文半角的
  - 缩进
	- 待尝试的内容需要缩进 4 个字符
	- total = int(a) + int(b)
	- 所有需要try的内容都要缩进进去
	- 就像while True中需要循环的循环体一样
    - 缩进距离不多不少 
    	- 必须4个
- 可以用`gg=G`自动调整缩进

### 尝试运行

- 运行失败了
	- 不过失败的错误提示系统报的错误
	- 而不是我自定义的报错信息
	- "total"变量没有被定义

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210815-1629031287390)

- 原来想的是试着执行这句
	- total = int(a) + int(b)
- 可是这句里面里面
	- 不但进行类型转化
	- 还声明了一个变量 total
	- 这个变量 total 后面还要被引用
	- 后面引用不到 所以报错了
- try没try成功
	- 就没办法正确声明 total
	- 后面调用total的时候
	- 系统找不到total
	- 所以报错了
- 怎么办？

### 再次修正

- 都放 try 里面

```python
#!/usr/bin/python
a = input("How many apples do you got?\\n")
print("You got " + a + " apples!")
b = input("How many bananas do you got?\\n")
print("You got " + b + " bananas!")
try:
    total = int(a) + int(b)
    print("You got " + str(total) + " fruits!")
except:
    print("\\33[41m[error]\\33[0m -- input should be numbers!")
```

### 尝试

- 试试行不行

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667043876126)

- 这次终于成功地报错了！
	- 或者说我接管了相关的报错信息
	- 对于这类错有了自己的处理
	- 这就是捕获了异常
	- 并且处理了异常
- 红颜色的 error 好扎眼
	- 我把他瞒下来
	- 不报错可以么？

### 不报错

```python
#!/usr/bin/python
a = input("How many apples do you got?\\n")
print("You got " + a + " apples!")
b = input("How many bananas do you got?\\n")
print("You got " + b + " bananas!")
try:
    total = int(a) + int(b)
    print("You got " + str(total) + " fruits!")
except:
    pass
```

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667043943445)

- <font style="color:red;font-size:48px;">这不行!!!😡</font>
	- 异常错误不处理不行
	- 要明确得处理
	- 要明确的报错
- 知道哪里错了
	- 才好修改
- 如果假装没犯错
	- 就会完全没有处理线索
	- 程序大了绝对让人彻底崩溃

### 对应禅语

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220328-1648418375957)

- 错误不应被悄悄传递
	- 除非你确定需要这样做
	- 精准地捕获异常
	- 不写 except:pass 风格的代码
	- 那什么是 except:pass 风格的代码呢？

### 异常飘过

- 就是那种知错不报错的方式
	- 虽然接收到了错误except
	- 但是轻轻飘过pass

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667043987282)

- 上面这是错的！
	- 这是最要命的
	- 让人没有追踪trace的方式
	- 无法调试debug!
	- 无语问苍天😭！
- 我不但要有自己的报错
- 还要保留系统的报错
- 有可能吗？

### 保留报错

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667047409821)

- 最终结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667047424252)

- 可以让报错详细一些吗？
- 比如文件、行号

### 保留报错细节

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667047853333)

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221029-1667047872197)

## 总结

- 这次学习了
  - try
  - except
- 注意要点
  - 半角冒号
  - 缩进
  - 输出错误信息
- 有错就报告
  - 不要隐瞒
  - 否则找不到出错位置
  - 还可以把traceback里面的信息原样输出
- 但是代码量好多啊
  - 10多 行了 🤯
  - 可以把他输入部分和输出部分么？🤔
- 我们下次再说！👋

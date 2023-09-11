---
show: step
version: 1.0
enable_checker: true
---

# 牛说(cowsay)

## 回忆上次内容

- 上次 我们研究了 shell脚本的编程
- 并且 在shell中 实现了
	- 循环 语句
	- 延迟 命令
	- 清屏 命令
	- python命令
	- figlet命令

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20220211-1644585817010)

- 还能 整点`什么` 呢？🤔

### cowsay

- 还想要 让小动物报时！
- 首先要安装 cowsay

```bash
sudo apt install cowsay
```

- 装完 之后
	- cow 就可以 say 了吗？

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210306-1614993917284)

- 怎么 `say`呢？

### 利用 管道

- 利用 管道(pipe)来say

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210306-1614993957714)

- 如何 与报时函数 `整合`呢？

### 整合

```
#!usr/bin/python3
import time
print(time.asctime())
```
- 一步一步 来

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665552184723)

- figlet的结果 再通过管道 送cowsay

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221012-1665552226279)


### 管道原理

![Image text](https://labfile.oss.aliyuncs.com/courses/2712/pipe.png)

- 然后 尝试`循环`起来

### 把 cowsay 整合进来

- 把 figlet的输出结果
	- 再送到 `cowsay -f moose -n`
- 其实 就是 
	- 一步步 通过管道流淌的 过程

```bash
for a in {1..10}
do
	clear
	python3 show_time.py | figlet ｜cowsay -f moose -n
	sleep 1s
done
```

- 看起来 有点复杂
	- -f moose 
		- 使用 驼鹿
	- -n 
		- 保留 转义字符`\n`
		- 避免 屏幕混乱

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210306-1614994076733)

- 这确实 有点`亚`文化😓
- 可以来点 更`亚`的文化 吗？😄

### 彩色效果

```bash
#安装彩色程序
sudo apt install lolcat
#实验
echo oeasy | lolcat
```

- 这样 就可以
	- 输出 `彩`色效果 了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665485149853)

- 这个 可以！
	- 真的 很`亚` ☺
- 可以 再把 报时
	- 整合 进来 吗？

### 整合 报时

- 有时 会因为 文字长度问题
	- 显得 很乱

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210812-1628752388506)

- 想要 把时间
	- 简化为 时分秒

### 整合 时间

- 整合 进入原来的loop.sh
- 循环中
	- 清屏 后
	- 输出 时间
	- 再 延时

```
for a in {1..100}
do
    clear
    python3 sleep.py | figlet | cowsay -f moose -n | lolcat
    sleep 1s
done
```

- 输出 时间
	- 文本 长度太长
- 想要
	- 不输出 年月日
	- `只`输出 时分秒


### 搜索

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210306-1614994224934)

- 这就得 修改 
	- 最初生成时间的 源头
	- show_time.py 文件
- 怎么修改呢？

## 总结

- 狂飙了一路
  - 从 用shell `直接`执行 python程序
  - 到 用shell `循环`执行 python程序
- 循环体中
  - 把 `python`的 输出结果 
	- 用管道 交给了 `figlet` 
  - 把 `figlet`的 输出结果 
	- 用管道 交给了 `cowsay`
  - 把 `cowsay`的 输出结果
	- 用管道 交给了 `lolcat`
- 这一路真的好远啊!
	- python3 是脚本解释器
	- shell 也是脚本解释器
- 现在的问题是
	- 日期时间 输出格式 非常复杂

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230128-1674902945544)


- 想要只输出时间 
	- 再送 figlet 和 cowsay 
	- 可以吗？🤔
- 我们下次再说程序！👋

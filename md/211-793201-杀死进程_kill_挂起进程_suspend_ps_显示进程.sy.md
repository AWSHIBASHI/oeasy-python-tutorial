---
show: step
version: 1.0
enable_checker: true
---

# 查看进程

## 回忆上次内容


- 进程前后台 切换
	- <kbd>ctrl</kbd> + <kbd>z</kbd> 把当前进程切换到后台并暂停
	- `fg` 把进程 再`切`回前台
	- `bg` 让进程 在后台 持续运行
- 但问题就是 根本停不下来！
- process 真的就 
	- 不断pro - pro - pro
	- 或者说foreword - foreword - foreword 跑起来了

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221221-1671631515885)

- 想让sleep 后台悄悄跑
- 可以吗？🤔

### 重构环境

- 如果sleep.py已经丢了

```python
#!/usr/bin/python
i = 0
import time
while True:
    i = i + 1
    print(i, "===", time.asctime())
    time.sleep(1)
```

- 需要重写一下

### 查询进程

- 搜索 `debian进程查询`

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210923-1632366568717)

### 进程

- 具体方法

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230415-1681550407191/wm)

- 想要 结束进程
	- 只能 新开一个终端 
		- 再想办法

### 动手试试

- 将老终端向右移动
	- 新开一个终端
		- 运行ps -elf 

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221222-1671711495125)

- 查看到两条进程信息
	- 看起来上一个zsh就是pid为281的进程
	- 记住281这个pid
- 现在我想干掉 281这个进程
	- 怎么做呢？
- 搜索一下

### 搜索

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221222-1671711597110)

- 搜索结果

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221222-1671711641202)

### 杀意

- 搜到一个可怕的程序 
	- 叫做 `kill`😱
	- kill 可以给 某个pid的进程 发送信号
		- pid 可以通过 ps -elf 查到
- 上个zsh的pid
	- 就是刚刚的281

```bash
#杀死进程
kill -9 PID
```
- `-9` 就是死亡信号
	- 发过去之后 那个进程就要自尽 🥵
	- 没有任何进程 愿意接受 这个信号
	- 君要臣死，臣不得不死
- 活着 对进程 是多么重要啊
	- 但是 接到了 就要执行
	- 阿啊阿啊阿啊·～ 💀

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221222-1671711696374)

- 真的把 之前的那个zsh进程 干掉了
	- 窗口 都消失 了 
- 但是 看到的进程 太多了
	- 我只想要 和当前zsh有关的 进程

### zsh进程

- 查询本终端子进程
	- 我们只要和zsh这个进程相关的
	- 把e去掉

```
ps -lf
```

- 这样 只会出现
	- 本shell相关的进程

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221011-1665459097567)

- kill起来比较方便...

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20210221-1613902879487)

- 好像 还挺好玩
	- 再建 几个进程 放后台
	- 试着 kill一下

### 启动更多新进程

- 先启动 更多的报时程序
	- 然后<kbd>ctrl</kbd> + <kbd>z</kbd>
		- 挂起 suspend

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230127-1674788381492)

- 再试着一个个地kill
- suspend什么意思来着？

### suspend词源

- suspend = sus + pend

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221222-1671717103266)

- sus来自于sub 下面
	- sustain 
		- 支撑;承受(sus+tain握住→在下面握住→支撑)
	- suspect 
		- 怀疑 (sus+pect看→在下面看一看→怀疑)
	- susceptive 有接受力的;敏感的(sus+cept拿+ive→有拿下的能力→有接受力的)
- suspend是什么意思呢？

### -pend

- pend 来自于 *(s)pen-

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221222-1671717328723)

- *(s)pen- 意思为悬挂带着
	- depend 
		- de-, 向下，离开 -pend, 悬挂
		- 即悬挂点
		- 引申义依靠
		- denpendent
		- independent
	-  append
		-  词根词缀： ap- 来 , 临近 
		-  -pend- 悬挂 
		-  垂→依附
	-   expend
		-   ex- 出 , 向外 + -pend- 支付
		-   spend
- suspend 
	- 挂起
	- 吊，悬挂；推迟，暂停

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230126-1674739277939)

- 挂起来和推迟有啥关系？

### suspend

- 古代萨克逊人使用的刀叫做撒克逊刀
	- 刃朝上
	- 抽出来 就是要战斗

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20221222-1671717759925)

- 挂起来
	- sustain 了 
	- 就是不战斗了
	- 推迟战斗了
	- 暂停了
- 程序先不运行
	- 就是挂起了
- 先运行 再挂起
	- 还是 有点麻烦
- 可以 直接后台运行
	- 但是 不输出到屏幕 吗？

## 总结

- 进程查询
	- `ps -lf` 查看 本终端相关的 进程信息
	- `ps -elf` 查看 所有进程的 信息
- 杀死 进程
	- `kill -9 PID` 给进程发送死亡信号
	- <kbd>ctrl</kbd> + <kbd>z</kbd> 可以挂起进程

![图片描述](https://doc.shiyanlou.com/courses/uid1190679-20230414-1681437719569)

- 我们最初想要的是进程在后台
	- 悄悄运行
	- 可以吗？🤔
- 我们下次再说！👋

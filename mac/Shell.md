# Shell 入门

在本文开始之前，我想先阐述一下本文的基本内容。

本文的标题是《Shell 入门》，内容将涵盖 如何写一个基本的 Shell 脚本、如何运行它、一些基本的流程控制和判断，以及更多可供参考学习的站点。

话不多说，让我们从一个最简单的 Shell 脚本开始。

## 一、Hello World

打开一个文本编辑器，输入以下脚本代码，保存为 helloworld.sh：

```
#!/bin/sh

# it's just a demo

echo "Hello World"
```

接着，打开 命令行 ，切换至 helloworld.sh 所在目录，并输入以下命令：

```
$ /bin/sh helloworld.sh
```

可以看到，命令行中输出了 “哈喽沃德”：

```
Hello World
```

好了，这就是我们使用一个 Shell 脚本的基本流程：编写脚本 =&gt; 运行脚本 =&gt; 运行结果。

## 二、编写的三个要素

观察一下我们的 helloworld.sh，我们可以把它分为三部分：指定程序、注释说明 以及 脚本命令。

### 1、指定程序：`#!/bin/sh`

符号 `#!` 用于指定运行该脚本使用的程序。

在 helloworld.sh 中，我们用 `/bin/sh`来执行这个脚本。

### 2、注释说明：`# it's just a demo`

注释，以 `#` 开头的一行表示注释。

```
#!/bin/sh

# 这里是注释 
# 可以用来解释这个脚本是用来做什么的 

######### 分割线 #############
# 你也可以用多个#来做注释之间的分割
#############################

echo "Hello World"
```

### 3、脚本命令： `echo "Hello World"`

`echo`用于在命令行中打印指定的字符串。

你可以用单引号、双引号将要打印的字符串包裹起来，也可以选择不用引号。

## 三、运行的两个方式

运行一个脚本，有两种方法：作为参数 或者是 作为可执行文件。

### 1、作为参数

```
$ /bin/bash ./helloworld.sh
```

可以看到，我们通过给 `/bin/bash` 这个程序指定要运行的脚本，来运行 helloworld.sh 的。

### 2、作为可执行文件

首先，我们让这个脚本变成**可执行**的程序：

```
$ chmod +x helloworld.sh
```

接下来，就可以直接运行这个脚本：

```
$ ./helloworld.sh
```

## 四、小进阶

在了解了基本的 Shell 编程之后，我们来让 Shell 脚本做更多的事情。

### 1、读取输入

```
#!/bin/sh

# read.sh

echo "你的名字？"
read name

echo "你好 $name，很高兴认识你。"
```

运行一下：

```
$ /bin/sh read.sh 
你的名字？
```

输入 `daixinye`，回车：

```
你好daixinye，很高兴认识你。
```

### 2、条件判断

```
#!/bin/sh

# if.sh

echo "你的年龄？"
read age

# 注意 等号左右两边 不能有空格
myAge=18

# 注意 方括号内部前后 需要有空格
if [ $age == $myAge ]
    then 
        echo "我们岁数一样哦"
    else 
        echo "我们岁数不一样哦" 
fi
```

运行一下：

```
$ /bin/sh if.sh 
你的年龄？
```

输入 `18`，回车：

```
我们岁数一样哦
```

### 3、条件循环

```
#!/bin/sh

# while.sh

echo "我有一个数字，你要来猜一下吗？1~1000哦"

answer=666
bingo=0

while [ $bingo == 0 ]; do 
    read guess
    if [ $guess == $answer ]
        then
            echo "猜对啦"
            bingo=1
        else
            echo "猜错啦，再猜一次吧？"
    fi
done
```

运行一下：

```
$ /bin/sh while.sh 
我有一个数字，你要来猜一下吗？1~1000哦
```

依次输入1、5、10、100、600、666 ：

```
1
猜错啦，再猜一次吧？
5
猜错啦，再猜一次吧？
10
猜错啦，再猜一次吧？
100
猜错啦，再猜一次吧？
600
猜错啦，再猜一次吧？
666
猜对啦
```

## 五、小结

好啦，通过本文你应该已经了解了以下几个知识点：

1. 如何写一个基本 Shell脚本
2. 如何打印内容（echo）
3. 如何运行脚本（作为参数和作为可执行程序）
4. 如何读取输入（read）
5. 如何进行条件判断（if...else 语句）
6. 如何进行条件循环（while... do 语句）

## 本文参考

[https://my.oschina.net/maczhao/blog/349452](https://my.oschina.net/maczhao/blog/349452)

## 测试代码

[https://github.com/daixinye/practice/tree/master/shell](https://github.com/daixinye/practice/tree/master/shell)






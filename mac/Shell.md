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

## 参考

[https://my.oschina.net/maczhao/blog/349452](https://my.oschina.net/maczhao/blog/349452)

### 




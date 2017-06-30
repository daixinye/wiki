# Forever

一个简单的命令行界面工具，让你的脚本永久运行下去。

（本文翻译自 [https://www.npmjs.com/package/forever](https://www.npmjs.com/package/forever)）

## 安装

```
$ [sudo] npm install forever -g
```

**注意：**如果你想在代码中使用 forever ，那么你应该安装 [forever-monitor](https://github.com/foreverjs/forever-monitor)。

```
$ cd /path/to/your/project
$ [sudo] npm install forever-monitor
```

## 使用方法

forever 有两种使用方法：通过命令行命令或者在代码中使用。**注意：**如果想在代码中使用 forever ，那么你应该安装 [forever-monitor](https://github.com/foreverjs/forever-monitor)。

#### 命令行使用方法

##### 示例

```
$ forever start app.js
```

##### 选项

```
$ forever --help
使用方法： forever [action] [options] SCRIPT [script-options]
```

    actions:
        start                在后台运行脚本
        stop                 通过 Id|Uid|Pid|Index|Script 停止在后台运行的脚本
        stopall              停止所有用 forever 命令运行的脚本
        restart              重新运行在后台运行的脚本
        restartall           重新运行所有用 forever 命令运行的脚本
        list                 打印所有正在运行的 forever 脚本
        config               打印所有 forever 用户配置
        set <key> <val>      设置特定的 forever 配置 <key>
        clear <key>          清除特定的 forever 配置 <key>
        logs                 打印所有 forever 进程的日志文件
        logs <script|index>  Tails the logs for <script|index>
        columns add <col>    Adds the specified column to the output in `forever list`
        columns rm <col>     Removed the specified column from the output in `forever list`
        columns set <cols>   Set all columns for the output in `forever list`
        cleanlogs            [谨慎] 删除所有 forever 历史日志文件

    options:
        -m  MAX          运行该脚本不超过 MAX 次
        -l  LOGFILE      输出 forever 日志至 LOGFILE
        -o  OUTFILE      Logs stdout from child script to OUTFILE
        -e  ERRFILE      Logs stderr from child script to ERRFILE
        -p  PATH         Base path for all forever related files (pid files, etc.)
        -c  COMMAND      COMMAND to execute (defaults to node)
        -a, --append     Append logs
        -f, --fifo       Stream logs to stdout
        -n, --number     Number of log lines to print
        --pidFile        The pid file
        --uid            DEPRECATED. Process uid, useful as a namespace for processes (must wrap in a string)
                         e.g. forever start --uid "production" app.js
                             forever stop production
        --id             DEPRECATED. Process id, similar to uid, useful as a namespace for processes (must wrap in a string)
                         e.g. forever start --id "test" app.js
                             forever stop test
        --sourceDir      The source directory for which SCRIPT is relative to
        --workingDir     The working directory in which SCRIPT will execute
        --minUptime      Minimum uptime (millis) for a script to not be considered "spinning"
        --spinSleepTime  Time to wait (millis) between launches of a spinning script.
        --colors         --no-colors will disable output coloring
        --plain          Disable command line colors
        -d, --debug      Forces forever to log debug output
        -v, --verbose    Turns on the verbose messages from Forever
        -s, --silent     Run the child script silencing stdout and stderr
        -w, --watch      监视文件的改动（并重新运行脚本）
        --watchDirectory Top-level directory to watch from
        --watchIgnore    To ignore pattern when watch is enabled (multiple option is allowed)
        -t, --killTree   Kills the entire child process tree on `stop`
        --killSignal     Support exit signal customization (default is SIGKILL),
                         used for restarting script gracefully e.g. --killSignal=SIGTERM
        -h, --help       You're staring at it

```
 [Long Running Process]
    The forever process will continue to run outputting log messages to the console.
    ex. forever -o out.log -e err.log my-script.js

 [Daemon]
    The forever process will run as a daemon which will make the target process start
    in the background. This is extremely useful for remote starting simple node.js scripts
    without using nohup. It is recommended to run start with -o -l, & -e.
    ex. forever start -l forever.log -o out.log -e err.log my-daemon.js
        forever stop my-daemon.js
```




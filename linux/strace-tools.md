# strace工具的使用

http://wiki.swoole.com/wiki/page/202.html

strace可以跟踪系统调用的执行情况，在程序发生问题后，可以用strace分析和跟踪问题。 使用方法：

    FreeBSD/MacOS下可以使用truss

```sh 
strace -o /tmp/strace.log -f -p $PID
```

- -f 表示跟踪多线程和多进程，如果不加-f参数，无法抓取到子进程和子线程的运行情况
- -o 表示将结果输出到一个文件中
- -p $PID，指定跟踪的进程ID，通过ps aux可以看到
- -tt 打印系统调用发生的时间，精确到微妙
- -s 限定字符串打印的长度，如recvfrom系统调用收到的数据，默认只打印32字节
- -c 实时统计每个系统调用的耗时
- -T 打印每个系统调用的耗时


---------

Date: 2015-10-09  Author: alex cai <cyy0523xc@gmail.com>

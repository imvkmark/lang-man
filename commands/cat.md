# man - cat(1)


cat - 连接 一个/多个文件 并在标准输出上输出

## 语法

```
cat [OPTION] [FILE]...
```

## 示例

```
# 合并显示多个文件
cat ./1.log ./2.log ./3.log
# 显示文件中的非打印字符、tab、换行符
cat -A test.log
# 压缩文件的空行
cat -s test.log
# 显示文件并在所有行开头附加行号
cat -n test.log
# 显示文件并在所有非空行开头附加行号
cat -b test.log
# 将标准输入的内容和文件内容一并显示
echo '######' |cat - test.log
```


`cat f - g`
Output f's contents, then standard input, then g's contents.
输出 f 的内容, 然后标准输入, 然后 g 的内容
`cat`
Copy standard input to standard output.
复制标准输入到标准输出

```
$ cat > nusers    # 建立文件
who | wc -l 	  # 程序的内容
^D                # ctrl + D 表示 end of file
```

## 说明



## 描述

将文件列表中的文件或标准输入, 或连接到标准输出。

`-A`, `--show-all`
等价于 -vET 。
`-b`, `--number-nonblank`
给非空输出行编号。
`-e`
等价于 -vE 。
`-E`, `--show-ends`
在每行结束显示 $ 。
`-n`, `--number`
给所有输出行编号。
`-s`, `--squeeze-blank`
将所有的连续的多个空行替换为一个空行。
`-t`
等价于 -vT 。
`-T`, `--show-tabs`
把 TAB 字符显示为 ^I 。
`-u`
(被忽略的选项)
`-v`, `--show-nonprinting`
除了 LFD 和 TAB 之外所有控制符用 ^ 和 M- 记方式显示。
`--help`
显示帮助并退出。
`--version`
显示版本信息并退出。
没有指定文件或指定的文件是 -，则从标准输入读取。 


## 注意

- 该命令是`GNU coreutils`包中的命令，相关的帮助信息请查看`man -s 1 cat`或`info coreutils 'cat invocation'`。
- 当使用`cat`命令查看**体积较大的文件**时，文本在屏幕上迅速闪过（滚屏），用户往往看不清所显示的内容，为了控制滚屏，可以按`Ctrl+s`键停止滚屏；按`Ctrl+q`键恢复滚屏；按`Ctrl+c`（中断）键可以终止该命令的执行，返回Shell提示符状态。
- 建议您查看**体积较大的文件**时使用`less`、`more`命令或`emacs`、`vi`等文本编辑器。
- 显示文件内容，如果没有文件或文件为`-`则读取标准输入。
- 将多个文件的内容进行连接并打印到标准输出。
- 显示文件内容中的不可见字符（控制字符、换行符、制表符等）。

## 参考链接

1. [Question about LFD key](https://superuser.com/questions/328054/is-there-an-lfd-key-on-my-keyboard)



# man - who(1)


 who - 显示当前所有登陆用户的信息
 

## 语法

```
who [OPTION]... [ FILE | ARG1 ARG2 ]
```

当没有给出非选项参数时，按以下字段顺序为每个当前用户打印信息：登录用户名称，终端信息，登录时间，远程主机或X display。
当用户执行 `who am i` 时，只显示运行该命令的用户的信息。

## 示例

```
$ who
duoli    console  May 15 18:43 
duoli    ttys000  May 25 23:43 

$ who -q
duoli    duoli    

$ who -T
duoli    - console  May 15 18:43 
duoli    + ttys000  May 25 23:43 
```

## 选项

`-a`, `--all`
等价于 `-b -d --login -p -r -t -T -u`

`-b`, `--boot`
上次系统启动的时间

`-d`, `--dead`
打印 dead 状态的进程。

`-H`, `--heading`
显示各栏位的标题信息列

`-l`, `--login`
打印系统登录进程

`--lookup`
尝试通过 DNS 规范主机名

`-m`
此参数的效果和指定"am i"字符串相同
仅仅输入相关的主机名称和用户

`-p`, `--process`
打印由 init 生成的活动进程

`-q`, `--count`
只显示登入系统的帐号名称和总人数

`-r`, `--runlevel`
打印当前运行级别

`-s`, `--short`
显示用户名, 行, 时间(默认)

`-t`, `--time`
打印上次系统时钟更改

`-T, -w`, `--mesg`, `--message`, `--writable`
添加用户信息的状态(+, -, ?)
> `-w` mac 系统不存在

`-u`, `--users`
显示登录的用户

`--help` 
帮助

`--version`
版本信息

指定 `file` 代替默认的 `/var/run/utmp` 、`/etc/utmp` ；通常使用 `/var/log/wtmp` 作为参数用于查看过去登陆系统的用户.

If ARG1 ARG2 given, -m presumed: 'am i'    or  'mom  likes'  are usual.

## 注意

该命令是`GNU coreutils`包中的命令，相关的帮助信息请查看`man -s 1 who`，`info coreutils 'who invocation'`
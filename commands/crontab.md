# man - crontab(1)

为独立的用户维护计划任务文件

## 语法

```
crontab [-u user] file
crontab [-u user] [-l | -r | -e] [-i] [-s]
crontab -n [ hostname ]
crontab -c
```

## 描述

这个 crontab 命令提交、编辑、列出或移除 cron 计划任务。一个 cron 计划任务是一个命令，其运行是由 cron 守护程序在规则的调度间隔执行的。要提交一个 cron 计划任务，使用 `crontab -e`。crontab 命令调用一个编辑会话，允许创建一个 crontab 文件。为此文件中的每个 cron 计划任务创建条目。每个条目必须是正确的计划任务格式。

## 参数 

`-u {user}`
用来设定某个用户的crontab服务, 如果不使用这个选项, crontab 编辑当前用户的 crontab, 注意 `su` 可能会混淆 crontab, 所以使用 su 的时候必须要加上 `-u` 选项. 如果一个用户的计划任务不存在, 运行 `crontab -u` 的时候会自动创建. 

`-l`
显示某个用户的crontab文件内容，如果不指定用户，则表示显示当前用户的crontab文件内容

`-r`
从 `/var/spool/cron` 目录中删除某个用户的 crontab 文件，如果不指定用户，则默认删除当前用户的 crontab 文件。

`-e`
编辑某个用户的 crontab 文件内容。如果不指定用户，则表示编辑当前用户的 crontab 文件

`-i`
在删除用户的 crontab 文件时给确认提示

`-n`
`cron` 使用 `-c` 选项时候使用, 启用主机集群. 

`-c`
`cron` 使用 `-c` 选项时候使用, 启用主机集群. 

## 文件
```
/etc/cron.allow
/etc/cron.deny
```
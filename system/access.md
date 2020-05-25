# man - access(2)

access - 确定文件是否可以存取访问

Original: http://linux.die.net/man/1/access
> 在 centos 5.10 版本的机器上, 也无法进行安装


## 语法
```
access -mode file
```

## 说明

如果 file 可以在特定模式下存取访问,那么成功退出. mode 为 rwx 中的一个或多个字符, 这里的 r 表示可读, w 表示可写,而 x 表示可执行.
access 和 test 之间的区别在于 后者查看权限位,而前者使用 access(2) 系统调用进行检查.当文件系统以只读方式被挂载时,两者就有区别了.  

## 选项

access 接受以下附加的选项:
`--help`
打印帮助信息并退出.
`--version`
打印版本信息并退出.
 


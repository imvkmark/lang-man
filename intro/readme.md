# Linux man 命令后面的数字含义及作用

Linux的man很强大，该手册分成很多section，使用man时可以指定不同的section来浏览，各个section意义如下： 

```
1 - commands
2 - system calls
3 - library calls
4 - special files
5 - file formats and convertions
6 - games for linux
7 - macro packages and conventions
8 - system management commands
9 - 其他
```
解释一下

> 1 是普通的命令
> 2 是系统调用,如open,write之类的(通过这个，至少可以很方便的查到调用这个函数，需要加什么头文件)
> 3 是库函数,如printf,fread
> 4 是特殊文件,也就是/dev下的各种设备文件
> 5 是指文件的格式,比如passwd, 就会说明这个文件中各个字段的含义
> 6 是给游戏留的,由各个游戏自己定义
> 7 是附件还有一些变量,比如向 environ 这种全局变量在这里就有说明
> 8 是系统管理用的命令,这些命令只能由 root 使用,如 ifconfig
> 9 是其他命令

这里根据 https://www.die.net/ 进行 man 命令的区分, 欢迎大家提交 pr, 以便这个项目发展的更好
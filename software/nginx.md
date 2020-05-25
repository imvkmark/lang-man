# man - nginx(8)

应用服务器程序 nginx

## 参数

Nginx 安装后只有一个程序文件，本身并不提供各种管理程序，它是使用参数和系统信号机制对 Nginx 进程本身进行控制的。 Nginx 的参数包括有如下几个：
可以这样使用 /usr/local/nginx/sbin/nginx  -参数

`-c <path_to_config>`：使用指定的配置文件而不是 conf 目录下的 nginx.conf 。

`-t`：测试配置文件是否正确，在运行时需要重新加载配置的时候，此命令非常重要，用来检测所修改的配置文件是否有语法错误。

`-v`：显示 nginx 版本号。

`-V`：显示 nginx 的版本号以及编译环境信息以及编译时的参数。

## 配置文件

```
/etc/nginx/conf.d/
```

## 命令

平滑重启

```bash
$ nginx -s reload
```
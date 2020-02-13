# [转+] CentOS 7 更新 curl 为最新版本

原文地址: [CentOS 7 更新 curl 为最新版本](https://www.htcp.net/337.html)

## 介绍

由于 CentOS 7 内置的 curl 和 libcurl 源为较旧的 7.29.0，不支持一些新特性且有安全性问题，所以需要更新一下, 这里使用 city-fan 的更新源来更新。

## 1. 更新 ca-bundle

1. 首先备份一下：

```
$ cp /etc/pki/tls/certs/ca-bundle.crt /etc/pki/tls/certs/ca-bundle.crt.bak
```

2. 更新并替换：

```
$ curl http://curl.haxx.se/ca/cacert.pem -o /etc/pki/tls/certs/ca-bundle.crt
```



## 2. 新增 repo 源

新增 repo：

```
$ vim /etc/yum.repos.d/city-fan-for-curl.repo
```

内容为：

```
[CityFanforCurl]
name=City  Fan  Repo
baseurl=http://www.city-fan.org/ftp/contrib/yum-repo/rhel7/x86_64/
enabled=1
gpgcheck=0
```


## 3. 更新 curl

直接使用如下命令进行更新：

``` 
$ yum update curl --enablerepo=CityFanforCurl  -y
```

更新完成后，建议重启一下。就可以正常使用了。

## 4. 更新php-fpm

如果系统中 存在 php-fpm 程序, 则需要对安装的 php-fpm 进行重启

```
$ systemctl restart php-fpm
```
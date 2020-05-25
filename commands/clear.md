# man - clear(1)

clear - 清除终端屏幕  

## 语法

```
clear
```

## 说明

clear可以在允许的情况下清屏. 它会在环境变量中查找终端的类型, 然后到 `terminfo` 数据库中找出清屏的方法.  
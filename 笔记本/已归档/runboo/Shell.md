# Shell
#runoob 

## 教程

```shell
echo "Hello World!"
```


## 变量

```shell
your_name = "name"

```

## 传递参数

## 数组

## 运算符

## echo命令

## printf命令

```shell
$ echo "Hello, Shell"

```

## test命令

```shell
num1 = 100
num2 = 100
if test $[num1] -eq $[num2]
then
	echo '两个数相等'
else
	echo '两个数不相等'
fi
```

## 流程控制

## 函数
函数定义格式如下:
```shell
[ function ] funname [()]

{
	action;
	[return int;]
}
```

## 输入/输出重定向

## 文件包含
```shell
#!/bin/bash
url = "http://www.baidu.com"
```
```shell
. ./test.sh
echo "baidu网址: $url"
```
```bat
chmod +x test2.sh
./test2.sh
```
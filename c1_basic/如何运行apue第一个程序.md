###如何运行 apue 中的第一个程序###

`myls.c` 中 `#include "apue.h"`， `apue.h` 是作者自己编写的头文件，其具体实现是 `error.c` 与 `errorlog.c`。
可以从 [链接](http://www.apuebook.com/code3e.html) 下载源码，解压后，可以在 /apue.3e/include 下找到头文件，在 /apue.3e/lib 下找到剩下两个源文件。

我使用的是 ubuntu18.04， 将上述三个文件放在同一个文件夹下，使用如下命令将两个源文件编译名为 `libapue.a` 的库文件：
```
gcc -c error.c errorlog.c
ar scr libapue.a error.o errorlog.o
```


将 `apue.h` 放到 `/usr/include`（gcc 编译时默认在该目录查找头文件） 目录下。
将 `libapue.a` 放在 `/usr/lib` （gcc 编译时默认在该目录查找库文件）目录下。

之后运行以下命令就可以成功执行第一个程序：
`gcc myls.c -0 myls -lapue`

[关于链接与编译参考可以参考该文](https://blog.csdn.net/wohu1104/article/details/110730805)
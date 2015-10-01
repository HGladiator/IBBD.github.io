# 编译PHP扩展的相关工具

http://wiki.swoole.com/wiki/page/177.html

首先你需要下载一份扩展的源码，可以到github或者pecl.php.net上下载，解压后放到一个目录中，cd进入此目录。

## autoconf

根据config.m4生成configure脚本，phpize是基于autoconf的封装。

## phpize

phpize这个工具是php官方提供的，用于将PHP扩展的config.m4解析生成./configure 脚本。

## configure

这个脚本是用来检测系统和环境状态，依赖库和头文件是否存在，编译配置等

## php-config

这个工具执行后会打印当前PHP安装在哪里目录，API版本号是什么，扩展目录在哪里等信息。configure脚本需要依赖它找到PHP安装的目录

## make

用来将.c源文件编译为目标文件。make install将编译好的扩展文件，如swoole.so安装到PHP的扩展目录下

## gcc

编译器，将\*.c源文件编译为目标文件。并连接所有目标文件生成swoole.so

## clang

另外一种编译器，FreeBSD/MacOS下用的比较多。

## 安装过程

```sh 
phpize
./configure
make
make install
```

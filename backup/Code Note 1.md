# 关于 sizeof()函数的相关知识
```c
#include <stdio.h>

int main()
{
	printf("%d\n",sizeof(char));              //1    字节
	printf("%d\n",sizeof(short));             //2
	printf("%d\n",sizeof(int));               //4
	printf("%d\n",sizeof(long));              //4         C语言规定sizeof(long)>=sizeof(int)
	printf("%d\n",sizeof(long long));         //8
	printf("%d\n",sizeof(float));             //4
	printf("%d\n",sizeof(double));            //8
	printf("%d\n",sizeof(long double));       //12

        return 0；
}
```
sizeof(数据类型)  计算数据类型所占的字节数
一般前用%lu %zu %zd打印sizeof的结果
计算机中的单位 bit  比特位 计算机中的单位bit为存1个二进制比特位所使用的大小
	               byte 字节   8比特位 = 1字节 
//			   kb         1024byte = 1kb
//			   mb           1024kb = 1mb 
//		           gb           1024mb = 1gb
//			     tb           1024gb = 1tb
//			     pb           1024tb = 1pb
//			    eb           1024pb = 1eb
//			     zb           1024eb = 1zb
---
# 同一个项目下，不同源文件之间的参数是可以通过一定手段实现跨越源文件使用的，如：
## 源文件1
```c
int d = 22；
```
## 源文件2
```c
extern int d；\\声明了一个变量d，类型为int,来自外部文件的全局变量，可以在整个工程中适用
```
# 常量类型

1. 字面常量
2. const修饰的常变量
3. define定义的标识符常量
4. 枚举常量

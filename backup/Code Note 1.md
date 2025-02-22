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
```c
30   ;  //字面常量
3.14 ;  
'w'  ;  //字符，用了单引号
"asd";  //能用肉眼观察到的常量，字符串用的双引号
```
---
```c
const int a = 10;//const修饰的a，本职是变量，但是不能被修改，有了常量的属性。
int arr[10] = { 0 };//创建了一个数组，可以存放10个整型，[]中需要输入一个常量，但是上述的a不可替代10，a本质还是变量
```
---
```c
#define MAX 100 //不可被更改
#define HHH "sada"
int main()
{
	printf("%d\n", MAX);
	int a = MAX;
	printf("%s\n", HHH);//打印字符串使用%s 单个字符打印用%c
return 0;
}
```
---
```c
enum Color
	{
	RED,//此三为枚举常量
	GREEN,
	BLUE
	};
enum Color c = RED;
enum SEX
	{Male,
	 Female,
	 SECRET
         };  
```
枚举常量先进行内容的定义列举，之后再调用枚举常量时所定义的常量的形式只能从枚举的内容中定义
例如 enum SEX x=1 是不允许的
```
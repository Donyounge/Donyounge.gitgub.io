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
## 字面常量
```c
30   ;  //字面常量
3.14 ;  
'w'  ;  //字符，用了单引号
"asd";  //能用肉眼观察到的常量，字符串用的双引号
```
## const 修饰的常变量
```c
const int a = 10;//const修饰的a，本职是变量，但是不能被修改，有了常量的属性。
int arr[10] = { 0 };//创建了一个数组，可以存放10个整型，[]中需要输入一个常量，但是上述的a不可替代10，a本质还是变量
```
## define定义的标识符常量
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
## 枚举常量
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
---
# 字符相关
#include <string.h>是包含字符串处理函数的头文件。这个头文件定义了多种操作字符数组的函数，如strlen（求字符串长度）、strcmp（比较两个字符串是否相同）、strcpy（字符串拷贝操作）、strcat（字符串连接操作）等
```c
char ch = 'w';  \\单个字符用‘’
char sh = "adad";\\字符串用“”
char arr1[10] = "affdfe";//arr1后面的[]中的内容是字符串，字符串的结尾有一个\0，所以arr[10]中只能存放9个字符,也可以不写[]中的内容，长度由字符串的长度决定
```

F10进入调试模式，程序通过F10逐行运行，将程序运行到return0后观察各个字符串的储存情况
```c
char arr2[] = { 'a','b','c','d','e','f'};//字符串的结束标志是\0，所以arr2中的字符串没有结束标志，所以arr2中的字符串会被错误输出
//	printf("%s\n", arr1);//abcdef
//	printf("%s\n", arr2);//错误输出
//	printf("\0");//\0是字符串的结束标志，所以这里输出的是一个空格
//	strlen(arr1);//strlen是一个函数，用来计算字符串的长度，不包括\0,string length
//	int len  = strlen ("abc");//strlen的参数可以是一个字符串，也可以是一个字符数组
//	printf("%d\n", len); 3
```
# 转义字符相关

## 实例
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	//printf("adc\n");          \\输出adc
	//printf("adc\0adwq"); \\输出adc,\0后的内容不输出
return 0;
}
```
## 常见转义字符汇总

\? 书写连续多个问号时候使用，防止编译器将其识别为三目运算符 早期编译器中三字母词 ??)--] ??(--[  
\a 警告字符，响铃
\b 退格
\f 换页
\n 换行
\r 回车
\t 水平制表符
\v 垂直制表符
\\ 反斜杠
\' 单引号
\" 双引号
\0 空字符
\ddd 1-3位八进制数所代表的字符
\xhh 1-2位十六进制数所代表的字符
\uhhhh 4位十六进制数所代表的字符
\Uhhhhhhhh 8位十六进制数所代表的字符
\r\n windows下的换行符
\n linux下的换行符
\r mac下的换行符

# 打印使用

%d  十进制有符号整数
%u  十进制无符号整数
%o  八进制整数
%x  十六进制整数
%f  float浮点数
%lf double双精度浮点数
%e  指数形式的浮点数
%g  指数形式的浮点或小数
%c  字符
%s  字符串
%p  指针的值
%n  存储已写字符的数量
%m  打印errno对应的错误信息
%I[类型]  读取输入的数据
%*  跳过输入的数据
%[]  读取输入的数据
%[^]  读取输入的数据
%zu  size_t类型
%zd  ssize_t类型
%lu  unsigned long类型
%ld  long类型
##实例
```c
include<stdio.h>
int main()
{
	printf("asdd\n");//只有字符串和单个字符可以这样打印，其余都需要按下面的方式打印
	//printf("%s\n","asdd");\\标准格式
	printf("\a");\\响铃
	printf("%c\n", '\130');// \130是八进制数，代表的是十进制的88，按照ASCII编码，所以输出的是X
	printf("%c\n", '\x58');// \x58是十六进制数，代表的是十进制的88，按照ASCII编码，所以输出的是X
	printf("%c\n", 'X');
	printf("%d\n",strlen("qw ert"));//加了空格，所以除了\0是六个字符\\6
	return 0;
}
```
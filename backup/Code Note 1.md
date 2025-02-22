#关于 sizeof()函数的使用
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
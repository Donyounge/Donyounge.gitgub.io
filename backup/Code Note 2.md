# 实例
## 分支选择
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	int input = 0;
	printf("偶遇成都经典款胖熊，拼尽全力无法战胜，你的选择是成为(1/0)\n");
	scanf("%d", &input);
	
	if (input == 0)
	{ 
		printf("当0\n");
	}
	else
	{
		printf("当1\n");
	}
	return 0;
}
```
## 循环
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int	main()
{
	int line = 0;
	printf("天天学习\n");
	while (line<20000) 
	{  
		printf("写代码%d\n",line);
		line++;
	}
	if (line >= 20000)
	{
		printf("不赖\n");
	}
	else 
	{
		printf("不行\n");
	}
	return 0;
}
```
## 加法器函数
```c
int add(int x, int y) //int为函数的返回值类型
{int z = 0    ;
	 z = x + y;
	 return z ;//z是整数，返回为整数，函数前也要声明为整数
}
```
更加简化的写法
```c
/*int add(int x, int y)
{
	return (x + y); 更加简化的写法
}
```
使用例
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
int main()
{
	int num1 = 0;
	int num2 = 0;
	int  sum = 0;
	scanf("%d %d", &num1, &num2);
	sum = Add(num1, num2)       ;
	printf("sum=%d\n", sum)     ;
	return 0                    ;
}
```
## 比较器
```c
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
 int max(int x,int y)
 { if (x>y)
   return x;
   else
   return y;
 }
int main()
{    int num1 = 0;
     int num2 = 0;
     int     Big = 0;
    scanf("%d %d",&num1,&num2);
    Big = max(num1,num2);
    printf("比较大的是%d\n"，Big);
    return 0;
}
```

# 数组
```c
int main()
{
	int arr[10] = { 0,1,2,3,4,5,6,7,18,9 };//其实数组里的元素是有隐藏的排序下标的，从0开始
	printf("%d\n",arr[8]);                    //打印数组里的第八个元素 
	int i = 0;
	while (i < 10)
	{
		printf("%d\n", arr[i]);
		i++;
	}
	return 0;
}
```
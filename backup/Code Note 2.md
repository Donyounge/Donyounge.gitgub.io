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
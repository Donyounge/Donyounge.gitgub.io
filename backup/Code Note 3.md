**EOF- End Of File 文件的结束标志 值是-1 通过左键选中右键下拉栏中查看定义**
# 关于ASCII的实例*2
输入ASCII码值，输出对应字符
```c
int main() 
{
    int c;
    scanf("%d", &c);
    printf("%c\n", c);
    return 0;
```
输入数值，输出对应ASCII码
```c
int main()
{
    char c;
    scanf("%c", &c);
    printf("%d\n", c);
    return 0;
}
```
# 算数操作符 +  -  *  /  % 
## 相关实例
```c
int main()
{
    int a = 7 / 2;
    int b = 7 % 2;
    float = 7.0/2；
//除号'/'的两端都是整数的时候，执行整数除法，结果也是整数，小数部分会被舍弃
//如果两端只要有一个是小数，结果就是小数
//'%'取模的两侧只能都是整数
//如果两端只要有一个是小数，结果就是小数
    printf("%d\n", a);//3
    printf("%d\n", b);//1 取模/取余 
    printf("%f\n", c);//3.5 此时进行浮点数除法
    printf("%.1f\n", c);//小数点后保留一位
    return 0;
}
```
# 赋值操作符及其相关实例
```c
int main()
{
	int a = 0;//初始化
	a = 20;   //赋值
	a += 3;   //a = a + 3//值为23
	a -= 5;   //a = a - 5//值为18
	a *= 2;   //a = a * 2//值为36
	a /= 4;   //a = a / 4//值为9
	a %= 4;   //a = a % 4//值为1

	return 0;
}

```
# 移位操作符
**移位操作符 >> <<**
# 位操作符
**位操作符  &  ^  |**  
# 双目操作符 
```c
a+b;
a-b;
a*b;
a/b;
a%b;
```
有两个参数参与、
# 单目操作符
!        逻辑反操作
-        负值
+        正值
&        取地址
sizeof   操作数的类型长度
~        对一个数的二进制按位取反
--       前置、后置--
++       前置、后置++
*        间接访问操作符（解引用操作符）
(类型)   强制类型转换
## 相关实例 ！
```c
\\C语言中  0表示假  非零表示真
 int main()
{
	int  flag = 1;
	if (!flag)//flag为0，取反为1，所以为真
	{
		printf("hehe\n");
	}
	else
	{
		printf("hoho\n");
	}

	return 0;
}

```
## 相关实例 size of #3 相关size of
```c
int main()
{
	int a = 10;
	printf("%d\n", sizeof(a));   //4
	printf("%d\n", sizeof (int));//4 
	printf("%d\n", sizeof a);    //4
	int arr[10] = { 0 };
	printf("%d\n", sizeof(arr));//40,是整个数组的大小，数组中有10个元素，每个元素是4个字节
	printf("%d\n", sizeof(arr[0]));//4,是数组中第一个元素的大小
	printf("%d\n", sizeof(arr) / sizeof(arr[0]));//10,数组的大小/数组中第一个元素的大小=数组中元素的个数
	return 0;
}

```
## 相关实例 前++与后++
```c
int main()
{
	int a = 10;
	int b = a++;
	//后置++，先赋值再++，等同int b = a; a = a + 1;

	printf("%d\n", b);
	printf("%d\n", a);
	return 0;
}
int main()
{
	int a = 10;
	int b = ++a;
	//前置++，先++再复制，等同a = a+1;int b = a; 

	printf("%d\n", b);
	printf("%d\n", a);
	return 0;
```
## 相关实例 强制类型转换
```c
int main()
{
	int a = 3.14;
	//3.14是一个浮点数，编译器默认其为double类型，double类型的数赋值给int类型的变量，会丢失精度
	printf("%d\n", a);//3
	int a = (int)3.14;
	printf("%d\n", a);//3
	return 0;
}
```
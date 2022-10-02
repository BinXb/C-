### 分支语句（选择结构）
#### if语句（三种结构）
	语法结构：
	if(表达式)
		语句；
}

	if(表达式)
		语句1；
	else
		语句2；
}

	if(表达式1)
		语句1；
	else if(表达式2)
		语句2；
	else
		语句3；
}

#include <stdio.h>
int main()
{
	int age = 20;
	if (age < 18)
		printf("未成年 \n");
	else if (age >= 18 && age < 28)
		printf("青年 \n");
	else
		printf("成年 \n");
	return 0;
}


如果条件成立，要执行多条语句，则要使用代码块
代码块用{	}表示，一对{	}是一个代码块

	if(表达式)
	{
		语句1；
	}
	else
	{
		语句2；
	}	

#### 悬空else
```
#include <stdio.h>
int main()
{
	int a = 0;
	int b = 2;
	if (a == 2)
		if(b == 2)
		printf("hehe\n");
	else//else离他最近的if语句匹配，可以利用代码块分离
		printf("haha\n");
	return 0;
}
```
输出1-100之间的奇数
```
#include <stdio.h>
int main()
{
	//输出1-100之间的奇数
	for (int i = 0;i<=100;i++)
	{
		if (i % 2 == 1)
		{
			printf("%d\n", i);
		}
	}
	return 0;
}
```
#### switch
```
switch(整形表达式)
	case 值1://case 整型/常量表达式
		printf();
		break;
	case 值2:
		printf();
		break;
	...
	
```
键盘输入数字，打印星期
```
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>


int main()
 {
	int day = 0;
	scanf("%d", &day);
	switch (day)
	{
	case 1:
		printf("今天是星期一 \n");
		break;//跳出循环
	case 2:
		printf("今天是星期二 \n");
		break;
	case 3:
		printf("今天是星期三 \n");
		break;
	case 4:
		printf("今天是星期四 \n");
		break;
	case 5:
		printf("今天是星期五 \n");
		break;
	case 6:
		printf("今天是星期六 \n");
		break;
	case 7:
		printf("今天是星期日 \n");
		break;
	default://处理非法情况时使用
		printf("输入错误\n");
		break;
	}
	return 0;
}

```	
### 循环语句
#### while 语法结构
while (表达式)
	循环语句:

```
#include <stdio.h>


int main()
 {
	int i = 1;
	while (i<=10)
	{
		if (i == 5)
			continue;//继续（跳过本次循环下面的代码）
		printf("%d\n", i);
		i++;
	}
	return 0;
}
```

break再while循环中的作用：
	停止后期循环中所有的循环，直接终止循环
continue介绍：
	跳过本次循环下面的代码，继续执行下一次循环

getchar -- 获取键盘输入的字符
```
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>

int main()
 {
	//int ch = getchar();//getchar输入字符
	//putchar(ch);//putchar输出字符
	int ch = 0;
	//ctrl + z会获取EOF 结束 --> -1 
	while ((ch = getchar()) != EOF)
	{
		putchar(ch);
	}
	return 0;
}
```
### while的补充

缓冲区
```
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>

int main()
{
	int ret = 0;
	int ch = 0;
	char password[20] = { 0 };
	printf("请输入密码:");
	scanf("%s", password);//输入密码，并存放在password数组中
	//缓冲区还剩余个'\n'
	//读取一下\n
	//getchar();
	while ((ch = getchar()) != '\n')//清空缓冲区中的数据
	{
		;
	}
	printf("请确认(Y/N)");
	ret = getchar();
	if (ret == 'Y')
	{
		printf("确认");
	}
	else
	{
		printf("放弃");
	}
	return 0;
}
```
 代码2
```
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>

int main()
{
	int ch = 0;
	while ((ch = getchar()) != EOF)
	{
		if (ch < '0' || ch>'9')//只会输出数字字符，其他字符不会输出
			continue;
		putchar(ch);
	}
	
	return 0;
}

```
### for循环（重要）
语法：for(表达式1;表达式2;表达式3)
			{
					循环语句；
			}

举例：在屏幕上打印1-10的数字
```
#include <stdio.h>

int main()
{
	for (int i = 1; i <= 10; i++)
	{
		printf("%d\n", i);
	}
	return 0;
}
```

建议：
	1.不可在for循环体内修改循环变量，防止for循环失去控制
	2.建议for语句的循环控制变量的取值采用“前闭后开区间”写法

#### for循环的变种
>变种1

for循环的初始化，调整，判断都可以省略
但是：
	for循环的判断部分如果被省略，则判断条件恒为真
	如果不是非常熟练，建议大家不要随便省略
```
#include <stdio.h>

int main()
{
	for (;;)
	{
		printf("hehe\n");
	}
	return 0;
}
```

>变种2

```//比较少见
#include <stdio.h>

int main()
{
	int x, y;
	for (x = 0, y = 10; x < 2 && y>5; ++x, y++)
	{
		printf("hehe\n");
	}
	return 0;
}
```

### do...while循环
>语法:
	do
		循环语句:
	while(表达式);


```
int main()
{
	//1-10
	int i = 1;
	do
	{
		printf("%d\n", i);
		i++;
	}
	while (i <= 10);
	return 0;
}
```

### 例题：二分查找
```
#include <stdio.h>

int main()
{

	int arr[] = { 1,2,3,4,5,6,7,8,9,10 };//创建一个数组
	int k = 7;//确定要查找的元素
	int sz = sizeof(arr) / sizeof(arr[0]);//计算元素个数
	int left = 0;//数组左下标
	int right = sz - 1;//数组右下标
	while (left<=right)
	{
		int mid = (left + right) / 2;//二分查找法，查找中间元素进行比较
		if (arr[mid] > k)//
		{
			right = mid - 1;
		}
		else if (arr[mid] < k)
		{
			left = mid + 1;
		}
		else
		{
			printf("找到了，下标是：%d\n", mid);
			break;
		}
	}
	if (left > right)
	{
		printf("找不到\n");
	}
	return 0;
}
```


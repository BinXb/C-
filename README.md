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

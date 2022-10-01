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

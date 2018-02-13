#include<stdio.h>
#include<stdlib.h>
#include<time.h>
#include<unistd.h>
int main()
{
	//产生4个0——9的随机数字
	srand((unsigned int)time(NULL));
	int a[4];
	int b[4];
	int num;
	a[0] = rand()%9;
	a[1] = rand()%9;
	a[2] = rand()%9;
	a[3] = rand()%9;

	//输入数字的每一位与前面产生的4个随机数进行比较，并给出正确反馈。
	//不断输入4位数字，直至四位分别与a,b,c,d相等，停止程序。
	
	//上一步求出的4个数值与随机产生的4个数值进行比较。
	do
	{	
		printf("请输入4位数字：");
		scanf("%d",&num);
		//求出4位数字的各个位上的数值。
		 b[0] = num / 1000;
		 b[1] = (num % 1000) / 100;
		 b[2] = (num % 100) /10;
		 b[3] = num % 10;
		//比较第一位
		if(b[0]>a[0])
		{
			printf("第一位大于正确数字。\n");
		}
		else if(b[0]<a[0])
		{
			printf("第一位小于正确数字。\n");
		}
		else
		{
			printf("第一位正确。\n");
		}
		//比较第二位
		if(b[1]>a[1])
		{
			printf("第二位大于正确数字。\n");
		}
		else if(b[1]<a[1])
		{
			printf("第二位小于正确数字。\n");
		}
		else
		{
			printf("第二位正确。\n");
		}
		//比较第三位
		if(b[2]>a[2])
		{
			printf("第三位大于正确数字。\n");
		}
		else if(b[2]<a[2])
		{
			printf("第三位小于正确数字。\n");
		}
		else
		{
			printf("第三位正确。\n");
		}
		//比较第四位
		if(b[3]>a[3])
		{
			printf("第四位大于正确数字。\n");
		}
		else if(b[3]<a[3])
		{
			printf("第四位小于正确数字。\n");
		}
		else
		{
			printf("第四位正确。\n");
		}
	}while(!(a[0]==b[0] && a[1]==b[1] && a[2]==b[2] && a[3]==b[3]));
	sleep(2);
}

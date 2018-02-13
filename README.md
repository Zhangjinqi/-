#include<stdio.h>
#include<stdlib.h>
#include<time.h>
#include<unistd.h>
int main()
{
	//产生4个0——9的随机数字
	int a[4];
	int b[4];
	int num;
	//a[0]不能为0.
	do
	{
	srand((unsigned int)time(NULL));
	a[0] = rand()%10;
	}while(a[0]==0);
	a[1] = rand()%10;
	a[2] = rand()%10;
	a[3] = rand()%10;

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
		//这里可以将四个比较合并成循环，什么脑子。
        int i;
		for(i=0;i<4;i++)
		{
			if(b[i]>a[i])
			{
				printf("第%d位大于正确数字。\n",i+1);
			}
			else if(b[i]<a[i])
			{
				printf("第%d位小于正确数字。\n",i+1);
			}
			else
			{
				printf("第%d位正确。\n",i+1);
			}
		}
	}while(!(a[0]==b[0] && a[1]==b[1] && a[2]==b[2] && a[3]==b[3]));
	printf("恭喜你猜对了\n");
    sleep(2);
}

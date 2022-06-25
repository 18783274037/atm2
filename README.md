# atm2
Atm机设计

#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <windows.h>
#define NUM 1001
void denglu();
void denglu2();
void shezhi();
void shezhi2(); 
void enter();
void enter2();
void enter3();
void enter4();
void tuichu();
void tuichu2();
void zhuanzhang();
void zhuanzhang2();
void chaxun();
void chaxun2();
void qukuan();
void qukuan2();
void cunkuan();
void cunkuan2();
void xiugai();
void xiugai2();
void load();
void save();

int j = 0, k;
struct yonghu
{
	char ID[20];
	char key[20];
	int account;
}user[NUM];


int main()
{
	printf("欢迎进入ATM机系统\n"); 
    printf("中文服务\n");
    printf("请按1！\n");
	printf("Engilsh servise\n"); 
	printf("press two\n");
	
	int x;
	scanf("%d",&x); 
	if(x==1)
	{
			enter();
	}
	else
	if(x==2)
	{
	        enter3();
	}

//进入界面 
	return 0;

}


void enter3()//一级菜单函数
{
	int a;
	load();
	system("cls");
	printf(" \t\t\t             ATM analog system\n");
	printf("|BLACK HEART Bank of China welcomes you|\n");
	printf("\n\n");
	printf("You have the following options\n");
	printf(" 1.sign in\n");
	printf(" 2.sign up\n");
	printf("3.back\n");
	printf("please enter your operation number");
	scanf("%d", &a);
	switch (a)
	{
	case 1:system("cls");//清屏
		shezhi2();
		break;
	case 2:system("cls");
		denglu2();
		break;
	case 3:system("cls");
		tuichu2();
		break;
	default:printf("\t\t\t\t无此操作项\n请重新选择\n");
		system("pause");
		system("cls");
		enter();
	}
}

void tuichu2()
{
	printf("Thank you for using it!\n");
	
	printf("welcome to use next time\n");
	printf("see you again!\n");
	exit(0);
}
void enter4()
{
	int n;
	do
	{
		printf("\n\n\n");
		printf(" \t\t\t+  A T M System PERSONAL Interfac  +\n");
		printf(" \t\t\t+  you have the f0llowing options  +\n");
		printf(" \t\t\t    #     1.  inquire  #\n");
		printf(" \t\t\t    #     2.  withdrawn#\n");
		printf(" \t\t\t    #     3.  transfer #\n");
		printf(" \t\t\t    #     4.  deposit  #\n");
		printf(" \t\t\t    #     5.change password #\n");
		printf(" \t\t\t    #     6.  return   #\n");
		scanf("%d", &n);
		switch (n)
		{
		case 1:system("cls");
			chaxun2();
			break;
		case 2:system("cls");
			qukuan2();
			break;
		case 3:system("cls");
			zhuanzhang2();
			break;
		case 4:system("cls");
			cunkuan2();
			break;
		case 5:system("cls");
			xiugai2();
			break;
		case 6:system("cls");
			enter3();
			break;
		default:printf("\t\t\t\t无此操作项\n\n");
			system("pause");
			system("cls");
		}
	} while (n > 4 && n < 0);
}


void denglu2()
{
	int i, n, m;

	char  id[20], kw[20];
	printf("\t\t   Enter an incorrect account or password for three consecutive times and return to the main menu\n\n\n");

	for (i = 0; i < 3; i++)
	{
		printf("please enter your login account\n");
		scanf("%s", id);
		for (k = 0; k < NUM - 1; k++)
		{
			if (strcmp(id, user[k].ID) == 0)
			{
				m = 1;
				break;
			}
			else
				m = 0;
		}
		if (m == 0)
		{
			printf("The account does not exist%d\n", 2 - i);
			if ((2 - i) == 0)
			{
				printf("Enter an incorrect account or password for three consecutive times and return to the main menu......\n\n\n");
				system("pause");
				enter3();
			}
		}

		if (m == 1)
		{
			printf("Please enter your login password\n");
			for (n = 0; n < 3; n++)
			{
				scanf("%s", kw);
				if (strcmp(kw, user[k].key) == 0)
				{
					system("cls");
					enter4();
				}
				else
				{
					printf("The account does not exist%d\n", 2 - n);
					if ((2 - n) == 0)
					{
						printf("Enter an incorrect account or password for three consecutive times and return to the main menu......\n\n\n");
						system("pause");
						enter3();
					}
				}
			}
		}
	}
}


void chaxun2()
{

	char ch;
	load();
	printf("\t\t\t******wlecome tofind servise******\n");
	printf("\t\t\t     your balance%dRNB\n\n", user[k].account);
	system("pause");
	system("cls");
	printf("\n\n\n");
	ch = getchar();//用来接收最后的回车符
	if (ch == '\n')
	{
		enter4();
	}
}

void qukuan2()
{

	int i, x;
	char a, ch;
	printf(" The minimum withdrawal amount of our bank is100RNB\n");
	printf("your card balance\n");
	printf(" %dRNB+\n", user[k].account);
	printf("The amount you need to withdraw:\n");
	printf("1: 100RNB     2:200RNB\n");
	printf("3.500RNB      4:1000RNB\n");
	printf("5:2000RNB     6:5000RNB+\n");
	printf("7: Custom amount+\n");
	printf("back step\n");
	scanf("%d", &i);
	if (i == 1)
	{
		x = 100;
	}
	else
		if (i == 2)
		{
			x = 200;
		}
		else
			if (i == 3)
			{
				x = 500;
			}
			else
				if (i == 4)
				{
					x = 1000;
				}
				else
					if (i == 5)
					{
						x = 2000;
					}
					else
						if (i == 6)
						{
							x = 5000;
						}
						else
							if (i == 7)
							{
								printf("\t\t\t\tplease input Custom amount:\n\t\t\t\t  ");
								scanf("%d", &x);
							}
	if (x <= user[k].account)
	{
		user[k].account = user[k].account - x;
		printf(" \t\t\t\ttake%dRNB\n", x);
		printf(" \t\t\t\tyour card balance%dRNB\n", user[k].account);
	}
	else if (x > user[k].account)
	{
		printf("\t\t\t\tYour credit card balance is insufficient\n");
		printf("\t\t\t\tPlease re-enter the withdrawal amount:\n");
	}
	printf(" \t\t\t\tPlease choose whether to continue the withdrawal\n");
	printf(" \t\t\t\tYES:Y          NO:N\n\n\t\t\t\t  ");
	scanf("%s", &a);
	if (a == 'Y')
	{
		save();
		qukuan2();
	}
	else
		if (a == 'N')
		{
			save();
			system("pause");//冻结屏幕
			system("cls");
			printf("\n\n\n");
		}
		else
		{
			save();
			system("pause");//冻结屏幕
			system("cls");
			printf("\n\n\n");
		}
		
		
	ch = getchar();//用来接收最后的回车符
	if (ch == '\n')
	{
		system("cls");
		enter4();
	}
}

void cunkuan2()
{

	int a;
	printf("\t\t\t\tyour still have a balance:\n\n\t\t\t\t  ");
	scanf("%d", &a);
	user[k].account = user[k].account + a;
	save();
	printf(" \t\t\t\tyyour balance %dRNB\n", user[k].account);
	system("pause");//冻结屏幕
	system("cls");
	printf("\n\n\n");
	enter2();
}
void xiugai2()
{

	printf("\t\t\t\tplease you input new password\n\t\t\t\t  ");
	scanf("%s", user[k].key);
	save();
	system("pause");//冻结屏幕
	system("cls");
	printf("\n\n\n");
	enter4();
}

void zhuanzhang2()
{
	int a,  x;
	char kahao[20];
	printf("\t\t\t       please you input tranfer account:\n\t\t\t\t  ");
	scanf("%s", kahao);
	for (a = 0; a < NUM - 1; a++)
	{
		if (!strcmp(kahao, user[a].ID))
		{
			printf("\t\t\t\t  true account\n\n");
			break;
		}
	}
	if (strcmp(kahao, user[a].ID))
	{
		printf("\t\t\t\t  not find account\n\n");
		system("pause");
		zhuanzhang2();
	}
	printf("\t\t\t\tplease input transfer RNB\n\t\t\t\t    ");
	scanf("%d", &x);

	if (x > user[k].account)
	{
		printf("\t\t\t\tPlease re-enter the withdrawal amount\n");
		printf("\t\t\t\tPlease choose whether to continue the withdrawal:\n");
	}
	else
	{
		user[k].account = user[k].account - x;
		user[a].account = user[a].account + x;
		save();
	}
	system("pause");//冻结屏幕
	system("cls");
	printf("\n\n\n");
	enter4();
}

void shezhi2()
{

	char ch;
	if (user[1000].account != 0)
	{
		j = user[1000].account;
	}
	printf("\n\n\t\t\t\tplease set your card number:\n\t\t\t\t  ");
	scanf("%s", user[j].ID);
	printf("\n\t\t\t\tplease set your password:\n\t\t\t\t  ");
	scanf("%s", user[j].key);
	user[j].account = 0;
	printf("card number：%s \nbalance：%4d\n", user[j].ID, user[j].account);
	user[1000].account = ++j;
	save();
	printf("\n\n\t\t\t\tCongratulations on your successful registration!");
	printf("\n\n\n");
	system("pause");
	printf("\t\t\t\tback step!\n");
	printf("\n\n\n");
	system("cls");
	ch = getchar();//用来接收最后的回车符
	if (ch == '\n')
	{
		enter3();
	}
}











//中文代码区 
void enter()//一级菜单函数
{
	int a;
	load();
	system("cls");
	printf("ATM机\n");
	printf("|欢迎使用黑心银行|\n");
	printf("1.注册\n");
	printf("2.登录\n");
	printf("3.退出\n");
	printf("\n\n");
	printf(" \t\t\t   |请输入您的操作号| \n\n\t\t\t\t  ");
	scanf("%d", &a);
	switch (a)
	{
	case 1:system("cls");//清屏
		shezhi();
		break;
	case 2:system("cls");
		denglu();
		break;
	case 3:system("cls");
		tuichu();
		break;
	default:printf("\t\t\t\t无此操作项\n请重新选择\n");
		system("pause");
		system("cls");
		enter();
	}
}

void load()
{
	FILE* fp;
	int i;
	if ((fp = fopen("D:/new.txt", "r")) == NULL)
	{
		printf("不能打开文件\n");
		return;
	}
	for (i = 0; !feof(fp); i++)
	{
		fread(&user[i], sizeof(struct yonghu), 1, fp);
	}
	fclose(fp);
	system("cls");
	printf("文件读取成功\n");
}
void save()
{
	FILE* fp;
	if ((fp = fopen("D:/new.txt", "w")) == NULL)
	{
		printf("无法打开文件\n");
		exit(0);
	}
	fwrite(user, sizeof(struct yonghu), NUM, fp);
	printf("文件写入完成\n");
	fclose(fp);
}

void shezhi()
{

	char ch;
	if (user[1000].account != 0)
	{
		j = user[1000].account;
	}
	printf("\n\n\t\t\t\t请设置您的卡号:\n\t\t\t\t  ");
	scanf("%s", user[j].ID);
	printf("\n\t\t\t\t请设置您的密码:\n\t\t\t\t  ");
	scanf("%s", user[j].key);
	user[j].account = 0;
	printf("卡号：%s \n余额：%4d\n", user[j].ID, user[j].account);
	user[1000].account = ++j;
	save();
	printf("\n\n\t\t\t\t恭喜您注册成功!");
	printf("\n\n\n");
	system("pause");
	printf("\t\t\t\t按回车键返回上一级\n");
	printf("\n\n\n");
	system("cls");
	ch = getchar();//用来接收最后的回车符
	if (ch == '\n')
	{
		enter();
	}
}
void tuichu()
{
	printf("\t\t\t**********谢谢**********\n");
	printf("\t\t\t******感谢您的使用******\n");
	printf("\t\t\t******欢迎下次光临******\n");
	printf("\t\t\t**********再见**********\n");
	exit(0);
}
void denglu()
{
	int i, n, m;

	char  id[20], kw[20];
	printf("\t\t    连续输错账号或密码三次，将返回主菜单\n");

	for (i = 0; i < 3; i++)
	{
		printf("请输入登录账号\n");
		scanf("%s", id);
		for (k = 0; k < NUM - 1; k++)
		{
			if (strcmp(id, user[k].ID) == 0)
			{
				m = 1;
				break;
			}
			else
				m = 0;
		}
		if (m == 0)
		{
			printf("该账号不存在,剩余输入次数%d\n", 2 - i);
			if ((2 - i) == 0)
			{
				printf("账号输入错误3次，即将返回菜单......\n");
				system("pause");
				enter();
			}
		}

		if (m == 1)
		{
			printf("请输入登录密码\n");
			for (n = 0; n < 3; n++)
			{
				scanf("%s", kw);
				if (strcmp(kw, user[k].key) == 0)
				{
					system("cls");
					enter2();
				}
				else
				{
					printf("密码输入错误,剩余输入次数%d\n", 2 - n);
					if ((2 - n) == 0)
					{
						printf("密码输入错误3次，即将返回菜单......\n");
						system("pause");
						enter();
					}
				}
			}
		}
	}
}

void enter2()
{
	int n;
	do
	{
		printf("\n\n\n");
		printf("A T M 系 统 操 作 界 面\n");
		printf("您 有 以 下 选 择\n");
		printf("1.  查询\n");
		printf("2.  取款\n");
		printf("3.  转账\n");
		printf("4.  存款\n");
		printf("5.修改密码\n");
		printf("6.返回目录\n");
		scanf("%d", &n);
		switch (n)
		{
		case 1:system("cls");
			chaxun();
			break;
		case 2:system("cls");
			qukuan();
			break;
		case 3:system("cls");
			zhuanzhang();
			break;
		case 4:system("cls");
			cunkuan();
			break;
		case 5:system("cls");
			xiugai();
			break;
		case 6:system("cls");
			enter();
			break;
		default:printf("无此操作项\n\n");
			system("pause");
			system("cls");
		}
	} while (n > 4 && n < 0);
}


void chaxun()
{

	char ch;
	load();
	printf("欢迎使用查询服务\n");
	printf("     您的余额为%d元\n\n", user[k].account);
	system("pause");
	system("cls");
	printf("\n\n\n");
	ch = getchar();//用来接收最后的回车符
	if (ch == '\n')
	{
		enter2();
	}
}
void qukuan()
{

	int i, x;
	char a, ch;

	printf("   本银行最低取款金额为100元  +\n");
	printf("        您卡号的余额为        +\n");
	printf("        %d元                  +\n", user[k].account);
	printf("     请选择你要提取的金额:    +\n");
	printf("     1: 100元     2:200元     +\n");
	printf("     3.500元      4:1000元    +\n");
	printf("     5:2000元     6:5000元    +\n");
	printf("         7: 自定义金额        +\n");
	printf(" ******返回上一步请按回车键*****\n");
	scanf("%d", &i);
	if (i == 1)
	{
		x = 100;
	}
	else
		if (i == 2)
		{
			x = 200;
		}
		else
			if (i == 3)
			{
				x = 500;
			}
			else
				if (i == 4)
				{
					x = 1000;
				}
				else
					if (i == 5)
					{
						x = 2000;
					}
					else
						if (i == 6)
						{
							x = 5000;
						}
						else
							if (i == 7)
							{
								printf("请输入自定义的金额:\n");
								scanf("%d", &x);
							}
	if (x <= user[k].account)
	{
		user[k].account = user[k].account - x;
		printf(" 您取了%d元钱\n", x);
		printf(" 您的余额为%d元\n", user[k].account);
	}
	else if (x > user[k].account)
	{
		printf("您卡里的余额不足\n");
		printf("请重新输入提取金额:\n");
	}
	printf(" 请选择是否继续取款\n");
	printf(" 是:Y          否:N\n\n  ");
	scanf("%s", &a);
	if (a == 'Y')
	{
		save();
		qukuan();
	}
	else
		if (a == 'N')
		{
			save();
			system("pause");//冻结屏幕
			system("cls");
			printf("\n\n\n");
		}
		else
		{
			save();
			system("pause");//冻结屏幕
			system("cls");
			printf("\n\n\n");
		}
		
		
	ch = getchar();//用来接收最后的回车符
	if (ch == '\n')
	{
		system("cls");
		enter2();
	}
}

void cunkuan()
{

	int a;
	printf("请输入存入账户的金额:\n\n");
	scanf("%d", &a);
	user[k].account = user[k].account + a;
	save();
	printf("您的余额为%d元\n", user[k].account);
	system("pause");//冻结屏幕
	system("cls");
	printf("\n\n\n");
	enter2();
}


void xiugai()
{

	printf("请输入新的密码\n");
	scanf("%s", user[k].key);
	save();
	system("pause");//冻结屏幕
	system("cls");
	printf("\n\n\n");
	enter2();
}


void zhuanzhang()
{
	int a,  x;
	char kahao[20];
	printf("请输入转账卡号:\n");
	scanf("%s", kahao);
	for (a = 0; a < NUM - 1; a++)
	{
		if (!strcmp(kahao, user[a].ID))
		{
			printf("卡号正确\n");
			break;
		}
	}
	if (strcmp(kahao, user[a].ID))
	{
		printf("卡号不存在\n");
		system("pause");
		zhuanzhang();
	}
	printf("请输入转账金额\n    ");
	scanf("%d", &x);

	if (x > user[k].account)
	{
		printf("您卡里的余额不足\n");
		printf("请重新输入提取金额:\n");
	}
	else
	{
		user[k].account = user[k].account - x;
		user[a].account = user[a].account + x;
		save();
	}
	system("pause");//冻结屏幕
	system("cls");
	printf("\n\n\n");
	enter2();
}
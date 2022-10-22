# GAME.2.1..1
三子棋棋盘
//放函数定义的

#include "game.h"

void InitBoard(char board[ROW][COL], int row, int col)
{
	int i = 0;
	int j = 0;
	for (i = 0; i < row; i++)
	{
		for (j = 0; j < col; j++)
		{
			board[i][j] = ' ';//将数组初始化为空格
		}
	}
}

//void DispalyBoard(char board[ROW][COL], int row, int col)
//{
//	int i = 0;
//	for (i = 0; i < row; i++)
//	{
//		//1.打印一行数据
//		printf(" %c | %c | %c \n",board[i][0],board[i][1],board[i][2]);
//		//2.打印分割行
//		if (i<row-1)
//		printf("---|---|---\n");
//	}
//}

//优化
void DispalyBoard(char board[ROW][COL], int row, int col)
{
	int i = 0;
	for (i = 0; i < row; i++)
	{
	
		int j = 0;
		for (j = 0; j < col; j++)
		{
		//1.打印一行数据
			printf(" %c ", board[i][j]);
				if(j< col -1)
					printf("|");
		}
		printf("\n");
		//2.打印分割行
		if (i < row - 1)
		{
			for (j = 0; j < col; j++)
			{
				printf("---");
				if (j < col - 1)
				printf("|");
			}
			
		}
		printf("\n");
	}
}

#include <stdio.h>

//放函数声明的
#define ROW 3//定义行
#define COL 3//定义列

//函数声明
void InitBoard(char board[ROW][COL], int row, int col);
void DispalyBoard(char board[ROW][COL], int row, int col);

//测试三子棋游戏


#include "game.h"
void menu()
{
	printf("**************************\n");
	printf("****1.paly   0.exit*******\n");
	printf("**************************\n");
}

void game()
{
	//数组-存放走出的棋盘信息
	char board[ROW][COL] = { 0 };
	//想要全部是空格，初始化棋盘
	InitBoard(board, ROW, COL);
	//打印棋盘
	DispalyBoard(board,ROW,COL);

}

void test()
{
	int input = 0;
	do
	{
		menu();
		printf("请选择:>");
		scanf_s("%d", &input);
		switch(input)
		{
			case 1:
				game();
				break;
			case 0:
					printf("退出游戏\n");
					break;
			default:;
		}
		
	} while (input);
}

int main()
{
	test();
	return 0;
}

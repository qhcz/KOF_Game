#include <conio.h>
#include <graphics.h>
#include <stdio.h>
#include <windows.h>
#include <mmsystem.h>
#pragma comment(lib,"Winmm.lib")

#define high  477  // 游戏画面尺寸
#define width 691
#define N 40


//图片定义//
//开始动画
IMAGE start_anime1;
IMAGE start_anime2;
IMAGE start_anime3;
IMAGE start_anime4;
IMAGE start_anime5;
IMAGE start_anime6;
IMAGE start_anime7;
IMAGE start_anime8;
IMAGE start_anime9;
IMAGE start_anime10;
IMAGE start_anime11;
IMAGE start_anime12;
IMAGE start_anime13;
IMAGE start_anime14;
IMAGE start_anime15;
IMAGE start_anime16;
IMAGE start_anime17;
IMAGE start_anime18;
IMAGE start_anime19;
IMAGE start_anime20;
IMAGE start_anime21;
IMAGE start_anime22;
IMAGE start_anime23;
IMAGE start_anime24;
IMAGE start_anime25;
IMAGE start_anime26;
IMAGE start_anime27;
IMAGE start_anime28;
IMAGE start_anime29;
IMAGE start_anime30;
IMAGE start_anime31;
IMAGE start_anime32;
IMAGE start_anime33;
IMAGE start_anime34;
IMAGE start_anime35;
IMAGE start_anime36;
IMAGE start_anime37;
IMAGE start_anime38;
IMAGE start_anime39;
IMAGE start_anime40;
IMAGE start_anime41;
IMAGE start_anime42;
IMAGE start_anime43;
IMAGE start_anime44;
IMAGE start_anime45;
IMAGE start_anime46;
IMAGE start_anime47;
IMAGE start_anime48;
IMAGE start_anime49;
IMAGE start_anime50;
IMAGE start_anime51;
IMAGE start_anime52;
IMAGE start_anime53;
IMAGE start_anime54;
IMAGE start_anime55;
IMAGE start_anime56;
IMAGE start_anime57;
IMAGE start_anime58;
IMAGE start_anime59;
IMAGE start_anime60;
IMAGE start_anime61;
IMAGE start_anime62;
IMAGE start_anime63;
IMAGE start_anime64;
IMAGE start_anime65;
IMAGE start_anime66;
IMAGE start_anime67;
IMAGE start_anime68;
IMAGE start_anime69;
IMAGE start_anime70;
IMAGE start_anime71;
IMAGE start_anime72;
IMAGE start_anime73;
IMAGE start_anime74;
IMAGE start_anime75;
IMAGE start_anime76;
IMAGE start_anime77;
IMAGE start_anime78;
IMAGE start_anime79;
IMAGE start_anime80;
IMAGE start_anime81;
IMAGE start_anime82;
IMAGE start_anime83;
IMAGE start_anime84;
IMAGE start_anime85;
IMAGE start_anime86;
IMAGE start_anime87;
IMAGE start_anime88;
IMAGE start_anime89;
IMAGE start_anime90;
IMAGE start_anime91;
IMAGE start_anime92;
IMAGE start_anime93;
IMAGE start_anime94;
IMAGE start_anime95;
IMAGE start_anime96;
IMAGE start_anime97;
IMAGE start_anime98;
IMAGE start_anime99;
IMAGE start_anime100;
IMAGE start_anime101;
IMAGE start_anime102;
IMAGE start_anime103;
IMAGE start_anime104;
IMAGE start_anime105;
IMAGE start_anime106;
//人物选择
IMAGE start97;
IMAGE select1;
IMAGE cursor1;
IMAGE cursor2;

void startup();			//游戏初始化（加载图片等等）
void gameover();		//游戏结束（结束绘图）
void video();			//开始动画播放

int start_video(int stage)
{
	if(stage==1)
	{
		video();
		EndBatchDraw();
		stage=2;
	}
	return stage;
}

int start_97(int stage)
{
	if(stage==2)
	{
		char input;
		input=getch();
		while(1)
		{
			putimage(0,0,&start97);
			Sleep(N);
			FlushBatchDraw();
			if(input=='j')			//按下j键进入下一个阶段
				break;	
		}
		EndBatchDraw();
		stage=3;
	}

	return stage;
}

int character_select(int stage)
{
	int select_x=47;				//选人光标初始位置
	int select_y=40;

	if(stage==3)
	{
		char input;
		int a=1;		//用于左右选人时的跳跃判定
		int b=1;		//用于上下选人时的跳跃判定
		while(1)
		{
			if(kbhit())
			{
				input=getch();
				putimage(0,0,&select1);
				putimage(select_x,select_y,&cursor1,SRCAND);
				putimage(select_x,select_y,&cursor2,SRCPAINT);
				//Sleep(N);
				FlushBatchDraw();
				if(input=='j')			//按下j键进入下一个阶段
					break;	
				else if(input=='d' && select_x<570)
				{
					if(a==3 || a==6)
					{
						select_x=select_x+115;
						a++;
					}
					else if(a==4 && b==2)
					{
						if(select_x<560)
						{
							select_x=select_x+107;
							a=a+2;
						}
					}
					else
					{
						select_x=select_x+52;
						a++;
					}	
				}	
				else if(input=='a' && select_x>47)
				{
					if(a==4 || a==7)
					{
						select_x=select_x-115;
						a--;
					}
					else if(a==6 && b==2)
					{
						if(select_x>360)
						{
							select_x=select_x-107;
							a=a-2;
						}
					}
					else
					{
						select_x=select_x-52;
						a--;
					}
				}
				else if(a==4 || a==6)
				{
					if(input=='s' && select_y<300)
					{
						if(b==1)
						{
							select_y=select_y+146;
							b++;
						}
						else
						{
							select_y=select_y+73;
							b++;
						}
					}
					else if(input=='w' && select_y>50)
					{
						if(b==2)
						{
							select_y=select_y-146;
							b--;
						}
						else
						{
							select_y=select_y-73;
							b--;
						}
					}

				}
				else
				{
					if(input=='s' && select_y<150)
						select_y=select_y+73;
					else if(input=='w' && select_y>40)
						select_y=select_y-73;
				}
				/*else if(input=='s' && select_y<150)
					select_y=select_y+73;
				else if(input=='w' && select_y>40)
					select_y=select_y-73;*/
			}
		}
		EndBatchDraw();
		stage=4;
	}

	return stage;
}


int fighting(int stage)
{
	if(stage==4)
	{
		EndBatchDraw();
		stage=5;
	}
	return stage;
}


int ending(int stage)
{

	gameover();
	stage=6;
	return stage;
}


int main()
{
	int s1,s2,s3,s4;	//用于储存游戏下一阶段的变量
	int stage=1;		//定义游戏阶段
	
	startup();
	
	start_video(stage);
	s1=start_video(stage);
	
	start_97(s1);
	s2=start_97(s1);

	character_select(s2);
	s3=character_select(s2);
	
	fighting(s3);
	s4=fighting(s3);
	
	ending(s4);
	return 0;
}




//下面是每个阶段可能用到的		【功能函数】or【代码过长的函数】



void gameover()			//结束绘图函数
{
	EndBatchDraw();
	closegraph();
}



void startup()			//初始化函数
{
	initgraph(width,high);
	
	//开始动画
	loadimage(&start_anime1,".\\1.png");
	loadimage(&start_anime2,".\\2.png");
	loadimage(&start_anime3,".\\3.png");
	loadimage(&start_anime4,".\\4.png");
	loadimage(&start_anime5,".\\5.png");
	loadimage(&start_anime6,".\\6.png");
	loadimage(&start_anime7,".\\7.png");
	loadimage(&start_anime8,".\\8.png");
	loadimage(&start_anime9,".\\9.png");
	loadimage(&start_anime10,".\\10.png");
	loadimage(&start_anime11,".\\11.png");
	loadimage(&start_anime12,".\\12.png");
	loadimage(&start_anime13,".\\13.png");
	loadimage(&start_anime14,".\\14.png");
	loadimage(&start_anime15,".\\15.png");
	loadimage(&start_anime16,".\\16.png");
	loadimage(&start_anime17,".\\17.png");
	loadimage(&start_anime18,".\\18.png");
	loadimage(&start_anime19,".\\19.png");
	loadimage(&start_anime20,".\\20.png");
	loadimage(&start_anime21,".\\21.png");
	loadimage(&start_anime22,".\\22.png");
	loadimage(&start_anime23,".\\23.png");
	loadimage(&start_anime24,".\\24.png");
	loadimage(&start_anime25,".\\25.png");
	loadimage(&start_anime26,".\\26.png");
	loadimage(&start_anime27,".\\27.png");
	loadimage(&start_anime28,".\\28.png");
	loadimage(&start_anime29,".\\29.png");
	loadimage(&start_anime30,".\\30.png");
	loadimage(&start_anime31,".\\31.png");
	loadimage(&start_anime32,".\\32.png");
	loadimage(&start_anime33,".\\33.png");
	loadimage(&start_anime34,".\\34.png");
	loadimage(&start_anime35,".\\35.png");
	loadimage(&start_anime36,".\\36.png");
	loadimage(&start_anime37,".\\37.png");
	loadimage(&start_anime38,".\\38.png");
	loadimage(&start_anime39,".\\39.png");
	loadimage(&start_anime40,".\\40.png");
	loadimage(&start_anime41,".\\41.png");
	loadimage(&start_anime42,".\\42.png");
	loadimage(&start_anime43,".\\43.png");
	loadimage(&start_anime44,".\\44.png");
	loadimage(&start_anime45,".\\45.png");
	loadimage(&start_anime46,".\\46.png");
	loadimage(&start_anime47,".\\47.png");
	loadimage(&start_anime48,".\\48.png");
	loadimage(&start_anime49,".\\49.png");
	loadimage(&start_anime50,".\\50.png");
	loadimage(&start_anime51,".\\51.png");
	loadimage(&start_anime52,".\\52.png");
	loadimage(&start_anime53,".\\53.png");
	loadimage(&start_anime54,".\\54.png");
	loadimage(&start_anime55,".\\55.png");
	loadimage(&start_anime56,".\\56.png");
	loadimage(&start_anime57,".\\57.png");
	loadimage(&start_anime58,".\\58.png");
	loadimage(&start_anime59,".\\59.png");
	loadimage(&start_anime60,".\\60.png");
	loadimage(&start_anime61,".\\61.png");
	loadimage(&start_anime62,".\\62.png");
	loadimage(&start_anime63,".\\63.png");
	loadimage(&start_anime64,".\\64.png");
	loadimage(&start_anime65,".\\65.png");
	loadimage(&start_anime66,".\\66.png");
	loadimage(&start_anime67,".\\67.png");
	loadimage(&start_anime68,".\\68.png");
	loadimage(&start_anime69,".\\69.png");
	loadimage(&start_anime70,".\\70.png");
	loadimage(&start_anime71,".\\71.png");
	loadimage(&start_anime72,".\\72.png");
	loadimage(&start_anime73,".\\73.png");
	loadimage(&start_anime74,".\\74.png");
	loadimage(&start_anime75,".\\75.png");
	loadimage(&start_anime76,".\\76.png");
	loadimage(&start_anime77,".\\77.png");
	loadimage(&start_anime78,".\\78.png");
	loadimage(&start_anime79,".\\79.png");
	loadimage(&start_anime80,".\\80.png");
	loadimage(&start_anime81,".\\81.png");
	loadimage(&start_anime82,".\\82.png");
	loadimage(&start_anime83,".\\83.png");
	loadimage(&start_anime84,".\\84.png");
	loadimage(&start_anime85,".\\85.png");
	loadimage(&start_anime86,".\\86.png");
	loadimage(&start_anime87,".\\87.png");
	loadimage(&start_anime88,".\\88.png");
	loadimage(&start_anime89,".\\89.png");
	loadimage(&start_anime90,".\\90.png");
	loadimage(&start_anime91,".\\91.png");
	loadimage(&start_anime92,".\\92.png");
	loadimage(&start_anime93,".\\93.png");
	loadimage(&start_anime94,".\\94.png");
	loadimage(&start_anime95,".\\95.png");
	loadimage(&start_anime96,".\\96.png");
	loadimage(&start_anime97,".\\97.png");
	loadimage(&start_anime98,".\\98.png");
	loadimage(&start_anime99,".\\99.png");
	loadimage(&start_anime100,".\\100.png");
	loadimage(&start_anime101,".\\101.png");
	loadimage(&start_anime102,".\\102.png");
	loadimage(&start_anime103,".\\103.png");
	loadimage(&start_anime104,".\\104.png");
	loadimage(&start_anime105,".\\105.png");
	loadimage(&start_anime106,".\\106.png");
	//人物选择
	loadimage(&start97,".\\start97.bmp");
	loadimage(&select1,".\\select.png");
	loadimage(&cursor1,".\\透明mask.bmp");
	loadimage(&cursor2,".\\透明.bmp");

	BeginBatchDraw();
}

void video()			//开始动画播放函数
{

	mciSendString("open .\\bkmusic_start.mp3 alias bkmusic", NULL, 0, NULL);//播放背景音乐
	mciSendString("play bkmusic", NULL, 0, NULL);	//播放一次

	int i;
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime1,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime2,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime3,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime4,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime5,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime6,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime7,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime8,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime9,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime10,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime11,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime12,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime13,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime14,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime15,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime16,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime17,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime18,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime19,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime20,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime21,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime22,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime23,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime24,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime25,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime26,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime27,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime28,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime29,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime30,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime31,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime32,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime33,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime34,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime35,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime36,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime37,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime38,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime39,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime40,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime41,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime42,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime43,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime44,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime45,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime46,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime47,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime48,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime49,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime50,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime51,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime52,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime53,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime54,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime55,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime56,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime57,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime58,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime59,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime60,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime61,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime62,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime63,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime64,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime65,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime66,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime67,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime68,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime69,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime70,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime71,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime72,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime73,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime74,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime75,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime76,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime77,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime78,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime79,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime80,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime81,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime82,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime83,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime84,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime85,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime86,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime87,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime88,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime89,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime90,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime91,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime92,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime93,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime94,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime95,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime96,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime97,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime98,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime99,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime100,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime101,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime102,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime103,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}

	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime104,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}

	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime105,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	
	for(i=0;(i<10 && kbhit()!=1);i++)
	{
		clearrectangle(0,0,691,477);
		putimage(0,0,691,477,&start_anime106,i*691,0);
		Sleep(N);
		FlushBatchDraw();
	}
	mciSendString("stop bkmusic", NULL, 0, NULL);		//最后关闭音乐
	mciSendString("close bkmusic", NULL, 0, NULL);		
}

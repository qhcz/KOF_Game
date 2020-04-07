#include <conio.h>
#include <graphics.h>
#include <stdio.h>
#include <windows.h>
#include <mmsystem.h>
#pragma comment(lib,"Winmm.lib")

#define high  477  // 游戏画面尺寸
#define width 691
#define N 40



//定义人物的动作变量


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
	//战斗背景
	IMAGE bk;
	//人物选择
	IMAGE start97;
	IMAGE select1;
	IMAGE cursor1;
	IMAGE cursor2;
	//导入左侧玩家的动作
	IMAGE bashenbenpao1;
	IMAGE bashenzhanli1;
	IMAGE bashenchuchang1;
	IMAGE bashenxiadun1;
	IMAGE bashendazhao1;
	IMAGE bashendazhao2;
	IMAGE bashendazhao3;
	IMAGE bashendazhao4;
	IMAGE bashendazhao5;
	IMAGE bashendazhao6;
	IMAGE bashendazhao7;
	IMAGE bashendazhao8;
	IMAGE bashendazhao9;
	IMAGE bashenerzhao1;
	IMAGE bashenerzhao2;
	IMAGE bashenqianjin1;
	IMAGE bashenhoutui1;
	IMAGE bashenhuibi1;
	IMAGE bashenpugong21;
	IMAGE bashenpugong22;
	IMAGE bashenpugong23;
	IMAGE bashensanzhao1;
	IMAGE bashentiaoyue1;
	IMAGE bashentiaoyue2;
	IMAGE bashentiaoyue3;
	IMAGE bashenpugong11;
	IMAGE bashenpugong12;
	IMAGE bashenpugong13;
	IMAGE bashenpugong14;
	IMAGE bashenbaoqi1;
	IMAGE bashenbaoqi2;
	IMAGE bashenjidao1;
	IMAGE bashenjidao2;
	IMAGE bashenjidao3;
	IMAGE bashenfangshou1;
	IMAGE bashenbenpao2;
	IMAGE bashenzhanli2;
	IMAGE bashenchuchang2;
	IMAGE bashenxiadun2;
	IMAGE bashendazhao;
	IMAGE bashenerzhao;
	IMAGE bashenqianjin;
	IMAGE bashenhoutui;
	IMAGE bashenhuibi;
	IMAGE bashenpugong2;
	IMAGE bashensanzhao;
	IMAGE bashentiaoyue;
	IMAGE bashenpugong1;
	IMAGE bashenbaoqi;
	IMAGE bashenjidao;
	IMAGE bashenfangshou;
	IMAGE bashentiaoyuegai1;
	IMAGE bashentiaoyuegai2;
	//导入左侧玩家的遮罩图
	IMAGE bashenbenpao1_;
	IMAGE bashenzhanli1_;
	IMAGE bashenchuchang1_;
	IMAGE bashenxiadun1_;
	IMAGE bashendazhao1_;
	IMAGE bashendazhao2_;
	IMAGE bashendazhao3_;
	IMAGE bashendazhao4_;
	IMAGE bashendazhao5_;
	IMAGE bashendazhao6_;
	IMAGE bashendazhao7_;
	IMAGE bashendazhao8_;
	IMAGE bashendazhao9_;
	IMAGE bashenerzhao1_;
	IMAGE bashenerzhao2_;
	IMAGE bashenqianjin1_;
	IMAGE bashenhoutui1_;
	IMAGE bashenhuibi1_;
	IMAGE bashenpugong21_;
	IMAGE bashenpugong22_;
	IMAGE bashenpugong23_;
	IMAGE bashensanzhao1_;
	IMAGE bashentiaoyue1_;
	IMAGE bashentiaoyue2_;
	IMAGE bashentiaoyue3_;
	IMAGE bashenpugong11_;
	IMAGE bashenpugong12_;
	IMAGE bashenpugong13_;
	IMAGE bashenpugong14_;
	IMAGE bashenbaoqi1_;
	IMAGE bashenbaoqi2_;
	IMAGE bashenjidao1_;
	IMAGE bashenjidao2_;
	IMAGE bashenjidao3_;
	IMAGE bashenfangshou1_;
	IMAGE bashentiaoyuegai1_;
	IMAGE bashentiaoyuegai2_;
	//导入右侧玩家的动作
	IMAGE kbenpao1;
	IMAGE kbenpao2;
	IMAGE kchuchang1;
	IMAGE kchuchang2;
	IMAGE kchuchang3;
	IMAGE kchuchang4;
	IMAGE kzhanli1;
	IMAGE kxiadun1;
	IMAGE kxiadun2;
	IMAGE kxiadun3;
	IMAGE kdazhao1;
	IMAGE kdazhao2;
	IMAGE kdazhao3;
	IMAGE kdazhao4;
	IMAGE kdazhao5;
	IMAGE kdazhao6;
	IMAGE kdazhao7;
	IMAGE kdazhao8;
	IMAGE kdazhao9;
	IMAGE kdazhao10;
	IMAGE kdazhao11;
	IMAGE kdazhao12;
	IMAGE kdazhao13;
	IMAGE kdazhao14;
	IMAGE kdazhao15;
	IMAGE kdazhao16;
	IMAGE kdazhao17;
	IMAGE kerzhao1;
	IMAGE kerzhao2;
	IMAGE kqianjin1;
	IMAGE kqianjin2;
	IMAGE kqianjin3;
	IMAGE khoutui1;
	IMAGE khoutui2;
	IMAGE khoutui3;
	IMAGE khuibi11;
	IMAGE khuibi21;
	IMAGE kpugong21;
	IMAGE kpugong22;
	IMAGE kpugong23;
	IMAGE ksanzhao1;
	IMAGE ksanzhao2;
	IMAGE ksanzhao3;
	IMAGE ksanzhao4;
	IMAGE ksanzhao5;
	IMAGE ktiaoyue1;
	IMAGE ktiaoyue2;
	IMAGE ktiaoyue3;
	IMAGE kpugong11;
	IMAGE kpugong12;
	IMAGE kbaoqi1;
	IMAGE kbaoqi2;
	IMAGE kbaoqi3;
	IMAGE kjidao1;
	IMAGE kjidao2;
	IMAGE kjidao3;
	IMAGE kfangshou1;
	//导入右侧玩家遮罩图
	IMAGE kbenpao1_;
	IMAGE kbenpao2_;
	IMAGE kchuchang1_;
	IMAGE kchuchang2_;
	IMAGE kchuchang3_;
	IMAGE kchuchang4_;
	IMAGE kzhanli1_;
	IMAGE kxiadun1_;
	IMAGE kxiadun2_;
	IMAGE kxiadun3_;
	IMAGE kdazhao1_;
	IMAGE kdazhao2_;
	IMAGE kdazhao3_;
	IMAGE kdazhao4_;
	IMAGE kdazhao5_;
	IMAGE kdazhao6_;
	IMAGE kdazhao7_;
	IMAGE kdazhao8_;
	IMAGE kdazhao9_;
	IMAGE kdazhao10_;
	IMAGE kdazhao11_;
	IMAGE kdazhao12_;
	IMAGE kdazhao13_;
	IMAGE kdazhao14_;
	IMAGE kdazhao15_;
	IMAGE kdazhao16_;
	IMAGE kdazhao17_;
	IMAGE kerzhao1_;
	IMAGE kerzhao2_;
	IMAGE kqianjin1_;
	IMAGE kqianjin2_;
	IMAGE kqianjin3_;
	IMAGE khoutui1_;
	IMAGE khoutui2_;
	IMAGE khoutui3_;
	IMAGE khuibi11_;
	IMAGE khuibi21_;
	IMAGE kpugong21_;
	IMAGE kpugong22_;
	IMAGE kpugong23_;
	IMAGE ksanzhao1_;
	IMAGE ksanzhao2_;
	IMAGE ksanzhao3_;
	IMAGE ksanzhao4_;
	IMAGE ksanzhao5_;
	IMAGE ktiaoyue1_;
	IMAGE ktiaoyue2_;
	IMAGE ktiaoyue3_;
	IMAGE kpugong11_;
	IMAGE kpugong12_;
	IMAGE kbaoqi1_;
	IMAGE kbaoqi2_;
	IMAGE kbaoqi3_;
	IMAGE kjidao1_;
	IMAGE kjidao2_;
	IMAGE kjidao3_;
	IMAGE kfangshou1_;



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
			}
			putimage(select_x,select_y,&cursor1,SRCAND);
			putimage(select_x,select_y,&cursor2,SRCPAINT);
			FlushBatchDraw();
		}
		EndBatchDraw();
		stage=4;
	}

	return stage;
}


int fighting(int stage)
{	

	int position_x=0,position_y=high*1.3-255;
	int position_x2=width*1.5-200,position_y2=high*1.3-255;
	int left=0,right=0;
	int x=0,y=0;
	char input;
	int key,key2;
	closegraph();
	initgraph(width*1.5,high*1.3);
	putimage(0,0,&bk);
	int i,k;
	
	for(i=0;(i<12 && kbhit()!=1);i++)
	{	
		clearrectangle(position_x,0,position_x+200,position_y+255);
		putimage(0,0,&bk);
		putimage(0,position_y,200,255,&bashenchuchang1_,i*200,0,SRCAND);
		putimage(0,position_y,200,255,&bashenchuchang1,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
		putimage(0,0,&bk);
		putimage(position_x2,position_y2,200,255,&kchuchang4_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang4,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
		putimage(0,0,&bk);
		putimage(position_x2,position_y2,200,255,&kchuchang3_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang3,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
		putimage(0,0,&bk);
		putimage(position_x2,position_y2,200,255,&kchuchang2_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang2,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
		putimage(0,0,&bk);
		putimage(position_x2,position_y2,200,255,&kchuchang1_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang1,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	while(1)
	{
	//添加左侧玩家控制人物的各项动作
		if(kbhit()==0)
		{	
		
				for(i=0;i<9;i++)
			{
				clearrectangle(0,0,691,477);
				putimage(0,0,&bk);
				putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
				putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
				putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
				putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
				FlushBatchDraw();
				Sleep(80);
			}
				
		}


		if(kbhit()!=0)
			{
		
			input=getch();
				
			
			//Sleep(N);	
				if((GetAsyncKeyState(0x41)&0x8000))		//实现八神的后退(左移)动作 a
				{
				
					for(i=0;i<6;i++)
					{
						clearrectangle(position_x,position_y,position_x+150,position_y+255);
						putimage(0,0,&bk);
						if(position_x>=0)	
						{
							position_x=position_x-20;
						}
						putimage(position_x,position_y,150,255,&bashenhoutui1_,i*150,0,SRCAND);
						putimage(position_x,position_y,150,255,&bashenhoutui1,i*150,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
				}
				if(GetAsyncKeyState(0x51)&0x8000)			//实现八神的快速后退 q
				{
					clearrectangle(position_x,position_y,position_x+200,position_y+255);
					putimage(0,0,&bk);
					if(position_x>=0)
					{
						position_x=position_x-20;
					}
					left++;
					putimage(position_x,position_y,200,255,&bashenhoutui1_,left*200,0,SRCAND);
					putimage(position_x,position_y,200,255,&bashenhoutui1,left*200,0,SRCPAINT);
					putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
					FlushBatchDraw();
					if(left==9)
						left=0;	

				}
				
				
				if(GetAsyncKeyState(0x44)&0x8000)		//实现八神的前进 d
				{
					
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+150,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
						position_x=position_x+20;
						}	
						putimage(position_x,position_y,150,255,&bashenqianjin1_,i*150,0,SRCAND);
						putimage(position_x,position_y,150,255,&bashenqianjin1,i*150,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}				
				}
			
				if(GetAsyncKeyState(0x53)&0x8000)		//实现八神的下蹲 s
				{
					for(i=0;i<6;i++)
					{
						clearrectangle(position_x,position_y,position_x+167,position_y+180);
						putimage(0,0,&bk);
						putimage(position_x,position_y+70,167,180,&bashenxiadun1_,i*167,0,SRCAND);
						putimage(position_x,position_y+70,167,180,&bashenxiadun1,i*167,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					} 
					for(i=0;i<9;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}

				}
				
				if(GetAsyncKeyState(0x4B)&0x8000)		//实现八神的跳跃 k
				{
					for(i=0;i<8;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_y>=0)
						{
							position_y=position_y-35;
						}
						putimage(position_x,position_y,200,255,&bashentiaoyuegai1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashentiaoyuegai1,i*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<5;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_y<=high*1.5)
						{
							position_y=position_y+56;
						}
						putimage(position_x,position_y,200,255,&bashentiaoyuegai2_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashentiaoyuegai2,i*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}

				
				}
				if(GetAsyncKeyState(0x4F)&0x8000)		//实现八神的爆气 o
				{
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						putimage(position_x,position_y,200,255,&bashenbaoqi1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenbaoqi1,i*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						putimage(position_x,position_y,200,255,&bashenbaoqi2_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenbaoqi2,i*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
				
				}
				if(GetAsyncKeyState(0x4C)&0x8000)		//实现八神的快速奔跑 l
				{
					clearrectangle(position_x,position_y,position_x+200,position_y+255);
					putimage(0,0,&bk);
					left++;
					position_x=position_x+20;
					putimage(position_x,position_y,200,255,&bashenbenpao1_,left*200,0,SRCAND);
					putimage(position_x,position_y,200,255,&bashenbenpao1,left*200,0,SRCPAINT);
					putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
					FlushBatchDraw();
					if(left==8)
						left=0;		
				}
				if(GetAsyncKeyState(0x55)&0x8000)		//实现八神的大招 u
				{
					for(i=0;i<10;i++)
					{
					clearrectangle(position_x,position_y,position_x+200,position_y+255);
					putimage(0,0,&bk);
					if(position_x<=position_x2-165)
					{
						position_x=position_x+5;
					}
					left++;
					putimage(position_x,position_y,200,255,&bashendazhao1_,left*200,0,SRCAND);
					putimage(position_x,position_y,200,255,&bashendazhao1,left*200,0,SRCPAINT);
					putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
					Sleep(N);
					FlushBatchDraw();
					if(left==10)
						left=0;
					}	
					
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,200,255,&bashendazhao2_,left*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashendazhao2,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						FlushBatchDraw();
						if(left==10)
							left=0;
					}

					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,200,255,&bashendazhao3_,left*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashendazhao3,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						FlushBatchDraw();
						if(left==10)
							left=0;
					}
	
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,155,255,&bashendazhao4_,left*200,0,SRCAND);
						putimage(position_x,position_y,155,255,&bashendazhao4,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						if(left==10)
							left=0;
					}

					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,155,255,&bashendazhao5_,left*200,0,SRCAND);
						putimage(position_x,position_y,155,255,&bashendazhao5,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						FlushBatchDraw();
						if(left==10)
							left=0;
					}
	
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,155,255,&bashendazhao6_,left*200,0,SRCAND);
						putimage(position_x,position_y,155,255,&bashendazhao6,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						FlushBatchDraw();
						if(left==10)
							left=0;
					}
	
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,155,255,&bashendazhao7_,left*200,0,SRCAND);
						putimage(position_x,position_y,155,255,&bashendazhao7,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						FlushBatchDraw();
						if(left==10)
							left=0;
					}
	
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,155,255,&bashendazhao8_,left*200,0,SRCAND);
						putimage(position_x,position_y,155,255,&bashendazhao8,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						FlushBatchDraw();
						if(left==10)
							left=0;
					}

					for(i=0;i<10;i++)
					{

						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						if(position_x<=position_x2-165)
						{
							position_x=position_x+5;
						}
						left++;
						putimage(position_x,position_y,200,255,&bashendazhao9_,left*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashendazhao9,left*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(N);
						FlushBatchDraw();
						if(left==7)
							left=0;
					}
						left=0;

				}
				if(GetAsyncKeyState(0x49)&0x8000)		//实现八神的二招 i
				{
						for(i=0;i<10;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						putimage(position_x,position_y,200,255,&bashenerzhao1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenerzhao1,i*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
						for(i=0;i<9;i++)
					{
						clearrectangle(position_x,position_y,position_x+200,position_y+255);
						putimage(0,0,&bk);
						putimage(position_x,position_y,200,255,&bashenerzhao2_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenerzhao2,i*200,0,SRCPAINT);
						putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
				}
				if(GetAsyncKeyState(0x4A)&0x8000)		//实现八神的普攻 j
				{	
						for(i=0;i<10;i++)
						{
							clearrectangle(position_x,position_y,position_x+150,position_y+255);
							putimage(0,0,&bk);
							if(position_x<=position_x2-165)
							{
								position_x=position_x+5;
							}
							putimage(position_x,position_y,150,255,&bashenpugong11_,i*150,0,SRCAND);
							putimage(position_x,position_y,150,255,&bashenpugong11,i*150,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
						for(i=0;i<10;i++)
						{
							clearrectangle(position_x,position_y,position_x+150,position_y+255);
							putimage(0,0,&bk);
							if(position_x<=position_x2-165)
							{
								position_x=position_x+5;
							}
							putimage(position_x,position_y,150,255,&bashenpugong12_,i*150,0,SRCAND);
							putimage(position_x,position_y,150,255,&bashenpugong12,i*150,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
						for(i=0;i<10;i++)
						{
							clearrectangle(position_x,position_y,position_x+150,position_y+255);
							putimage(0,0,&bk);
							if(position_x<=position_x2-165)
							{
								position_x=position_x+5;
							}
							putimage(position_x,position_y,150,255,&bashenpugong13_,i*150,0,SRCAND);
							putimage(position_x,position_y,150,255,&bashenpugong13,i*150,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
						for(i=0;i<4;i++)
						{
							clearrectangle(position_x,position_y,position_x+150,position_y+255);
							putimage(0,0,&bk);
							if(position_x<=position_x2-165)
							{
								position_x=position_x+5;
							}
							putimage(position_x,position_y,150,255,&bashenpugong14_,i*150,0,SRCAND);
							putimage(position_x,position_y,150,255,&bashenpugong14,i*150,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
				}
			//导入右侧玩家控制的人物的动作
			key=getch();
			
			if(GetAsyncKeyState(VK_LEFT)&0x8000)		//实现k的前进
			{
					for(i=0;i<10;i++)
					{
						clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
						putimage(0,0,&bk);
						if(position_x2>=0)	
						{
							position_x2=position_x2-15;
						}
						putimage(position_x2,position_y2,200,255,&kqianjin1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kqianjin1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
						for(i=0;i<5;i++)
					{
						clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
						putimage(0,0,&bk);
						if(position_x2>=0)	
						{
							position_x2=position_x2-15;
						}
						putimage(position_x2,position_y2,200,255,&kqianjin2_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kqianjin2,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
			}
			if(GetAsyncKeyState(VK_RIGHT)&0x8000)		//实现k的后退
			{
					for(i=5;i<10;i++)
					{
						clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
						putimage(0,0,&bk);
						if(position_x2>=position_x)	
						{
							position_x2=position_x2+15;
						}
						putimage(position_x2,position_y2,200,255,&kqianjin2_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kqianjin2,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=5;i<11;i++)
					{
						clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
						putimage(0,0,&bk);
						if(position_x2>=position_x)	
						{
							position_x2=position_x2+15;
						}
						putimage(position_x2,position_y2,200,255,&kqianjin3_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kqianjin3,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
			}
			if(GetAsyncKeyState(VK_UP)&0x8000)			//实现k的跳跃
			{	
				for(i=0;i<7;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_y2>=0)	
					{
						position_y2=position_y2-30;
					}
					putimage(position_x2,position_y2,200,255,&ktiaoyue2_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&ktiaoyue2,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=5;i<12;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_y2<=high*1.3-255)	
					{
						position_y2=position_y2+30;
					}
					putimage(position_x2,position_y2,200,255,&ktiaoyue3_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&ktiaoyue3,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
			}
			if(GetAsyncKeyState(VK_DOWN)&0x8000)			//k下蹲
			{	
				
				for(i=0;i<2;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2,200,255,&kxiadun1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kxiadun1,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<4;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+100,position_y2+150);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2+100,100,255,&kxiadun2_,i*100,0,SRCAND);
					putimage(position_x2,position_y2+100,100,255,&kxiadun2,i*100,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<4;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2,200,255,&kxiadun3_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kxiadun3,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
			}
			if(GetAsyncKeyState(0x30)&0x8000)			//k释放了大招
			{
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao1,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao2_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao2,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao3_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao3,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao4_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao4,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao5_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao5,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao6_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao6,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao7_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao7,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao8_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao8,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao9_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao9,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao10_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao10,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao11_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao11,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao12_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao12,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao13_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao13,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao14_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao14,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2+12;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao15_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao15,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-12;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao16_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao16,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<12;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{	
						position_x2=position_x2-3;
					}
					putimage(position_x2,position_y2,200,255,&kdazhao17_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kdazhao17,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
			}
			if(GetAsyncKeyState(0x31)&0x8000)
			{
				for(i=0;i<12;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+250,position_y2+300);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2,250,300,&kerzhao1_,i*250,0,SRCAND);
					putimage(position_x2,position_y2,250,300,&kerzhao1,i*250,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<12;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+250,position_y2+300);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2,250,300,&kerzhao2_,i*250,0,SRCAND);
					putimage(position_x2,position_y2,250,300,&kerzhao2,i*250,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
			}
			if(GetAsyncKeyState(0x33)&0x8000)
			{
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{
						position_x2=position_x2-5;
					}
					putimage(position_x2,position_y2,200,255,&ksanzhao1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&ksanzhao1,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{
						position_x2=position_x2-5;
					}
					putimage(position_x2,position_y2,200,255,&ksanzhao2_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&ksanzhao2,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{
						position_x2=position_x2-5;
					}
					putimage(position_x2,position_y2,200,255,&ksanzhao3_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&ksanzhao3,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{
						position_x2=position_x2-5;
					}
					putimage(position_x2,position_y2,200,255,&ksanzhao4_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&ksanzhao4,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<10;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+200,position_y2+255);
					putimage(0,0,&bk);
					if(position_x2>=0)
					{
						position_x2=position_x2-5;
					}
					putimage(position_x2,position_y2,200,255,&ksanzhao5_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&ksanzhao5,i*200,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
			}
			if(GetAsyncKeyState(0x35)&0x8000)
			{
				for(i=0;i<3;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+250,position_y2+300);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2,250,300,&kpugong23_,i*250,0,SRCAND);
					putimage(position_x2,position_y2,250,300,&kpugong23,i*250,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<15;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+300,position_y2+250);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2,300,250,&kpugong22_,i*300,0,SRCAND);
					putimage(position_x2,position_y2,300,250,&kpugong22,i*300,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
				for(i=0;i<2;i++)
				{
					clearrectangle(position_x2,position_y2,position_x2+250,position_y2+300);
					putimage(0,0,&bk);
					putimage(position_x2,position_y2,250,300,&kpugong21_,i*250,0,SRCAND);
					putimage(position_x2,position_y2,250,300,&kpugong21,i*250,0,SRCPAINT);
					Sleep(50);
					FlushBatchDraw();
				}
			}
			}
		
		}
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
	int stage=1;		//定义游戏阶段，其中stage=1的时候对应的是播放开始动画，stage=2的时候是拳皇97的进入界面，stage=3对应的是游戏的选人界
						//stage=4对应的是进入战斗界面
	
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
	//战斗背景的导入
	loadimage(&bk,".\\bk.png");
	//左侧玩家控制的人物动作和战斗效果的导入	
	loadimage(&bashenbenpao1,".\\bashen 1.bmp");
	loadimage(&bashenbenpao1_,".\\bashen1.bmp");
	loadimage(&bashenzhanli1,".\\bashen 2.bmp");
	loadimage(&bashenzhanli1_,".\\bashen2.bmp");
	loadimage(&bashenchuchang1,".\\bashen 3.bmp");
	loadimage(&bashenchuchang1_,".\\bashen3.bmp");
	loadimage(&bashenxiadun1,".\\bashen 4.bmp");
	loadimage(&bashenxiadun1_,".\\bashen4.bmp");
	loadimage(&bashendazhao1,".\\bashen 5.bmp");
	loadimage(&bashendazhao1_,".\\bashen5.bmp");
	loadimage(&bashendazhao2,".\\bashen 6.bmp");
	loadimage(&bashendazhao2_,".\\bashen6.bmp");
	loadimage(&bashendazhao3,".\\bashen 7.bmp");
	loadimage(&bashendazhao3_,".\\bashen7.bmp");
	loadimage(&bashendazhao4,".\\bashen 8.bmp");
	loadimage(&bashendazhao4_,".\\bashen8.bmp");
	loadimage(&bashendazhao5,".\\bashen 9.bmp");
	loadimage(&bashendazhao5_,".\\bashen9.bmp");
	loadimage(&bashendazhao6,".\\bashen 10.bmp");
	loadimage(&bashendazhao6_,".\\bashen10.bmp");
	loadimage(&bashendazhao7,".\\bashen 11.bmp");
	loadimage(&bashendazhao7_,".\\bashen11.bmp");
	loadimage(&bashendazhao8,".\\bashen 12.bmp");
	loadimage(&bashendazhao8_,".\\bashen12.bmp");
	loadimage(&bashendazhao9,".\\bashen 13.bmp");
	loadimage(&bashendazhao9_,".\\bashen13.bmp");
	loadimage(&bashenerzhao1,".\\bashen 14.bmp");
	loadimage(&bashenerzhao1_,".\\bashen14.bmp");
	loadimage(&bashenerzhao2,".\\bashen 15.bmp");
	loadimage(&bashenerzhao2_,".\\bashen15.bmp");
	loadimage(&bashenqianjin1,".\\bashen 16.bmp");
	loadimage(&bashenqianjin1_,".\\bashen16.bmp");
	loadimage(&bashenhoutui1,".\\bashen 17.bmp");
	loadimage(&bashenhoutui1_,".\\bashen17.bmp");
	loadimage(&bashenhuibi1,".\\bashen 18.bmp");
	loadimage(&bashenhuibi1_,".\\bashen18.bmp");
	loadimage(&bashenpugong21,".\\bashen 19.bmp");
	loadimage(&bashenpugong21_,".\\bashen19.bmp");
	loadimage(&bashenpugong22,".\\bashen 20.bmp");
	loadimage(&bashenpugong22_,".\\bashen20.bmp");
	loadimage(&bashenpugong23,".\\bashen 21.bmp");
	loadimage(&bashenpugong23_,".\\bashen21.bmp");
	loadimage(&bashensanzhao1,".\\bashen 22.bmp");
	loadimage(&bashensanzhao1_,".\\bashen22.bmp");
	loadimage(&bashentiaoyue1,".\\bashen 23.bmp");
	loadimage(&bashentiaoyue1_,".\\bashen23.bmp");
	loadimage(&bashentiaoyue2,".\\bashen 24.bmp");
	loadimage(&bashentiaoyue2_,".\\bashen24.bmp");
	loadimage(&bashentiaoyue3,".\\bashen 25.bmp");
	loadimage(&bashentiaoyue3_,".\\bashen25.bmp");
	loadimage(&bashenpugong11,".\\bashen 26.bmp");
	loadimage(&bashenpugong11_,".\\bashen26.bmp");
	loadimage(&bashenpugong12,".\\bashen 27.bmp");
	loadimage(&bashenpugong12_,".\\bashen27.bmp");
	loadimage(&bashenpugong13,".\\bashen 28.bmp");
	loadimage(&bashenpugong13_,".\\bashen28.bmp");
	loadimage(&bashenpugong14,".\\bashen 29.bmp");
	loadimage(&bashenpugong14_,".\\bashen29.bmp");
	loadimage(&bashenbaoqi1,".\\bashen 30.bmp");
	loadimage(&bashenbaoqi1_,".\\bashen30.bmp");
	loadimage(&bashenbaoqi2,".\\bashen 31.bmp");
	loadimage(&bashenbaoqi2_,".\\bashen31.bmp");
	loadimage(&bashenjidao1,".\\bashen 32.bmp");
	loadimage(&bashenjidao1_,".\\bashen32.bmp");
	loadimage(&bashenjidao2,".\\bashen 33.bmp");
	loadimage(&bashenjidao2_,".\\bashen33.bmp");
	loadimage(&bashenjidao3,".\\bashen 34.bmp");
	loadimage(&bashenjidao3_,".\\bashen34.bmp");
	loadimage(&bashenfangshou1,".\\bashen 35.bmp");
	loadimage(&bashenfangshou1_,".\\bashen35.bmp");
	loadimage(&bashentiaoyuegai1,".\\bashen 36.bmp");
	loadimage(&bashentiaoyuegai1_,".\\bashen36.bmp");
	loadimage(&bashentiaoyuegai2,".\\bashen 37.bmp");
	loadimage(&bashentiaoyuegai2_,".\\bashen37.bmp");
	//右侧玩家控制的人物的动作和战斗效果导入
	loadimage(&kbenpao1,".\\k 1.bmp");
	loadimage(&kbenpao1_,".\\k1.bmp");
	loadimage(&kbenpao2,".\\k 2.bmp");
	loadimage(&kbenpao2_,".\\k2.bmp");
	loadimage(&kchuchang1,".\\k 3.bmp");
	loadimage(&kchuchang1_,".\\k3.bmp");
	loadimage(&kchuchang2,".\\k 4.bmp");
	loadimage(&kchuchang2_,".\\k4.bmp");
	loadimage(&kchuchang3,".\\k 5.bmp");
	loadimage(&kchuchang3_,".\\k5.bmp");
	loadimage(&kchuchang4,".\\k 6.bmp");
	loadimage(&kchuchang4_,".\\k6.bmp");
	loadimage(&kzhanli1,".\\k 60.bmp");
	loadimage(&kzhanli1_,".\\k60.bmp");
	loadimage(&kdazhao1,".\\k 8.bmp");
	loadimage(&kdazhao1_,".\\k8.bmp");	
	loadimage(&kdazhao2,".\\k 9.bmp");
	loadimage(&kdazhao2_,".\\k9.bmp");
	loadimage(&kdazhao3,".\\k 10.bmp");
	loadimage(&kdazhao3_,".\\k10bmp");
	loadimage(&kdazhao4,".\\k 11.bmp");
	loadimage(&kdazhao4_,".\\k11.bmp");
	loadimage(&kdazhao5,".\\k 12.bmp");
	loadimage(&kdazhao5_,".\\k12.bmp");
	loadimage(&kdazhao6,".\\k 13.bmp");
	loadimage(&kdazhao6_,".\\k13.bmp");
	loadimage(&kdazhao7,".\\k 14.bmp");
	loadimage(&kdazhao7_,".\\k14.bmp");	
	loadimage(&kdazhao8,".\\k 15.bmp");
	loadimage(&kdazhao8_,".\\k15.bmp");
	loadimage(&kdazhao9,".\\k 16.bmp");
	loadimage(&kdazhao9_,".\\k16.bmp");
	loadimage(&kdazhao10,".\\k 17.bmp");
	loadimage(&kdazhao10_,".\\k17.bmp");
	loadimage(&kdazhao11,".\\k 18.bmp");
	loadimage(&kdazhao11_,".\\k18.bmp");
	loadimage(&kdazhao12,".\\k 19.bmp");
	loadimage(&kdazhao12_,".\\k19.bmp");
	loadimage(&kdazhao13,".\\k 20.bmp");
	loadimage(&kdazhao13_,".\\k20.bmp");	
	loadimage(&kdazhao14,".\\k 21.bmp");
	loadimage(&kdazhao14_,".\\k21.bmp");
	loadimage(&kdazhao15,".\\k 22.bmp");
	loadimage(&kdazhao15_,".\\k22.bmp");
	loadimage(&kdazhao16,".\\k 23.bmp");
	loadimage(&kdazhao16_,".\\k23.bmp");
	loadimage(&kdazhao17,".\\k 24.bmp");
	loadimage(&kdazhao17_,".\\k24.bmp");
	loadimage(&kqianjin1,".\\k 25.bmp");
	loadimage(&kqianjin1_,".\\k25.bmp");
	loadimage(&kqianjin2,".\\k 26.bmp");
	loadimage(&kqianjin2_,".\\k26.bmp");
	loadimage(&kqianjin3,".\\k 27.bmp");
	loadimage(&kqianjin3_,".\\k27.bmp");
	loadimage(&khuibi11,".\\k 30.bmp");
	loadimage(&khuibi11_,".\\k30.bmp");
	loadimage(&khuibi21,".\\k 31.bmp");
	loadimage(&khuibi21_,".\\k31.bmp");
	loadimage(&ksanzhao1,".\\k 32.bmp");
	loadimage(&ksanzhao1_,".\\k32.bmp");
	loadimage(&ksanzhao2,".\\k 33.bmp");
	loadimage(&ksanzhao2_,".\\k33.bmp");
	loadimage(&ksanzhao3,".\\k 34.bmp");
	loadimage(&ksanzhao3_,".\\k34.bmp");
	loadimage(&ksanzhao4,".\\k 35.bmp");
	loadimage(&ksanzhao4_,".\\k35.bmp");	
	loadimage(&ksanzhao5,".\\k 36.bmp");
	loadimage(&ksanzhao5_,".\\k36.bmp");
	loadimage(&ktiaoyue1,".\\k 37.bmp");
	loadimage(&ktiaoyue1_,".\\k37.bmp");
	loadimage(&ktiaoyue2,".\\k 38.bmp");
	loadimage(&ktiaoyue2_,".\\k38.bmp");
	loadimage(&ktiaoyue3,".\\k 39.bmp");
	loadimage(&ktiaoyue3_,".\\k39.bmp");
	loadimage(&kpugong11,".\\k 40.bmp");
	loadimage(&kpugong11_,".\\k40.bmp");
	loadimage(&kpugong12,".\\k 41.bmp");
	loadimage(&kpugong12_,".\\k41.bmp");	
	loadimage(&kjidao1,".\\k 42.bmp");
	loadimage(&kjidao1_,".\\k42.bmp");
	loadimage(&kjidao2,".\\k 43.bmp");
	loadimage(&kjidao2_,".\\k43.bmp");
	loadimage(&kjidao3,".\\k 44.bmp");
	loadimage(&kjidao3_,".\\k44.bmp");
	loadimage(&kfangshou1,".\\k 45.bmp");
	loadimage(&kfangshou1_,".\\k45.bmp");
	loadimage(&kxiadun1,".\\k 46.bmp");
	loadimage(&kxiadun1_,".\\k46.bmp");
	loadimage(&kxiadun2,".\\k 47.bmp");
	loadimage(&kxiadun2_,".\\k47.bmp");	
	loadimage(&kxiadun3,".\\k 48.bmp");
	loadimage(&kxiadun3_,".\\k48.bmp");
	loadimage(&kerzhao1,".\\k 49.bmp");
	loadimage(&kerzhao1_,".\\k49.bmp");
	loadimage(&kerzhao2,".\\k 50.bmp");
	loadimage(&kerzhao2_,".\\k50.bmp");
	loadimage(&khoutui1,".\\k 51.bmp");
	loadimage(&khoutui1_,".\\k51.bmp");
	loadimage(&khoutui2,".\\k 52.bmp");
	loadimage(&khoutui2_,".\\k52.bmp");
	loadimage(&khoutui3,".\\k 53.bmp");
	loadimage(&khoutui3_,".\\k53.bmp");	
	loadimage(&kbaoqi2,".\\k 54.bmp");
	loadimage(&kbaoqi2_,".\\k54.bmp");
	loadimage(&kbaoqi3,".\\k 55.bmp");
	loadimage(&kbaoqi3_,".\\k55.bmp");
	loadimage(&kpugong21,".\\k 56.bmp");
	loadimage(&kpugong21_,".\\k56.bmp");
	loadimage(&kpugong22,".\\k 57.bmp");
	loadimage(&kpugong22_,".\\k57.bmp");
	loadimage(&kpugong23,".\\k 58.bmp");
	loadimage(&kpugong23_,".\\k58.bmp");
	loadimage(&kbaoqi1,".\\k 59.bmp");
	loadimage(&kbaoqi1_,".\\k59.bmp");
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

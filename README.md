#include <conio.h>
#include <graphics.h>
#include <stdio.h>
#include <windows.h>
#include <mmsystem.h>
#include<time.h>
#pragma comment(lib,"Winmm.lib")


/***********************************************定义全局变量***********************************************************/
#define high  477  // 游戏画面尺寸
#define width 691
#define N 40

int blood1,blood2;//定义两个玩家的初始血量
int energy1,energy2;//定义两个玩家的初始能量
int flag;		//定义用于防止闪屏的变量
int choice;		//定义记录回合的变量
int result;		//定义掷色子结果的变量
int position_x,position_y;	//记录P1的位置的变量
int position_x2,position_y2;//记录P2的位置的变量
int left,right;			//记录图片遍历时樟树
int position_y3;		//记录审判之剑的竖直方向坐标
int bashendazhao,kdazhao;//记录P1和P2大招的有无
int time1,time2;		//记录玩家使用技能的次数
int note1,note2;		//用于计算加血数量的变量



/****************************************图片定义****************************************/
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
	IMAGE cursor1_p1;
	IMAGE cursor2_p1;
	IMAGE cursor1_p2;
	IMAGE cursor2_p2;
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
	IMAGE bashenbaoqi21;
	IMAGE bashenbaoqi22;
	IMAGE bashenbaoqi23;
	IMAGE bashenbaoqi24;
	IMAGE bashenbaoqi25;
	IMAGE bashenbaoqi26;
	IMAGE bashenbaoqi27;
	IMAGE bashenbaoqi28;
	IMAGE bashenjidao1;
	IMAGE bashenjidao2;
	IMAGE bashenjidao3;
	IMAGE bashenfangshou1;
	IMAGE bashenbenpao2;
	IMAGE bashenzhanli2;
	IMAGE bashenchuchang2;
	IMAGE bashenxiadun2;
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
	IMAGE bashenbaoqi21_;
	IMAGE bashenbaoqi22_;
	IMAGE bashenbaoqi23_;
	IMAGE bashenbaoqi24_;
	IMAGE bashenbaoqi25_;
	IMAGE bashenbaoqi26_;
	IMAGE bashenbaoqi27_;
	IMAGE bashenbaoqi28_;
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
	IMAGE kbaoqi21;
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
	IMAGE kbaoqi21_;
	IMAGE kjidao1_;
	IMAGE kjidao2_;
	IMAGE kjidao3_;
	IMAGE kfangshou1_;
	//定义血条,箭头，能量条等标志性图片
	IMAGE xuetiao1;
	IMAGE xuetiao2;
	IMAGE xuetiao3;
	IMAGE xuetiao4;
	IMAGE xuetiao5;
	IMAGE xuetiao6;
	IMAGE xuetiao7;
	IMAGE xuetiao8;
	IMAGE xuetiao9;
	IMAGE xuetiao10;
	IMAGE xuetiao11;
	IMAGE xuetiao12;
	IMAGE xuetiao13;
	IMAGE xuetiao14;
	IMAGE xuetiao15;
	IMAGE xuetiao16;
	IMAGE xuetiao17;
	IMAGE xuetiao18;
	IMAGE xuetiao19;
	IMAGE xuetiao20;
	IMAGE energy_1;
	IMAGE energy_2;
	IMAGE energy3;
	IMAGE energy4;
	IMAGE energy5;
	IMAGE energy6;
	IMAGE energy7;
	IMAGE energy8;
	IMAGE energy9;
	IMAGE energy10;
	IMAGE energy11;
	IMAGE energy12;
	IMAGE energy13;
	IMAGE energy14;
	IMAGE energy15;
	IMAGE energy16;
	IMAGE energy17;
	IMAGE energy18;
	IMAGE energy19;
	IMAGE energy20;
	IMAGE siwangshenpan1;
	IMAGE siwangshenpan2;
	IMAGE bashensiwang;
	IMAGE ksiwang;
	IMAGE bkending;
	IMAGE zuojiantou;
	IMAGE zuojiantou_;
	IMAGE youjiantou;
	IMAGE youjiantou_;
	IMAGE dazhao;
	IMAGE dazhao_;
	IMAGE bashenshengli;
	IMAGE kshengli;
	//加入开头说明的背景，使玩家更易理解游戏玩法
	IMAGE shuoming1;
	IMAGE shuoming2;
	IMAGE shuoming3;
	IMAGE shuoming4;
	//加入色子的随机数效果，从而使先手的确定更加公平
	IMAGE shaizi1;
	IMAGE shaizi2;
	IMAGE shaizi3;
	IMAGE shaizi4;
	IMAGE shaizi5;
	IMAGE shaizi6;
	//游戏结束时的箭头
	IMAGE ending_cursor1;
	IMAGE ending_cursor2;
	
/*******************************************函数声明***************************************************/


	void startup();			//游戏初始化（加载图片等等）
	void gameover();		//游戏结束（结束绘图）
	void video();			//开始动画播放
	void bloodshowbashen(int blood1);//显示左侧玩家的血量
	void bloodshowk(int blood2);	//显示右侧玩家的血量
	void energyshowbashen(int energy1);//显示左侧玩家的能量
	void energyshowk(int energy2);//显示右侧玩家的能量
	void emerge();				//显示出场动画
	void round(int choice);	//定义显示回合的箭头的函数
	void bigskill(int bashendazhao,int kdazhao);//添加大招标记
	int bloodplus(int dazhao,int blood,int time,int note);//回血函数
	void pictureloading();		//图片加载函数
	void startvideo();			//开头动画播放函数
	void start_97();			//拳皇97待定界面播放函数
	void character_select();	//人物选择界面播放函数
	void explain();				//游戏玩法及操作说明函数
	int  first();				//先手判定函数
	void fighting();			//战斗函数
	int ending();				//游戏结束时的函数
	

void startup()			//初始化函数
{

	blood1=10,blood2=10;//定义两个玩家的初始血量
	energy1=5,energy2=5;//定义两个玩家的初始能量
	flag=1;				//用于防止闪屏的变量
	choice=1;			//任务选择变量
	result=0;			//掷色子结果变量
	position_x=0,position_y=high*1.3-255;//P1位置
	position_x2=width*1.5-200,position_y2=high*1.3-255;//P2位置
	left=0,right=0;		//遍历图片的初始变量
	position_y3=0;		//审判之剑纵坐标
	bashendazhao=0,kdazhao=0;//大招判定
	time1=0,time2=0;	//技能使用次数判定
	note1=time1,note2=time2;//加血函数判定
	initgraph(width,high);
	pictureloading();//图片加载函数
	BeginBatchDraw();
	startvideo();//开头动画播放
	start_97();	//97画面
	character_select(); //人物选择画面
	explain();//玩法说明
	
}



void show()//游戏显示
{
	//注：下面之所以将其中一些变量又一次初始化，是因为while循环中只有show函数，没有startup函数为了让玩家可以一直玩下去，因此如此
	blood1=10,blood2=10;
	energy1=5,energy2=5;
	flag=1;
	choice=1;	
	result=0;
	position_x=0,position_y=high*1.3-255;
	position_x2=width*1.5-200,position_y2=high*1.3-255;
	left=0,right=0;
	position_y3=0;
	bashendazhao=0,kdazhao=0;
	time1=0,time2=0;
	note1=time1,note2=time2;
	first();
	bloodshowbashen(blood1);
	bloodshowk(blood2);
	energyshowbashen(energy1);
	energyshowk(energy2);
	round(choice);
	bigskill(bashendazhao,kdazhao);		
}


void updataWithoutInput()//用户无关设置
{
	bloodplus(bashendazhao,blood1,time1,note1);//P1加血函数
	bloodplus(kdazhao,blood2,time2,note2);//P2加血函数
}



void updataWithInput()//用户有关设置
{
	fighting();//战斗
}


void gameover()
{
	EndBatchDraw();
	closegraph();
	ShowWindow(FindWindow("ConsoleWindowClass",NULL),SW_HIDE);
	exit(0);
}

int ending()
{
	char input;
	input=getch();

	int a=1;			//用来判断光标是否选择退出
	int x=-100;
	int y=-50;

	while(1)
	{	
		if(kbhit())
		{
			input=getch();
			putimage(0,0,&bkending);
			if(input=='s' && y>=-50 && y<20)
			{
				y=y+70;
				a--;
			}
			else if(input=='w' && y>-50 && y<=20)
			{
				y=y-70;
				a++;
			}
			else if(a==1 && input=='y')				//游戏结束
			{
				gameover();
			}
													//按“y”键进行选择
			else if(a==0 && input=='y')				//实现了光标只能在两个选项中移动
			{
				break;
			}
		}
		putimage(x,y,&ending_cursor1,SRCAND);
		putimage(x,y,&ending_cursor2,SRCPAINT);
		FlushBatchDraw();
	}
	flag=0;

	return flag;
}

int main()
{
	ShowWindow(FindWindow("ConsoleWindowClass",NULL),SW_HIDE);
	startup();//数据初始化
	while(1)//游戏循环 
	{
		show();//游戏显示 
		updataWithoutInput();//用户无关设置 
		updataWithInput(); //用户有关设置 
	} 
	gameover();
	return 0; 
} 


/**************************************一些功能函数******************************************/ 


void bloodshowbashen(int blood1)//P1的血量显示函数，共有十滴血，通过blood1的多少进行判定从而显示对应的图片
{	
	if(blood1==1)
	{
		putimage(5,5,&xuetiao1);
	}
	if(blood1==2)
	{
		putimage(5,5,&xuetiao2);
	}
	if(blood1==3)
	{
		putimage(5,5,&xuetiao3);
	}
	if(blood1==4)
	{
		putimage(5,5,&xuetiao4);
	}
	if(blood1==5)
	{
		putimage(5,5,&xuetiao5);
	}
	if(blood1==6)
	{
		putimage(5,5,&xuetiao6);
	}
	if(blood1==7)
	{
		putimage(5,5,&xuetiao7);
	}
	if(blood1==8)
	{
		putimage(5,5,&xuetiao8);
	}
	if(blood1==9)
	{
		putimage(5,5,&xuetiao9);
	}
	if(blood1>=10)
	{
		putimage(5,5,&xuetiao10);
	}
}


void bloodshowk(int blood2)//P2的血量显示函数，共有十滴血，通过blood2的多少进行判定从而显示对应的图片
{

	if(blood2==1)
	{
		putimage(600,5,&xuetiao11);
	}
	if(blood2==2)
	{
		putimage(600,5,&xuetiao12);
	}
	if(blood2==3)
	{
		putimage(600,5,&xuetiao13);
	}
	if(blood2==4)
	{
		putimage(600,5,&xuetiao14);
	}
	if(blood2==5)
	{
		putimage(600,5,&xuetiao15);
	}
	if(blood2==6)
	{
		putimage(600,5,&xuetiao16);
	}
	if(blood2==7)
	{
		putimage(600,5,&xuetiao17);
	}
	if(blood2==8)
	{
		putimage(600,5,&xuetiao18);
	}
	if(blood2==9)
	{
		putimage(600,5,&xuetiao19);
	}
	if(blood2>=10)
	{
		putimage(600,5,&xuetiao20);
	}
}


void energyshowbashen(int energy1)//P1的能量函数，共有十个能量，通过energy1的多少进行判定从而显示对应的图片
{
	if(energy1<=1)
	{
		putimage(5,40,&energy_1);
	}
	if(energy1==2)
	{
		putimage(5,40,&energy_2);
	}
	if(energy1==3)
	{
		putimage(5,40,&energy3);
	}
	if(energy1==4)
	{
		putimage(5,40,&energy4);
	}
	if(energy1==5)
	{
		putimage(5,40,&energy5);
	}
	if(energy1==6)
	{
		putimage(5,40,&energy6);
	}
	if(energy1==7)
	{
		putimage(5,40,&energy7);
	}
	if(energy1==8)
	{
		putimage(5,40,&energy8);
	}
	if(energy1==9)
	{
		putimage(5,40,&energy9);
	}
	if(energy1>=10)
	{
		putimage(5,40,&energy10);
	}
}


void energyshowk(int energy2)//P2的能量函数，共有十个能量，通过energy2的多少进行判定从而显示对应的图片
{
	if(energy2<=1)
	{
		putimage(600,40,&energy11);
	}
	if(energy2==2)
	{
		putimage(600,40,&energy12);
	}
	if(energy2==3)
	{
		putimage(600,40,&energy13);
	}
	if(energy2==4)
	{
		putimage(600,40,&energy14);
	}
	if(energy2==5)
	{
		putimage(600,40,&energy15);
	}
	if(energy2==6)
	{
		putimage(600,40,&energy16);
	}
	if(energy2==7)
	{
		putimage(600,40,&energy17);
	}
	if(energy2==8)
	{
		putimage(600,40,&energy18);
	}
	if(energy2==9)
	{
		putimage(600,40,&energy19);
	}
	if(energy2>=10)
	{
		putimage(600,40,&energy20);
	}
}


void round(int choice)//判定是谁的回合从而显示对应箭头的方向
{
	if(choice==1)//如果choice=1，则是P1的回合
	{
		putimage(380,30,255,194,&zuojiantou_,0,0,SRCAND);//显示左箭头
		putimage(380,30,255,194,&zuojiantou,0,0,SRCPAINT);
	}
	if(choice==2)//如果choice=2，则是P2的回合
	{
		putimage(380,30,255,194,&youjiantou_,0,0,SRCAND);//显示右箭头
		putimage(380,30,255,194,&youjiantou,0,0,SRCPAINT);
	}
}


void bigskill(int bashendazhao,int kdazhao)//显示大招有无的函数
{
	if(bashendazhao==1)//判定P1大招的有无
	{
		putimage(30,70,30,20,&dazhao_,0,0,SRCAND);//在P1的血条下方显示标记
		putimage(30,70,30,20,&dazhao,0,0,SRCPAINT);
	}
	if(kdazhao==1)
	{
		putimage(width*1.5-120,70,30,20,&dazhao_,0,0,SRCAND);//在P2的血条下方显示标记
		putimage(width*1.5-120,70,30,20,&dazhao,0,0,SRCPAINT);
	}
}


int bloodplus(int dazhao,int blood,int time,int note)//加血函数
{
	if(dazhao==1)//通过传入bashendazhao，和kdazhao，如果为1则每回合加一滴血，否则不加
	{
		blood=blood+time-note;
	}
	return blood;
}


void start_97()			//97界面
{
	char input;
	input=getch();
	while(1)
	{
		putimage(0,0,&start97);	//载入97界面的图片
		Sleep(N);
		FlushBatchDraw();
		if(input=='j')			//按下j键进入下一个阶段
			break;	
	}
	EndBatchDraw();	
}


void character_select()		//人物选择函数
{
	int select_x_p1=0;				//选人光标初始位置
	int select_y_p1=5;
	int select_x_p2=0;
	int select_y_p2=5;
	char input;
	while(1)
	{
		if(kbhit())
		{
			input=getch();
			putimage(0,0,&select1);
			//p1操作
			if(input=='y')								//按下y键进入下一个阶段
				break;	
			else if(GetAsyncKeyState(0x44) & 0x8000 && select_x_p1<270)			//光标的移动限制
				select_x_p1=select_x_p1+54;
			else if(GetAsyncKeyState(0x41) & 0x8000 && select_x_p1>0)
				select_x_p1=select_x_p1-54;
			else if(GetAsyncKeyState(0x53) & 0x8000 && select_y_p1<264)
				select_y_p1=select_y_p1+66;
			else if(GetAsyncKeyState(0x57) & 0x8000 && select_y_p1>5)
				select_y_p1=select_y_p1-66;

			//p2操作
			else if(GetAsyncKeyState(VK_RIGHT) & 0x8000 && select_x_p2<270)			//光标的移动限制
				select_x_p2=select_x_p2+54/2;
			else if(GetAsyncKeyState(VK_LEFT) & 0x8000 && select_x_p2>0)
				select_x_p2=select_x_p2-54/2;
			else if(GetAsyncKeyState(VK_DOWN) & 0x8000 && select_y_p2<264)
				select_y_p2=select_y_p2+66/2;
			else if(GetAsyncKeyState(VK_UP) & 0x8000 && select_y_p2>5)
				select_y_p2=select_y_p2-66/2;
		}
		//p1光标
		putimage(select_x_p1,select_y_p1,&cursor1_p1,SRCAND);
		putimage(select_x_p1,select_y_p1,&cursor2_p1,SRCPAINT);
		//p2光标
		putimage(select_x_p2,select_y_p2,&cursor1_p2,SRCAND);
		putimage(select_x_p2,select_y_p2,&cursor2_p2,SRCPAINT);
		FlushBatchDraw();
	}
	EndBatchDraw();
}


void explain()
{	
	char input;
	int sign=1;//定义变量使得在四张说明图片放完后可以跳出函数进入下一个阶段
	initgraph(width*1.5,high*1.3);
	if(sign==1)
	{
		input=getch();
		if(input=='j')//按下J依次播放说明图片
		putimage(0,0,&shuoming1);	
		input=getch();
		if(input=='j')
		putimage(0,0,&shuoming2);
		input=getch();
		if(input=='j')
		putimage(0,0,&shuoming3);
		input=getch();
		if(input=='j')
		putimage(0,0,&shuoming4);
		input=getch();
		if(input=='j')
		sign=0;	//sign=0，跳出说明界面
	}

}


int first()
{
	putimage(0,0,&bk);
	int i=1;
	
	char input;
	srand ( (unsigned) time (NULL) );	//这是一个很有用的语句，防止伪随机数，需要种下“种子”
	while(result>6||result<=0)		
	{
		result=rand()%7;		//进行随机，选出0-6中的一个任意数
	}
	
	input=getch();
	if(input=='j')		//按下J键播放色子随机的动画
	{
		for(i=1;i<=6;i++)
		{
			putimage(500,310,&shaizi1);
			Sleep(50);
			putimage(500,310,&shaizi2);
			Sleep(50);
			putimage(500,310,&shaizi3);
			Sleep(50);
			putimage(500,310,&shaizi4);
			Sleep(50);
			putimage(500,310,&shaizi5);
			Sleep(50);
			putimage(500,310,&shaizi6);
			Sleep(50);
		}
	}	
		//播放完动画之后按照上面得到的0-6的随机数，显示对应色子点数的图片
		if(result==1)
		{
			putimage(500,310,&shaizi1);
			choice=1;
		}
		if(result==2)
		{
			putimage(500,310,&shaizi2);
			choice=1;
		}
		if(result==3)
		{
			putimage(500,310,&shaizi3);
			choice=1;
		}
		if(result==4)
		{
			putimage(500,310,&shaizi4);
			choice=2;
		}
		if(result==5)
		{
			putimage(500,310,&shaizi5);
			choice=2;
		}
		if(result==6)
		{
			putimage(500,310,&shaizi6);
			choice=2;
		}
			
	input=getch();
	if(input=='j')	//再次按下J键，跳出该环节，进入下一个函数
	{
		return 0;
	}
	return 0;
}

/**************************************战斗函数****************************************/ 

void fighting()		//战斗函数
{	
	char input;		//用于记录键入的字符
	int sign=1;		//防止闪屏的变量
	initgraph(width*1.5,high*1.3);//开一个更大的画布
	putimage(0,0,&bk);//放置背景
	fillrectangle(10,0,60,20);
	int i;
	mciSendString("open .\\bkmusic_start.mp3 alias bkmusic", NULL, 0, NULL);//播放背景音乐
	mciSendString("play bkmusic", NULL, 0, NULL);	//播放一次
		
	//播放P1，P2的出场动画
		for(i=0;(i<12 && kbhit()!=1);i++)
	{	
		putimage(0,0,&bk);
		bloodshowbashen(blood1);
		bloodshowk(blood2);
		energyshowbashen(energy1);
		energyshowk(energy2);
		putimage(0,position_y,200,255,&bashenchuchang1_,i*200,0,SRCAND);
		putimage(0,position_y,200,255,&bashenchuchang1,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		putimage(0,0,&bk);
		bloodshowbashen(blood1);
		bloodshowk(blood2);
		energyshowbashen(energy1);
		energyshowk(energy2);
		putimage(position_x2,position_y2,200,255,&kchuchang4_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang4,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		putimage(0,0,&bk);
		bloodshowbashen(blood1);
		bloodshowk(blood2);
		energyshowbashen(energy1);
		energyshowk(energy2);
		putimage(position_x2,position_y2,200,255,&kchuchang3_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang3,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		putimage(0,0,&bk);
		bloodshowbashen(blood1);
		bloodshowk(blood2);
		energyshowbashen(energy1);
		energyshowk(energy2);
		putimage(position_x2,position_y2,200,255,&kchuchang2_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang2,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	for(i=9;(i>=0 && kbhit()!=1);i--)
	{	
		putimage(0,0,&bk);
		bloodshowbashen(blood1);
		bloodshowk(blood2);
		energyshowbashen(energy1);
		energyshowk(energy2);
		putimage(position_x2,position_y2,200,255,&kchuchang1_,i*200,0,SRCAND);
		putimage(position_x2,position_y2,200,255,&kchuchang1,i*200,0,SRCPAINT);
		Sleep(N);
		FlushBatchDraw();
	}
	//进入战斗循环
	while(flag==1)//当flag=1的时候会在战斗中，这样就可以保障即使其中一方已经死亡也不会一直进行循环
	{
	while(sign==1)//用与死亡判定的变量，当sign=1的时候可以战斗，若其中一方死亡，sign=0，之后会跳出这个while循环，从而播放胜利结算
	{
			blood1=bloodplus(bashendazhao,blood1,time1,note1);//P1加血
			blood2=bloodplus(kdazhao,blood2,time2,note2);	//P2加血
			note1=time1;
			note2=time2;
			if(blood1<=0)//判定P1已经死亡
			{
					if(position_y3<=high*1.3-380)
				{
					for(i=0;i<10;i++)
				{
					putimage(0,0,&bk);
					bloodshowbashen(blood1);
					bloodshowk(blood2);
					energyshowbashen(energy1);
					energyshowk(energy2);
					round(choice);	
					putimage(position_x,position_y,150,170,&bashenjidao1_,i*150,0,SRCAND);//播放P1到底画面
					putimage(position_x,position_y,150,170,&bashenjidao1,i*150,0,SRCPAINT);
					putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);//播放k站立动画
					putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
					putimage(position_x,position_y3,200,400,&siwangshenpan2,0,0,SRCAND);//播放审判之剑
					putimage(position_x,position_y3,200,400,&siwangshenpan1,0,0,SRCPAINT);	
					FlushBatchDraw();
					Sleep(40);
					position_y3=position_y3+10;
				}
					for(i=0;i<10;i++)
				{
					putimage(0,0,&bk);
					bloodshowbashen(blood1);
					bloodshowk(blood2);
					energyshowbashen(energy1);
					energyshowk(energy2);
					round(choice);	
					putimage(position_x,position_y+75,200,100,&bashenjidao2_,i*200,0,SRCAND);
					putimage(position_x,position_y+75,200,100,&bashenjidao2,i*200,0,SRCPAINT);
					putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
					putimage(position_x,position_y3,200,400,&siwangshenpan2,0,0,SRCAND);
					putimage(position_x,position_y3,200,400,&siwangshenpan1,0,0,SRCPAINT);		
					FlushBatchDraw();
					Sleep(40);
					position_y3=position_y3+10;
				}
					for(i=0;i<10;i++)
				{
					putimage(0,0,&bk);
					bloodshowbashen(blood1);
					bloodshowk(blood2);
					energyshowbashen(energy1);
					energyshowk(energy2);
					round(choice);	
					putimage(position_x,position_y+150,200,100,&bashenjidao3_,i*200,0,SRCAND);
					putimage(position_x,position_y+150,200,100,&bashenjidao3,i*200,0,SRCPAINT);
					putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
					putimage(position_x,position_y3,200,400,&siwangshenpan2,0,0,SRCAND);
					putimage(position_x,position_y3,200,400,&siwangshenpan1,0,0,SRCPAINT);
					FlushBatchDraw();
					Sleep(40);
					position_y3=position_y3+10;
				}
				}
				sign=0;	//让sign=0
			}
			if(blood2<=0)//判定P2已经死亡
			{
				if(position_y3<=high*1.3-450)
				{
				for(i=0;i<10;i++)
				{
					putimage(0,0,&bk);
					bloodshowbashen(blood1);
					bloodshowk(blood2);	
					energyshowbashen(energy1);
					energyshowk(energy2);
					round(choice);	
					putimage(position_x2,position_y2,200,100,&kjidao1_,i*200,0,SRCAND);//播放K击倒画面
					putimage(position_x2,position_y2,200,100,&kjidao1,i*200,0,SRCPAINT);
					putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);//播放八神站立动画
					putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
					putimage(position_x2,position_y3,200,400,&siwangshenpan2,0,0,SRCAND);//播放审判之剑
					putimage(position_x2,position_y3,200,400,&siwangshenpan1,0,0,SRCPAINT);
					FlushBatchDraw();
					Sleep(80);
					position_y3=position_y3+15;
				}
				for(i=0;i<10;i++)
				{
					putimage(0,0,&bk);
					bloodshowbashen(blood1);
					bloodshowk(blood2);	
					energyshowbashen(energy1);
					energyshowk(energy2);
					round(choice);	
					putimage(position_x2,position_y2+150,200,100,&kjidao2_,i*200,0,SRCAND);
					putimage(position_x2,position_y2+150,200,100,&kjidao2,i*200,0,SRCPAINT);
					putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
					putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
					putimage(position_x2,position_y3,200,400,&siwangshenpan2,0,0,SRCAND);
					putimage(position_x2,position_y3,200,400,&siwangshenpan1,0,0,SRCPAINT);
					FlushBatchDraw();
					Sleep(80);
					position_y3=position_y3+15;
				}
		
				}
				sign=0;//让sign=0
			}
			if(kbhit()==0&&sign==1)
			{	
				//循环播放两者初始状态
				for(i=0;i<9;i++)
				{
					putimage(0,0,&bk);
					bloodshowbashen(blood1);
					bloodshowk(blood2);
					energyshowbashen(energy1);
					energyshowk(energy2);
					round(choice);	
					putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
					putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
					putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
					putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
					FlushBatchDraw();
					Sleep(80);
				}
					
			}
			if(kbhit()!=0&&sign==1)
				{
			
				input=getch();
					

				if(choice==1)
				{

					if((GetAsyncKeyState(0x41)&0x8000))		//实现八神的后退(左移)动作 a
					{
					
						for(i=0;i<6;i++)
						{
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
				
					
					if(GetAsyncKeyState(0x44)&0x8000)		//实现八神的前进 d
					{
						
						for(i=0;i<7;i++)
						{
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							if(position_x<=position_x2-165)
							{
							position_x=position_x+20;
							}	
							putimage(position_x,position_y,300,255,&bashenbenpao1_,i*300,0,SRCAND);
							putimage(position_x,position_y,300,255,&bashenbenpao1,i*300,0,SRCPAINT);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							putimage(position_x,position_y+70,167,180,&bashenxiadun1_,i*167,0,SRCAND);
							putimage(position_x,position_y+70,167,180,&bashenxiadun1,i*167,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						} 
						for(i=0;i<9;i++)
						{
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
					if((GetAsyncKeyState(0x4F)&0x8000)&&(energy1>=3))	//实现八神的三招o
					{
						choice=2;
						energy1=energy1-3;
						time1++;
						for(i=0;i<10;i++)
						{
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							putimage(position_x,position_y,200,255,&bashenbaoqi1_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenbaoqi1,i*200,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
						for(i=0;i<10;i++)
						{
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							putimage(position_x,position_y,200,255,&bashenbaoqi2_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenbaoqi2,i*200,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
						position_x=0;
						position_y=high*1.3-255;
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,SRCPAINT);
						if((position_x+200>=position_x2)&&(position_y==position_y2))
						{
								blood2=blood2-3;
						}
						position_x=0;
						position_y=high*1.3-255;
					}
		
					if((GetAsyncKeyState(0x55)&0x8000)&&(bashendazhao==1))		//实现八神的大招 u
					{
						choice=2;
						bashendazhao=0;
						time1++;
						for(i=0;i<10;i++)
						{
						putimage(0,0,&bk);
						bloodshowbashen(blood1);
						bloodshowk(blood2);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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

							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
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
						if((position_x+200>=position_x2)&&(position_y==position_y2))
						{
								blood2=blood2-5;
								for(i=0;i<10;i++)//当P1释放大招的时候P2会有一个击倒的效果
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x2,position_y2,200,255,&kjidao1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kjidao1,i*200,0,SRCPAINT);
								putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
								putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
								for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x2,position_y2,200,255,&kjidao2_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kjidao2,i*200,0,SRCPAINT);
								putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
								putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
								for(i=0;i<4;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x2,position_y2,200,255,&kjidao3_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kjidao3,i*200,0,SRCPAINT);
								putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
								putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
						}
						position_x=0;
						position_y=high*1.3-255;
					}
					if((GetAsyncKeyState(0x49)&0x8000)&&(energy1>=5))		//实现八神的二招 i
					{
						choice=2;
						energy1=energy1-5;
						time1++;
						for(i=0;i<10;i++)
						{
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							putimage(position_x,position_y,200,255,&bashenerzhao1_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenerzhao1,i*200,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
							for(i=0;i<9;i++)
						{
							putimage(0,0,&bk);
							bloodshowbashen(blood1);
							bloodshowk(blood2);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							putimage(position_x,position_y,200,255,&bashenerzhao2_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenerzhao2,i*200,0,SRCPAINT);
							putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
							if((position_x+200>=position_x2)&&(position_y==position_y2))
						{
							blood2=blood2-4;
						}
						position_x=0;
						position_y=high*1.3-255;
					}
					if((GetAsyncKeyState(0x48)&0x8000)&&(energy1>=10))		//按下H键，八神爆气
					{
						choice=2;
						energy1=1;
						bashendazhao=1;
						time1++;
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi21_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi21,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi22_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi22,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi23_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi23,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi24_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi24,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi25_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi25,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi26_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi26,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi27_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi27,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								putimage(position_x,position_y,250,300,&bashenbaoqi28_,i*250,0,SRCAND);
								putimage(position_x,position_y,250,300,&bashenbaoqi28,i*250,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(50);
								FlushBatchDraw();
							}
							position_x=0;
							position_y=high*1.3-255;
					}
					if(GetAsyncKeyState(0x4A)&0x8000)		//实现八神的普攻 j
					{	
						choice=2;
						energy1=energy1+3;
						time1++;
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								if(position_x<=position_x2-165)
								{
									position_x=position_x+5;
								}
								putimage(position_x,position_y,150,255,&bashenpugong11_,i*150,0,SRCAND);
								putimage(position_x,position_y,150,255,&bashenpugong11,i*150,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(40);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								if(position_x<=position_x2-165)
								{
									position_x=position_x+5;
								}
								putimage(position_x,position_y,150,255,&bashenpugong12_,i*150,0,SRCAND);
								putimage(position_x,position_y,150,255,&bashenpugong12,i*150,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(40);
								FlushBatchDraw();
							}
							for(i=0;i<10;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								if(position_x<=position_x2-165)
								{
									position_x=position_x+5;
								}
								putimage(position_x,position_y,150,255,&bashenpugong13_,i*150,0,SRCAND);
								putimage(position_x,position_y,150,255,&bashenpugong13,i*150,0,SRCPAINT);
								putimage(position_x2,position_y2,200,255,&kzhanli1_,i*200,0,SRCAND);
								putimage(position_x2,position_y2,200,255,&kzhanli1,i*200,0,SRCPAINT);
								Sleep(40);
								FlushBatchDraw();
							}
							for(i=0;i<4;i++)
							{
								putimage(0,0,&bk);
								bloodshowbashen(blood1);
								bloodshowk(blood2);
								energyshowbashen(energy1);
								energyshowk(energy2);
								round(choice);
								bigskill(bashendazhao,kdazhao);
								if(position_x<=position_x2-165)
								{
									position_x=position_x+5;
								}
								putimage(position_x,position_y,150,255,&bashenpugong14_,i*150,0,SRCAND);
								putimage(position_x,position_y,150,255,&bashenpugong14,i*150,0,SRCPAINT);
								Sleep(40);
								FlushBatchDraw();
							}
							if((position_x+200>=position_x2)&&(position_y==position_y2))
							{
								blood2=blood2-1;
							}
							position_x=0;
							position_y=high*1.3-255;
					}
				}
				//导入右侧玩家控制的人物的动作
				if(choice==2)
				{

					if(GetAsyncKeyState(VK_LEFT)&0x8000)		//实现k的前进
					{
						for(i=0;i<10;i++)
						{
							putimage(0,0,&bk);
							bloodshowk(blood2);
							bloodshowbashen(blood1);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							if(position_x2>=position_x+200)	
							{
								position_x2=position_x2-15;
							}
							putimage(position_x2,position_y2,200,255,&kqianjin1_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kqianjin1,i*200,0,SRCPAINT);
							putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
							for(i=0;i<5;i++)
						{
							putimage(0,0,&bk);
							bloodshowk(blood2);
							bloodshowbashen(blood1);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							if(position_x2>=position_x+200)	
							{
								position_x2=position_x2-15;
							}
							putimage(position_x2,position_y2,200,255,&kqianjin2_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kqianjin2,i*200,0,SRCPAINT);
							putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
				}
				if(GetAsyncKeyState(VK_RIGHT)&0x8000)		//实现k的后退
				{
						for(i=5;i<10;i++)
						{
							putimage(0,0,&bk);
							bloodshowk(blood2);
							bloodshowbashen(blood1);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							position_x2=position_x2+15;
							putimage(position_x2,position_y2,200,255,&kqianjin2_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kqianjin2,i*200,0,SRCPAINT);
							putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
						for(i=5;i<11;i++)
						{
							putimage(0,0,&bk);
							bloodshowk(blood2);
							bloodshowbashen(blood1);
							energyshowbashen(energy1);
							energyshowk(energy2);
							round(choice);
							bigskill(bashendazhao,kdazhao);
							position_x2=position_x2+15;
							putimage(position_x2,position_y2,200,255,&kqianjin3_,i*200,0,SRCAND);
							putimage(position_x2,position_y2,200,255,&kqianjin3,i*200,0,SRCPAINT);
							putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
							putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
							Sleep(50);
							FlushBatchDraw();
						}
				}
				if(GetAsyncKeyState(VK_UP)&0x8000)			//实现k的跳跃
				{	
					for(i=0;i<7;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_y2>=0)	
						{
							position_y2=position_y2-30;
						}
						putimage(position_x2,position_y2,200,255,&ktiaoyue2_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&ktiaoyue2,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=5;i<12;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_y2<=high*1.3-255)	
						{
							position_y2=position_y2+30;
						}
						putimage(position_x2,position_y2,200,255,&ktiaoyue3_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&ktiaoyue3,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
				}
				if(GetAsyncKeyState(VK_DOWN)&0x8000)			//k下蹲
				{	
					
					for(i=0;i<2;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,200,255,&kxiadun1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kxiadun1,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<4;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2+100,200,255,&kxiadun2_,i*200,0,SRCAND);
						putimage(position_x2,position_y2+100,200,255,&kxiadun2,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<4;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,200,255,&kxiadun3_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kxiadun3,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
				}
				if((GetAsyncKeyState(0x30)&0x8000)&&(kdazhao==1))			//k释放了大招
				{
					choice=1;
					kdazhao=0;
					time2++;
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=0)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao1,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao2_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao2,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao3_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao3,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao4_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao4,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao5_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao5,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao6_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao6,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao7_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao7,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao8_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao8,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao9_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao9,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{

						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao10_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao10,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao11_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao11,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao12_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao12,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao13_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao13,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao14_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao14,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2+12;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao15_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao15,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-12;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao16_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao16,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<12;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{	
							position_x2=position_x2-3;
						}
						putimage(position_x2,position_y2,200,255,&kdazhao17_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&kdazhao17,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)		//当P2释放大招的时候P1会有一个击倒的效果
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x,position_y+75,150,170,&bashenjidao1_,i*150,0,SRCAND);
						putimage(position_x,position_y+75,150,170,&bashenjidao1,i*150,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x,position_y+75,200,100,&bashenjidao2_,i*200,0,SRCAND);
						putimage(position_x,position_y+75,200,100,&bashenjidao2,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x,position_y+75,200,100,&bashenjidao3_,i*200,0,SRCAND);
						putimage(position_x,position_y+75,200,100,&bashenjidao3,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&kzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&kzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					
					if((position_x2<=position_x+200)&&(position_y==position_y2))
					{
						blood1=blood1-5;
					}
					position_x2=width*1.5-200;
					position_y2=high*1.3-255;
				}
				if((GetAsyncKeyState(0x31)&0x8000)&&(energy2>=3))			//k的二招
				{
					choice=1;
					energy2=energy2-3;
					time2++;
					for(i=0;i<12;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,250,300,&kerzhao1_,i*250,0,SRCAND);
						putimage(position_x2,position_y2,250,300,&kerzhao1,i*250,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<12;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,250,300,&kerzhao2_,i*250,0,SRCAND);
						putimage(position_x2,position_y2,250,300,&kerzhao2,i*250,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					if((position_x2<=position_x+200)&&(position_y==position_y2))
					{
						blood1=blood1-3;
					}
					position_x2=width*1.5-200;
					position_y2=high*1.3-255;
				}
				if((GetAsyncKeyState(0x33)&0x8000)&&(energy2>=5))			//k的三招
				{
					choice=1;
					energy2=energy2-5;
					time2++;
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{
							position_x2=position_x2-5;
						}
						putimage(position_x2,position_y2,200,255,&ksanzhao1_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&ksanzhao1,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{
							position_x2=position_x2-5;
						}
						putimage(position_x2,position_y2,200,255,&ksanzhao2_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&ksanzhao2,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{
							position_x2=position_x2-5;
						}
						putimage(position_x2,position_y2,200,255,&ksanzhao3_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&ksanzhao3,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{
							position_x2=position_x2-5;
						}
						putimage(position_x2,position_y2,200,255,&ksanzhao4_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&ksanzhao4,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<10;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						if(position_x2>=position_x+200)
						{
							position_x2=position_x2-5;
						}
						putimage(position_x2,position_y2,200,255,&ksanzhao5_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,255,&ksanzhao5,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					if((position_x2<=position_x+200)&&(position_y==position_y2))
					{
						blood1=blood1-4;
					}
					position_x2=width*1.5-200;
					position_y2=high*1.3-255;
				}
				if(GetAsyncKeyState(0x35)&0x8000)			//k的普通攻击
				{
					choice=1;
					energy2=energy2+3;
					time2++;
					for(i=0;i<3;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,250,300,&kpugong23_,i*250,0,SRCAND);
						putimage(position_x2,position_y2,250,300,&kpugong23,i*250,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<15;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,300,250,&kpugong22_,i*300,0,SRCAND);
						putimage(position_x2,position_y2,300,250,&kpugong22,i*300,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<2;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,250,300,&kpugong21_,i*250,0,SRCAND);
						putimage(position_x2,position_y2,250,300,&kpugong21,i*250,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					if((position_x2<=position_x+200)&&(position_y==position_y2))
					{
						blood1--;
					}
					position_x2=width*1.5-200;
					position_y2=high*1.3-255;
				}
				if((GetAsyncKeyState(0x38)&0x8000)&&(energy2>=10))			//k开始爆气
				{
					energy2=1;
					kdazhao=1;
					choice=1;
					time2++;
					for(i=0;i<4;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,200,300,&kbaoqi21_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,300,&kbaoqi21,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<4;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,200,300,&kbaoqi21_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,300,&kbaoqi21,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
					for(i=0;i<4;i++)
					{
						putimage(0,0,&bk);
						bloodshowk(blood2);
						bloodshowbashen(blood1);
						energyshowbashen(energy1);
						energyshowk(energy2);
						round(choice);
						bigskill(bashendazhao,kdazhao);
						putimage(position_x2,position_y2,200,300,&kbaoqi21_,i*200,0,SRCAND);
						putimage(position_x2,position_y2,200,300,&kbaoqi21,i*200,0,SRCPAINT);
						putimage(position_x,position_y,200,255,&bashenzhanli1_,i*200,0,SRCAND);
						putimage(position_x,position_y,200,255,&bashenzhanli1,i*200,0,SRCPAINT);
						Sleep(50);
						FlushBatchDraw();
					}
				position_x2=width*1.5-200;
				position_y2=high*1.3-255;
				}
			}
		}
			Sleep(100);
			if(sign==0)//当其中一方死亡后进入游戏结束画面
			{
				if(blood1<=0 || blood2<=0)
				{	
					if(blood1<=0)
					{
						putimage(0,0,&kshengli);
					}
					if(blood2<=0)
					{
						putimage(0,0,&bashenshengli);
					}
					Sleep(500);
					ending();
					flag=ending();
				}	
			}
		}//sign
	}//flag
}

/****************************************有关图片的函数*************************************/ 
void pictureloading()//图片加载函数
{
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

	loadimage(&cursor1_p1,".\\p1光标mask.bmp");
	loadimage(&cursor2_p1,".\\p1光标.bmp");

	loadimage(&cursor1_p2,".\\p2光标mask.bmp");
	loadimage(&cursor2_p2,".\\p2光标.bmp");
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
	loadimage(&bashenbaoqi21,".\\bashen 38.bmp");
	loadimage(&bashenbaoqi21_,".\\bashen38.bmp");
	loadimage(&bashenbaoqi22,".\\bashen 39.bmp");
	loadimage(&bashenbaoqi22_,".\\bashen39.bmp");
	loadimage(&bashenbaoqi23,".\\bashen 40.bmp");
	loadimage(&bashenbaoqi23_,".\\bashen40.bmp");
	loadimage(&bashenbaoqi24,".\\bashen 41.bmp");
	loadimage(&bashenbaoqi24_,".\\bashen41.bmp");
	loadimage(&bashenbaoqi25,".\\bashen 42.bmp");
	loadimage(&bashenbaoqi25_,".\\bashen42.bmp");
	loadimage(&bashenbaoqi26,".\\bashen 43.bmp");
	loadimage(&bashenbaoqi26_,".\\bashen43.bmp");
	loadimage(&bashenbaoqi27,".\\bashen 44.bmp");
	loadimage(&bashenbaoqi27_,".\\bashen44.bmp");
	loadimage(&bashenbaoqi28,".\\bashen 45.bmp");
	loadimage(&bashenbaoqi28_,".\\bashen45.bmp");
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
	loadimage(&kbaoqi21,".\\k 61.bmp");
	loadimage(&kbaoqi21_,".\\k61.bmp");

	//初始化界面（包括血条，背景，死亡界面，死亡动画效果,胜利）
	loadimage(&xuetiao1,".\\xuetiao1.png");
	loadimage(&xuetiao2,".\\xuetiao2.png");
	loadimage(&xuetiao3,".\\xuetiao3.png");
	loadimage(&xuetiao4,".\\xuetiao4.png");
	loadimage(&xuetiao5,".\\xuetiao5.png");
	loadimage(&xuetiao6,".\\xuetiao6.png");
	loadimage(&xuetiao7,".\\xuetiao7.png");
	loadimage(&xuetiao8,".\\xuetiao8.png");
	loadimage(&xuetiao9,".\\xuetiao9.png");
	loadimage(&xuetiao10,".\\xuetiao10.png");
	loadimage(&xuetiao11,".\\xuetiao11.png");
	loadimage(&xuetiao12,".\\xuetiao12.png");
	loadimage(&xuetiao13,".\\xuetiao13.png");
	loadimage(&xuetiao14,".\\xuetiao14.png");
	loadimage(&xuetiao15,".\\xuetiao15.png");
	loadimage(&xuetiao16,".\\xuetiao16.png");
	loadimage(&xuetiao17,".\\xuetiao17.png");
	loadimage(&xuetiao18,".\\xuetiao18.png");
	loadimage(&xuetiao19,".\\xuetiao19.png");
	loadimage(&xuetiao20,".\\xuetiao20.png");
	loadimage(&energy_1,".\\能量1.png");
	loadimage(&energy_2,".\\能量2.png");
	loadimage(&energy3,".\\能量3.png");
	loadimage(&energy4,".\\能量4.png");
	loadimage(&energy5,".\\能量5.png");
	loadimage(&energy6,".\\能量6.png");
	loadimage(&energy7,".\\能量7.png");
	loadimage(&energy8,".\\能量8.png");
	loadimage(&energy9,".\\能量9.png");
	loadimage(&energy10,".\\能量10.png");
	loadimage(&energy11,".\\能量11.png");
	loadimage(&energy12,".\\能量12.png");
	loadimage(&energy13,".\\能量13.png");
	loadimage(&energy14,".\\能量14.png");
	loadimage(&energy15,".\\能量15.png");
	loadimage(&energy16,".\\能量16.png");
	loadimage(&energy17,".\\能量17.png");
	loadimage(&energy18,".\\能量18.png");
	loadimage(&energy19,".\\能量19.png");
	loadimage(&energy20,".\\能量20.png");
	loadimage(&siwangshenpan1,".\\死亡审判1.bmp");
	loadimage(&siwangshenpan2,".\\死亡审判2.bmp");
	loadimage(&zuojiantou,".\\左箭头.bmp");
	loadimage(&zuojiantou_,".\\左箭头遮罩图.bmp");
	loadimage(&youjiantou,".\\右箭头.bmp");
	loadimage(&youjiantou_,".\\右箭头遮罩图.bmp");
	loadimage(&bashensiwang,".\\bashensiwang.png");
	loadimage(&ksiwang,".\\ksiwang.png");
	loadimage(&bkending,".\\ending.png");
	loadimage(&dazhao,".\\大招.bmp");
	loadimage(&dazhao_,".\\大招遮罩图.bmp");
	loadimage(&bashenshengli,"\\bashenshengli.png");
	loadimage(&kshengli,"\\kshengli.png");
	//导入开头解释说明的背景图片
	loadimage(&shuoming1,".\\背景1.png");
	loadimage(&shuoming2,".\\背景2.png");
	loadimage(&shuoming3,".\\背景3.png");
	loadimage(&shuoming4,".\\背景4.png");
	//导入骰子图片
	loadimage(&shaizi1,".\\色子1.png");
	loadimage(&shaizi2,".\\色子2.png");
	loadimage(&shaizi3,".\\色子3.png");
	loadimage(&shaizi4,".\\色子4.png");
	loadimage(&shaizi5,".\\色子5.png");
	loadimage(&shaizi6,".\\色子6.png");
	//游戏结束时的箭头
	loadimage(&ending_cursor1,".\\箭头_mask.bmp");
	loadimage(&ending_cursor2,".\\箭头.bmp");
} 


void startvideo()			//开始动画播放函数
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

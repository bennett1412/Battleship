# Battleship


Skip to content
Using Gmail with screen readers
battleship 

Conversations
0.99 GB (0%) of 115 GB used
Manage
Terms · Privacy · Program Policies
Last account activity: 33 minutes ago
Details

//Battleship - A Game of Strategy
#include<iostream.h>
#include<conio.h>
#include<process.h>
void rules()
{
//Function to display rules of the game
cout<<"1.The computer has placed three boats of size 2,3 and 4 randomly.\n";
cout<<"2.None of the boats are placed diagonally.\n";
cout<<"3.No two boats are touching each other.\n";
cout<<"4.To shoot your missiles onto your opponets grid follow the instructions \n";
cout<<"5.Cannot exit the game while inputing a value\n";
cout<<"6.Scores will be provided on the basis of hits and misses.";
}
//Fuction to display the grid
void grid(char sea[8][8])
{
int i,j,c;
cout<<"   ";
for(i=0,j=0;j<8;j++)
{
cout<<j<<"  ";
}
cout<<"\n";
for(i=0;i<8;i++)
{	for(j=0;j<8;j++)
	{	if(j==0)
		{
		 cout<<i<<"  ";
		}
	       sea[i][j]='+';
	       cout<<sea[i][j]<<"  ";
	}
	cout<<"\n";
}


}

//Function to store the coordinates
//Boat 1
void boat1(int boat1x[2], int boat1y[2], char boat1t[2]){
   for (int i=0;i<2;i++) {
     boat1x[i]=7;
     boat1y[i]=i+1;
     boat1t[i]='+';
     }
}
//Function to check hit or miss
//Boat 1
int checkBoat1(int x, int y, int boat1x[2], int boat1y[2], char boat1t[2],char sea1[8][8]){

    for (int i=0;i<2;i++) {
      if ((boat1x[i]==x) && (boat1y[i]==y)) {
	  boat1t[i]='#';
	  sea1[x][y]='#';
	  return 1;
      }
     }
     return 0;
}
//Function to check if the boat is destroyed or not
//boat 1
int checkDestroy1(char boat1t[2]){
    for (int i=0;i<2;i++) {
	if (boat1t[i]=='+') return 0;
}
    return 1;
}
//Function store the coordinates
//boat 2
void boat2(int boat2x[3], int boat2y[3], char boat2t[3]){
     for (int i=0;i<3;i++) {
     boat2x[i]=i+2;
     boat2y[i]=7;
     boat2t[i]='+';
     }
}
//Function to check hit or miss
//Boat 2
int checkBoat2(int x, int y, int boat2x[3], int boat2y[3], char boat2t[3],char sea1[8][8]){

    for (int i=0;i<3;i++) {
      if ((boat2x[i]==x) && (boat2y[i]==y)) {
	  boat2t[i]='#';
	  sea1[x][y]='#';
	  return 1;
      }
     }
     return 0;
}
//Function to check if the boat is destroyed or not
//Boat 2
int checkDestroy2(char boat2t[3]){
    for (int i=0;i<3;i++) {
	if (boat2t[i]=='+') return 0;
}
    return 2;
}
//Function store coordinates of the boat
//boat3
void boat3(int boat3x[4],int boat3y[4],char boat3t[4]){
     for (int i=0;i<4;i++) {
     boat3x[i]=i;
     boat3y[i]=3;
     boat3t[i]='+';
     }

}
//Function to check hit or miss
//boat3
int checkBoat3(int x, int y, int boat3x[4], int boat3y[4], char boat3t[4],char sea1[8][8]){

    for (int i=0;i<4;i++) {
      if ((boat3x[i]==x) && (boat3y[i]==y)) {
	  boat3t[i]='#';
	  sea1[x][y]='#';
	  return 1;
      }
     }
     return 0;
}
//Function to check if the boat is destroyed or not
//boat3
int checkDestroy3(char boat3t[4]){
    for (int i=0;i<4;i++) {
	if (boat3t[i]=='+') return 0;
}
    return 3;
}
//Function to store the coordinates of the boat
//boat4
void boat4(int boat4x[5],int boat4y[5],char boat4t[5]){
     for (int i=0;i<5;i++) {
     boat4x[i]=5;
     boat4y[i]=i;
     boat4t[i]='+';
     }

}
//Function to check hit or miss
//boat 4
int checkBoat4(int x, int y, int boat4x[5], int boat4y[5], char boat4t[5],char sea1[8][8]){

    for (int i=0;i<5;i++) {
      if ((boat4x[i]==x) && (boat4y[i]==y)) {
	  boat4t[i]='#';
	  sea1[x][y]='#';
	  return 1;
      }
     }
     return 0;
}
//Function to check if the boat is destroyed or not
//boat4
int checkDestroy4(char boat4t[5]){
    for (int i=0;i<5;i++) {
	if (boat4t[i]=='+') return 0;
}
    return 4;
}

//Function to store the boats in an array
void comp(char sea[8][8])
{
int i,j,c;
for(i=0;i<8;i++)
{	for(j=0;j<8;j++)
	{
	 sea[i][j]='+';
	}

}
//Size of the boat is 2
for(i=7,j=1;j<3;j++)
{
sea[i][j]='#';
}
//Size of the boat is 3
for(i=2,j=7;i<5;i++)
{
sea[i][j]='#';
}

//Size of the boat is 4
for(i=0,j=3;i<4;i++)
{
sea[i][j]='#';
}

//Size of the boat is 5
for(i=5,j=0;j<5;j++)
{
sea[i][j]='#';
}


}

//Program to accept coordinates at which user wants shoot
void shoot(int &x,int &y)
{
cout<<"\n\nEnter the coordinates at which wanna shoot:\n";
do{
cout<<"Enter the row number in which u wanna shoot:\n";
cin>>x;
if(x>7)  {
  cout<<"Error!! row number should be between 0-7\n";
}
}while(x>7) ;
do {
  cout<<"Enter the column number at which u wanna shoot:\n";
  cin>>y;
  if(y>7)  {
  cout<<"Error!! column number should be between 0-7\n";
	   }
   } while(y>7);

}

//Function to show user hits and misses
void prgrid(char sea[8][8])
{
int i,j,c;
cout<<"   ";
for(i=0,j=0;j<8;j++)
{
cout<<j<<"  ";
}
cout<<"\n";

for(i=0;i<8;i++)
{	for(j=0;j<8;j++)
	{	if(j==0)
		{
		 cout<<i<<"  ";
		}
		cout<<sea[i][j]<<"  ";
	}
	cout<<"\n";

}

 }
//Function to check gameover or not
int gameover(char sea[8][8],char sea1[8][8])
{int i,j;
for(i=0;i<8;i++)
{	for(j=0;j<8;j++)
	{
	if (sea[i][j]=='#') {
	    if(sea[i][j]!=sea1[i][j])
	    return 0;
	    }
	 }

}
return 1;
}
void main()
{
clrscr();
int i,j,a,b,c,s,result,count;
count=0;//Var to check score
char se[8][8],se1[8][8];//computer grids
int boat1x[2],boat1y[2];//boat1 coordinates
char boat1t[2];//var to check hit(#) or miss($)
int boat2x[3],boat2y[3];//boat2 coordinates
char boat2t[3];//var to check hit or miss
int boat3x[4],boat3y[4];//boat3 coordinates
char boat3t[4];//var to check hit or miss
int boat4x[5],boat4y[5];//boat 4 coordinates
char boat4t[5];//var to check hit or miss
cout<<"Battleship - A game of strategy\n\n";
grid(se1);        //show grid
 //initialize grid array
comp(se);      //set computer boats
cout<<"This is the grid this is where the boats are hidden.\n\n";
cout<<"These are the rules for the game";
rules();       //show rules of the game
cout<<"\n\n";
boat1(boat1x,boat1y,boat1t);//store boat1 co
boat2(boat2x,boat2y,boat2t);//store boat2 co
boat3(boat3x,boat3y,boat3t);//store boat4 co
boat4(boat4x,boat4y,boat4t);//store boat3 co
//game loop
do{
shoot(a,b);
if (checkBoat1(a,b,boat1x,boat1y,boat1t,se1)) cout<<"\nHit Boat1\n\n"<<"# denotes hit and $ denotes miss\n\n"  ;
else {
	if (checkBoat2(a,b,boat2x,boat2y,boat2t,se1)) cout <<"\nHit Boat2\n\n"<<"# denotes hit and $ denotes miss\n\n";
	else {
	if(checkBoat3(a,b,boat3x,boat3y,boat3t,se1)) cout<<"\nHit Boat3\n\n"<<"# denotes hit and $ denotes miss\n\n";
		else{
			if(checkBoat4(a,b,boat4x,boat4y,boat4t,se1)) cout<<"\nHit Boat4\n\n"<<"# denotes hit and $ denotes miss\n\n";
			else{
			se1[a][b]='$';cout<<"\nMiss\n\n"<<"# denotes hit and $ denotes miss\n\n";
			count=count+1;
			    };
		    }
	      }
     }

prgrid(se1);
int result1=checkDestroy1(boat1t);
if (result1) {
   cout<<"Boat 1 sinked\t";
   }

int result2=checkDestroy2(boat2t);
if (result2) {
   cout<<"Boat 2 sinked\t";
   }

int result3=checkDestroy3(boat3t);
if (result3) {
   cout<<"Boat 3 sinked\t";
   }

int result4=checkDestroy4(boat4t);
if (result4) {
   cout<<"Boat 4 sinked\t";
   }

if (result1&&result2&&result3&&result4){
   cout<<"\n\nGameover!!\n\n";
   cout<<"Scores are as follows:-\n\n";
   if(count<10){
   cout<<"Score=50/50";}
   else{
	if((count>10)&&(count<20)){
	cout<<"Score=40/50";}
	else{
		if((count>20)&&(count<30)){
		cout<<"Score=30/50";}
		else{cout<<"You lost!!";}
	     }
       }
   cout<<"\n\nPress e to quit the screen.\n\n";
   c=getch();
   if(c=='e') exit(0);
   }
cout<<"\nPress e to Exit or any other key to continue\n";
c=getch();
if (c=='e') result=1;
} while(result!=1);
}
//The end
BATTLE1.CPP
Displaying BATTLE1.CPP.

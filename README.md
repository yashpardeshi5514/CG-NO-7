Write a C++ program to control a ball using arrow keys. Apply the concept of polymorphism.
OR
Write a C++ program to implement bouncing ball using sine wave form. Apply the concept of polymorphism.
OR
c) Write C++ program to draw man walking in the rain with an umbrella. Apply the concept of
polymorphism.
OR
d) Write a C++ program to implement the game of 8 puzzle. Apply the concept of
polymorphism.
OR
e) Write a C++ program to implement the game Tic Tac Toe. Apply the concept of polymorphism


// BOUNCING BALL

#include<iostream> 
#include<conio.h> 
#include<graphics.h> 
#include<dos.h> 
int main() 
{ 
  
 int gd=0,gm,x=20,flag=0,y=200,uplimit=250; 
 initgraph(&gd,&gm,"C:\\Tc\\BGI"); 
 while(!kbhit()) 
 { 
  setcolor(4); 
  line(0,400,679,400); 
  if(flag==0) 
  { 
   y+=2; 
   x+=1; 
   if(y>=385) 
   flag=1; 
  } 
  if(flag==1) 
  { 
   y-=2; 
   x+=1; 
   if(y<=uplimit) 
   { 
    flag=0; 
    uplimit+=20; 
 
   } 
  } 
 
  setcolor(15); 
  fillellipse(x,y,15,15); 
  delay(15); 
  setcolor(0); 
  setfillstyle(1,10); 
  fillellipse(x,y,15,15); 
  cleardevice(); 
 } 
 
 getch(); 
}

// Man Walked In Rain 

#include<iostream> 
#include<conio.h> 
#include<graphics.h> 
#include<stdlib.h> 
#include<dos.h> 
using namespace std; 
class walkingman 
{ 
int rhx,rhy; 
public: 
void draw(int,int); 
void draw(int); 
}; 
void walkingman::draw(int i) 
{ 
line(20,380,580,380); 
if(i%2) 
{ 
line(25+i,380,35+i,340); 
line(45+i,380,35+i,340); 
line(35+i,310,25+i,330); 
delay(20); 
} 
else 
{ 
line(35+i,340,35+i,310); 
line(35+i,310,40+i,330); 
delay(20); 
} 
line(35+i,340,35+i,310); 
circle(35+i,300,10); 
line(35+i,310,50+i,330); 
line(50+i,330,50+i,280); 
line(15+i,280,85+i,280); 
arc(50+i,280,0,180,35); 
arc(55+i,330,180,360,5); 
} 
void walkingman::draw(int x,int y) 
{ 
int j; 
rhx=x; 
rhy=y; 
for 
(j=0;j<100;j++) 
{ 
outtextxy(rand()%rhx,rand()%(rhy-50),"|"); 
setcolor(WHITE); 
} 
} 
int main() 
{ 
int gd=DETECT,gm; 
int rhx,rhy,j,i; 
walkingman obj; 
initgraph(&gd,&gm,""); 
for(i=0;i<500;i++) 
{ 
obj.draw(i); 
rhx=getmaxx(); 
rhy=getmaxy(); 
obj.draw(rhx,rhy); 
delay(150); 
cleardevice(); 
} 
getch(); 
} 

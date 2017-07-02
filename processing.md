import processing.serial.*;
Serial duankou;
int V;
float a= random(3);
int x;
int y;
void setup(){
  duankou = new Serial(this,"COM3",9600);
  size(600,200);
  background(0);
}
void draw(){
  background(0);
    if(a>0&&a<=1){draw1();x=1;}
    if(a>1&&a<=2){draw2();x=2;}
    if(a>2&&a<=3){draw3();x=3;}
    if(duankou.available()>0){
      V=duankou.read();
      println(V);
      if(V==1){draw01();y=1;}
      if(V==2){draw02();y=2;}
      if(V==3){draw03();y=3;}
      if(x==y){reset();}
            delay(500);

    }
  
}
void reset(){a=random(3);}
void draw1(){
  fill(255);
  ellipse(100,100,100,100);
}
void draw2(){
  fill(255);
  ellipse(300,100,100,100);
}
void draw3(){
  fill(255);
  ellipse(500,100,100,100);
}
void draw01(){
  fill(0);
  ellipse(100,100,100,100);
}
void draw02(){
  fill(0);
  ellipse(300,100,100,100);
}
void draw03(){
  fill(0);
  ellipse(500,100,100,100);
}

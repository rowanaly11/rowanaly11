#include <GL/gl.h>
#include <GL/glu.h>
#include <GL/glut.h>
#include <math.h>

#include <stdlib.h>
#include <windows.h>
void display();
void reshape(int w,int h);
void timer(int);



void init(){
    glClearColor(73.0/255.0,146.0/255.0 ,255.0/255.0,0.0);
}
int main(int argc,char**argv)
{
    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_RGB);

    glutInitWindowPosition(200,0);
    glutInitWindowSize(1200,800);

    glutCreateWindow("20101794");

    glutDisplayFunc(display);
    glutReshapeFunc(reshape);
    glutTimerFunc(0,timer,0);


     init();

    glutMainLoop();
}
float step=0;
void display()
{
    glClear(GL_COLOR_BUFFER_BIT);
    glLoadIdentity();
    double radius;
    int y_position;


 //garden
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(34, 139 ,34);
glVertex2f(-15,-6);
glVertex2f(15,-6);
glVertex2f(15,-10);
glVertex2f(-15,-10);
glEnd();
glPopMatrix();

//house

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(205 ,133 ,63);
    glVertex2f(6,-9);
    glVertex2f(12,-9);
    glVertex2f(12,0);
    glVertex2f(6,0);
    glEnd();
glPopMatrix();

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_TRIANGLES);
    glColor3ub(139 ,90 ,43);
    glVertex2f(6,0);
    glVertex2f(12,0);
    glVertex2f(8.9,5);

    glEnd();
glPopMatrix();


//windows1
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(139 ,90 ,43);
    glVertex2f(6.5,-3);
    glVertex2f(8.5,-3);
    glVertex2f(8.5,-1);
    glVertex2f(6.5,-1);
    glEnd();
glPopMatrix();
//window2
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(139 ,90 ,43);
    glVertex2f(9.5,-3);
    glVertex2f(11.5,-3);
    glVertex2f(11.5,-1);
    glVertex2f(9.5,-1);
    glEnd();
glPopMatrix();

//door
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(139 ,90 ,43);
    glVertex2f(8,-9);
    glVertex2f(10,-9);
    glVertex2f(10,-5.5);
    glVertex2f(8,-5.5);
    glEnd();
glPopMatrix();




//1st tree
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(139 ,69 ,19);
glVertex2f(-12,-7);
glVertex2f(-11,-7);
glVertex2f(-11,0);
glVertex2f(-12,0);
glEnd();
glPopMatrix();



//1st tree
glPushMatrix();
glBegin(GL_TRIANGLES);
glColor3ub(105, 139 ,34	);
glVertex2f(-15,0);
glVertex2f(-8,0);
glVertex2f(-11.7,7.5);

glEnd();
glPopMatrix();


//2nd tree
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(139 ,69 ,19);
glVertex2f(-9,-6);
glVertex2f(-8,-6);
glVertex2f(-8,-2);
glVertex2f(-9,-2);
glEnd();
glPopMatrix();

//2nd tree
glPushMatrix();
glBegin(GL_TRIANGLES);
glColor3ub(105, 139 ,34	);
glVertex2f(-11,-2);
glVertex2f(-5,-2);
glVertex2f(-8.3,4.5);

glEnd();
glPopMatrix();


//sun
glPushMatrix();
glTranslated(-8.5,6.5,0);
glRotated(-8.5,6.5,0,0);
glBegin(GL_POLYGON);
glColor3ub(255,255 ,0);

radius=1.6;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}
glEnd();
glPopMatrix();




//----robot----

//head

glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(176, 48 ,96);
glVertex2f(-2,0);
glVertex2f(2,0);
glVertex2f(2,-3);
glVertex2f(-2,-3);
glEnd();
glPopMatrix();



//body
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(219 ,112 ,147);
glVertex2f(-1.5,-5.5);
glVertex2f(1.5,-5.5);
glVertex2f(1.5,-3);
glVertex2f(-1.5,-3);
glEnd();
glPopMatrix();

//----eyes---
//eye1
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(255 ,174 ,185);
glVertex2f(-1.2,-1.5);
glVertex2f(-0.5,-1.5);
glVertex2f(-0.5,-1);
glVertex2f(-1.2,-1);
glEnd();
glPopMatrix();

//eye2
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(255 ,174, 185);
glVertex2f(0.2,-1.5);
glVertex2f(0.9,-1.5);
glVertex2f(0.9,-1);
glVertex2f(0.2,-1);
glEnd();
glPopMatrix();

//mouth
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(255 ,174 ,185);
glVertex2f(-0.5,-2.5);
glVertex2f(0.5,-2.5);
glVertex2f(0.5,-2);
glVertex2f(-0.5,-2);
glEnd();
glPopMatrix();


//hat
glPushMatrix();
glBegin(GL_TRIANGLES);
glColor3ub(139, 58 ,98);
glVertex2f(-0.8,0);
glVertex2f(0.8,0);
glVertex2f(0,1.5);

glEnd();
glPopMatrix();


//---legs---

//leg1
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(176 ,48, 96);
glVertex2f(-1,-7.5);
glVertex2f(-0.3,-7.5);
glVertex2f(-0.3,-5.5);
glVertex2f(-1,-5.5);
glEnd();
glPopMatrix();


//leg2
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(176, 48 ,96);
glVertex2f(0.5,-7.5);
glVertex2f(1.2,-7.5);
glVertex2f(1.2,-5.5);
glVertex2f(0.5,-5.5);
glEnd();
glPopMatrix();



//---hands---
//hand1

glPushMatrix();
glTranslated(-2.8,-4,0);
glRotated(-19,3.8,6.5,8);
glBegin(GL_POLYGON);
glColor3ub(176, 48 ,96);
radius=0.3;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)+radius,radius*sin(angle));
}
glEnd();
glPopMatrix();

//hand2

glPushMatrix();
glTranslated(2.05,-4,0);
glRotated(40,3.8,6.5,8);
glBegin(GL_POLYGON);
glColor3ub(176, 48 ,96);
radius=0.3;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)+radius,radius*sin(angle));
}
glEnd();
glPopMatrix();

//---cloud--
//1
glPushMatrix();
//step to make the clouds moves
glTranslated(step+-3,7,0);
glBegin(GL_POLYGON);
glColor3ub(255, 250, 250);

radius=1;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}
glEnd();
glPopMatrix();

//2
glPushMatrix();
glTranslated(step+-1.5,7,0);
glBegin(GL_POLYGON);
glColor3ub(255 ,250 ,250);

radius=1;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}
glEnd();
glPopMatrix();


//3
glPushMatrix();
glTranslated(step+-0,7,0);
glBegin(GL_POLYGON);
glColor3ub(255 ,250 ,250);

radius=1;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}
glEnd();
glPopMatrix();


//---cloud2---

//1
glPushMatrix();
glTranslated(step+10,7,0);
glBegin(GL_POLYGON);
glColor3ub(255 ,250, 250);

radius=1;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}

glEnd();
glPopMatrix();


//2
glPushMatrix();
glTranslated(step+8.5,7,0);
glBegin(GL_POLYGON);
glColor3ub(255 ,250, 250);

radius=1;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}

glEnd();
glPopMatrix();




//3
glPushMatrix();
glTranslated(step+7,7,0);
glBegin(GL_POLYGON);
glColor3ub(255 ,250, 250);

radius=1;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}

glEnd();
glPopMatrix();



//ball
glPushMatrix();
glTranslated(step+1.5,-8,0);
glBegin(GL_POLYGON);
glColor3ub(0 ,0, 139);

radius=1;
for(int i=0;i<360;i++)
{
   double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}

glEnd();
glPopMatrix();

//line1
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_LINES);
    glColor3ub(176, 226 ,255);
    glVertex2f(step+1.5,-8.0);
    glVertex2f(step+2,-8.9);

    glEnd();
glPopMatrix();

//line2
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_LINES);
    glColor3ub(176, 226 ,255);
    glVertex2f(step+1.5,-8.0);
    glVertex2f(step+2,-7);

    glEnd();
glPopMatrix();

//line3
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_LINES);
    glColor3ub(176, 226 ,255);
    glVertex2f(step+1.5,-8.0);
    glVertex2f(step+.4,-8);

    glEnd();
glPopMatrix();






    glFlush();
}


void timer(int){
    glutPostRedisplay();
    glutTimerFunc(1000/10,timer,0);

step+=0.1;



}











void reshape(int w,int h)
{
    glViewport(0,0,(GLsizei)w,(GLsizei)h);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(-15,15,-10,10);
    glMatrixMode(GL_MODELVIEW);
}







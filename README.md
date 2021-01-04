# Circular-queue
#include<stdio.h>
#include<stdlib.h>
#include<conio.h>
#define max 10
struct queue
{int data[max];
int front,rear,count;
}q;
void enqueue()
{char ch='y';
printf("---------------------------------------------------------------");
do
{if(q.count == max)
{printf("\nQueue OVERFLOW!!");
break;
}
else
{printf("\nInsert Item :");
scanf("%d",&q.data[q.rear]);
q.rear=(q.rear+1)%max;
q.count++;
}
printf("\tAdd More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch=='y' || ch=='Y');
}
void dequeue()
{int ch='y';
printf("---------------------------------------------------------------");
do
{if(q.count==0)
{printf("\nQueue UNDERFLOW!!");
break;
}
else
{printf("\nData Deleted : %d",q.data[q.front]);
q.front=(q.front+1)%max;
q.count--;
}
printf("\tDelete More?? Y or N:");
ch=getch();
printf("%c",ch);
} while (ch=='y'||ch=='Y');
}
void display()
{printf("------------------------------------------------------------");
if(q.count==0)
printf("\nEmpty Queue");
else
{int i=q.front;
printf("\nFront->");
while(i!=q.rear)
{printf("%d ",q.data[i]);
i =(i+1)%max;
}
printf("<-Rear");
}
}
int main()
{int c,size,x=1;
q.front=0; q.rear=0; q.count=0;
do
{printf("\n------------------------------------------------------------\n");
printf("1.ENQUEUE(Add data)  \t2.DEQUEUE(delete data)    \t3.Display QUEUE\n4.Exit");
printf("\n\t\tEnter Choice :");
scanf("%d",&c);
switch(c)
{case 1: {enqueue(); break; }
case 2: {dequeue(); break; }
case 3: {display(); break; }
case 4: {x=0;break;exit(0);    }
default:{printf("\n\n\t\tError!!!!!"); break;}
}
}while(x);
return 0;
}


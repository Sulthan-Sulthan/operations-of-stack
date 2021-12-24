# operations-of-stack
#include<stdio.h>
#include<stdlib.h>
#include<math.h>
#define MAX 3
void push(int[], int, int);
int pop(int[], int);
void palin(int[], int);
void display(int[], int);
int main()
{
int choice,stack[MAX],top=-1,ele;
while(1)
{
 printf("\n\n**********************MENU*****************");
 printf("\n1. Push an Element to Stack\n2. Pop an Element 
from Stack\n3. Checking Stack for Palindrome\n4. Display the status of 
Stack\n5. Exit\n");
 printf("Enter your choice : ");
 scanf("%d", &choice);
 switch(choice)
{
case 1: if(top < MAX-1)
{
printf("Enter the element to be pushed : 
");
scanf("%d",&ele);
top++;
push(stack,ele,top);
}
else
printf("Stack is full\n");
break;
case 2: if(top >= 0)
{
ele = pop(stack,top);
top--;
else 
printf("Stack is empty\n");
break;
case 3: palin(stack, top);
break;
case 4: display(stack,top);
break;
case 5: exit(0);
}
}
}
void push(int stack[MAX],int ele, int top)
{
stack[top] = ele;
}
int pop(int stack[MAX], int top)
{
return stack[top];
}
void palin(int stack[MAX],int top)
{
int i, num=0,count=0,temp=0,dup=0,digit=0,rev=0;
if(top >= 0)
{
for(i=top;i>=0;i--)
{
num = stack[i];
while(num != 0)
{
num = num/10;
count++;
}
temp = temp * pow(10,count) + stack[i];
count = 0;
}
dup = temp;
while(temp != 0)
{
digit = temp%10;
rev = rev * 10 + digit;
temp = temp/10;
}
if(dup == rev)
printf("The content of stack is palindrome");
else
printf("The content of stack is not palindrome");
}
else
printf("Stack is empty\n");
}
void display(int stack[MAX], int top)
{
int i;
if(top >= 0)
{
printf("The elements of stack are\n\n");
for(i=0; i<=top; i++)
printf("%d ",stack[i]);
}
else
printf("Stack is empty\n");
}

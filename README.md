# BalancedParentheses
//Code in C to check balanced parentheses(using stack)
#include<stdio.h>
#include<string.h>
int A[99],top=-1;
void Push(int);
void Pop();
int gettop();
int isEmpty();
void AreBal(char[],int)
int main()
{
  int l=0;
  char str[100];
  printf("Enter a string:");
  gets(str);
  l=strlen(str);
  if(top==-1)
  printf("Balanced");
  else printf("Not Balanced");
  return 0;
}
void Push(int x)
{
  A[++top]=x;
}
void Pop()
{
  top--;
}
int gettop()
{
  return top;
}
int isEmpty()
{
  if(top==-1)
  return 1;
  else return 0;
}
void AreBal(char *exp,int length)
{
  int i;
  for(i=0;i<length;i++)
  if(exp[i]=='(' || exp[i]=='{' || exp[i]=='[')
  Push(exp[i]);
  else 
  if(exp[i]==')' || exp[i]=='}' || exp[i]==']')
  {
     if( isEmpty()==1)
     break;
     else if((exp[i]==')'&& gettop()=='(') || (exp[i]=='}'&& gettop()=='{') || (exp[i]==']'&& gettop()=='['))
     Pop();
     else break;
   } 
   
}
    
  

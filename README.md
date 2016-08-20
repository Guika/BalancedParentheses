# BalancedParentheses
//Code in C to check balanced parentheses(using stack)
#include<stdio.h>
void Push(int);
void Pop();
int top();
int isEmpty();
int AreBal(char[],int)
int A[99],top=-1;
int main()
{
  int l=0;
  char str[100];
  printf("Enter a string:");
  gets(str);
  l=strlen(str);
  if(AreBal(str,l)
  printf("Balanced");
  else printf("Not balanced");
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
int top()
{
  return top;
}
int isEmpty()
{
  if(top==-1)
  return 1;
  else return 0;
}
int AreBal(char *exp,int length)
{
  int i;
  for(i=0;i<length;i++)
  if(exp[i]=='(' || exp[i]=='{' || exp[i]=='[')
  Push(exp[i]);
  else 
  if(exp[i]==')' || exp[i]=='}' || exp[i]==']')
  {
     if( isEmpty()==1)
     return 0;
     else if((exp[i]==')'&& top()=='(') || (exp[i]=='}'&& top()=='{') || (exp[i]==']'&& top()=='['))
     Pop();
   } 
}
    
  

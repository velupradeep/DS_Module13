# Ex2 Conversion of the infix expression into postfix expression
## DATE:01/05/2025
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1.Start the program. 

2.Initialize a stack and set the top index to -1. 

3.Define the push() and pop() functions to add and remove elements from the stack. 

4.Define the priority() function to assign priorities to operators. 

5.Traverse the expression in the IntoPost() function, handling operands, parentheses, and operators. 

6.After processing the expression, pop and print any remaining operators from the stack. 

7.End.

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: PRADEEP V
RegisterNumber:  212223240119
*/
#include<stdio.h> 
#include<ctype.h> 
 
char stack[100]; 
int top = -1; 
void push(char x) 
{ 
stack[++top]=x; 
 
} 
 
char pop() 
{ 
if(top==-1) 
return 0; 
else 
return stack[top--]; 
} 
int priority(char x) 
{ 
if(x=='(') 
  
  
{ 
return 0; 
} 
if(x=='&'||x=='|') 
{ 
return 1; 
} 
if(x=='+'||x=='-') 
{ 
return 2; 
} 
if(x=='*'||x=='/'||x=='%') 
{ 
return 3; 
} 
if(x=='^') 
{ 
return 4; 
} 
return 0; 
} 
char IntoPost(char *exp) 
{ 
char *e,x; 
e=exp; 
while(*e!='\0') 
{ 
if(isalnum(*e)) 
{ 
printf("%c ",*e); 
} 
else if(*e=='(') 
{ 
push(*e); 
} 
else if(*e==')') 
{ 
while((x=pop())!='(') 
printf("%c ",x); 
} 
else 
{ 
while(priority(stack[top])>=priority(*e)) 
printf("%c ",pop()); 
push(*e); 
} 
e++; 
} 
  
  
 
while(top != -1) 
{ 
printf("%c ",pop()); 
}return 0; 
} 
int main() 
{ 
char exp[100]= "2+8*(5^3-1)^(7+9*4)-6";
IntoPost(exp); 
return 1; 
} 

```

## Output:
![437436594-959445f2-99b6-4d1d-b589-fa10c34b04c5](https://github.com/user-attachments/assets/9601029c-6b29-40b5-9b28-6c4ddf642efa)



## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.

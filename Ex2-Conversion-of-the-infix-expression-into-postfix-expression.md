# Ex2 Conversion of the infix expression into postfix expression
## DATE:
## AIM:
To write a C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm
1. Read each character from the infix expression one by one.
2.If the character is an operand, print it immediately.
3.If the character is '(', push it onto the stack; if it is ')', pop and print until '(' is found.
4.If the character is an operator, pop from the stack and print while the top of the stack has higher or equal priority, then push the current operator.
5.After the expression is scanned, pop and print all remaining operators from the stack. 

## Program:
```
/*
Program to convert the infix expression into postfix expression
Developed by: Sharmitha V
RegisterNumber: 212223110048
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
    return stack[top--];
}
int priority(char x)
{
    if(x=='^'){
        return 4;
    }
    if((x=='*')||(x=='%')||(x=='/')){
        return 3;
    }
    if((x=='+')||(x=='-')){
        return 2;
    }
    if((x=='&')||(x=='|')){
        return 1;
    }
    if((x=='(')||(x==')')){
        return 0;
    }
    else{
        return -1;
    }
}
char IntoPost(char *exp)
{
    char x;
    while(*exp != '\0'){
        if(isalnum(*exp)){
            printf("%c ",*exp);
        }
        else if(*exp=='('){
            push(*exp);
        }
        else if(*exp==')'){
            while((x=pop())!='('){
                printf("%c ",x);
            }
        }
        else{
            while(priority(stack[top])>=priority(*exp))
                printf("%c ",pop());
            push(*exp);
        }
        exp++;
    }
    
    while(top != -1)
    {
       printf("%c ",pop());
    }return 0;
}


int main()
{
    char exp[50]="(P%Q)/A*B^C+(R-S/U)+W^V";
    IntoPost(exp);
    return 1;
}

*/
```

## Output:

![image](https://github.com/user-attachments/assets/986b3367-e549-44a2-802d-bf0ee3698780)


## Result:
Thus, the C program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.

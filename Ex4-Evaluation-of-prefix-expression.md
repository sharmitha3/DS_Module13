# Ex4 Evaluation of prefix expression
## DATE:
## AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function . 

## Algorithm
```
1.Scan the prefix expression from right to left.
2.If the character is a digit, convert it to integer and push onto the stack.
3.If the character is an operator, pop two operands from the stack.
4.Perform the operation and push the result back onto the stack.
5.After the loop ends, pop and print the final result from the stack. 
```
## Program:
```
/*
Program to evaluate the given prefix expression
Developed by: Sharmitha V
RegisterNumber:  212223110048
#include<stdio.h>
#include<string.h>
#include<ctype.h>

int s[50];
int top=0;

void push(int ch)
{
	top++;
	s[top]=ch;
}

int pop()
{
	int ch;
	ch=s[top];
	top=top-1;
	return(ch);
}

void evalprefix(char p[50])
{
    int i,n1,n2,n3,num;
   for (i = strlen(p) - 1; i >= 0; i--){
        if(isdigit(p[i])){
            num=p[i] -'0';
            push(num);
        }
        else{
            n1=pop();
            n2=pop();
            switch(p[i]){
                case '+':
                    n3=n1+n2;
                    break;
                case '-':
                n3=n1-n2;
                break;
                case '*':
                n3=n1*n2;
                break;
                case '/':
                n3=n1/n2;
                break;
                }
                push(n3);
            }
        }
        printf("%d",pop());
    }


*/
```

## Output:

![image](https://github.com/user-attachments/assets/8fc44d09-6384-4dbd-9b3f-b8d60e026a65)


## Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.

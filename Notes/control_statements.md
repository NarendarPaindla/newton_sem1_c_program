## 2.1  INTRODUCTION

In the previous chapter, we learnt the basics of problem solving techniques and the C language. In this chapter, we will focus on some of the advanced C programming constructs, such as arrays, functions, structures, and unions. But, first of all, we will begin by exploring the various control statements provided by C. Control statements allow the programmer to manipulate the solution logic by controlling and manipulating the program flow. These statements not only allow you to manipulate the statement execution sequence but also let you repeat the execution of a statement block for certain specified number of times.

At the end of this chapter, we will learn about one of the most important and advanced C programming concepts, called **pointers**.

> **Note** *If you are already familiar with advanced C programming constructs, then you may choose to skip this chapter.*

## 2.2  CONTROL STATEMENTS

C language allows you to manipulate the flow of program control by using various control statements. These control statements are categorized into the following types:

1. **Decision making statements** Decide which actions are to be performed.
2. **Looping statements** Decide how many times an action is to be performed.

One of the significant differences between decision making and looping statements is that the decision making statements direct the flow of program control from top to bottom without any iteration; while, looping statements direct the flow of program control from top to bottom, and then again to the top, in an iterative manner.

A program may contain both decision making as well as looping statements.

### 2.2.1  Decision Making Statements

C language supports the following decision-making statements.

1. If
2. If Else
3. Switch

**1. If** If statement executes a specific set of instructions only if the given expression is true. However, if the expression evaluates to a false value, then the set of instructions are skipped at the time of program execution. A program can contain multiple if statements.

**Syntax**

```c
if(expression)
{
    statement 1;
    statement 2;
    .
    .
    statement n;
}
```

**FLOWCHART**

Figure 2.1 shows the flowchart of if statement

<img width="560" height="395" alt="image" src="https://github.com/user-attachments/assets/98f2dbfd-5a0e-4f8a-abe9-4126c15bec6d" />

**Fig. 2.1** *Flowchart of if statement*

**Example 2.1** Using if statement, write a program to find out if the given number is positive or negative.

**Program 2.1** *Determine whether given number is positive or negative*

```c
#include<stdio.h>
#include<conio.h>
void main()
{
    int num;
    clrscr();
    printf("Enter an integer value: ");
    scanf("%d", &num);
    if(num>0)
    printf("%d is a positive number",num);
    if(num<0)
    printf("%d is a negative number",num);
    getch();
}
```

*If there is only a single statement inside the if block then the braces are not required to be added.*

**Output**

```text
Enter an integer value: -9
-9 is a negative number
```

**Program analysis**

| Key Statement  | Purpose                                                                   |
| -------------- | ------------------------------------------------------------------------- |
| **if(num>=0)** | Uses if statement to check whether *num* is greater than or equal to zero |
| **if(num<0)**  | Uses if statement to check whether *num* is less than zero                |

> **Tip** *Do not add a semicolon at the end of an if expression, otherwise the block of statements specified in the if block will always be executed regardless of the outcome of the conditional expression statement.*

**2. If else statement** **If else statement** comprises two sets of instruction, one each with if and else block. If the given expression statement is true then the if-block instructions are executed. However, if the expression evaluates to a false value, then the if-block instructions are skipped and the else-block instructions are executed. A program can contain multiple if else statements.

**Syntax**

```c
if(expression)
{
    statement 1;
    statement 2;
    .
    .
    statement n;
}
else
{
    statement 1;
    statement 2;
    .
    .
    statement n;
}
```

**FLOWCHART**

Figure 2.2 shows the flowchart of if else statement:

<img width="487" height="361" alt="image" src="https://github.com/user-attachments/assets/de2848e9-3c03-4cac-87cc-5b61412409c4" />


**Fig. 2.2** *Flowchart of if else statement*

**Example 2.2** Using if else statement, write a program to find out if the given number is positive or negative.

**Program 2.2** *Determine whether given number is positive or negative*

```c
#include<stdio.h>
#include<conio.h>
void main()
{
    int num;
    clrscr();
    printf("Enter an integer value: ");
    scanf("%d", &num);
    if(num>=0)
    printf("%d is a positive number",num);
    else
    printf("%d is a negative number",num);
    getch();
}
```

**Output**

```text
Enter an integer value: 22
22 is a positive number
```

**Program analysis**

| Key Statement                                                                                                          | Purpose                                                                          |
| ---------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **if(num>=0)**<br>**printf("%d is a positive number",num);**<br>**else**<br>**printf("%d is a negative number",num);** | if-else block is used to display the output based on the value of *num* variable |

### 3. Switch statement

**Switch statement** is a multi-way selection structure that matches the given expression or variable value with one of a number of integer values, and upon successful match branches to the corresponding statement block. A default value is also specified with the switch statement to take appropriate action in case there is a complete mismatch. **Switch statement** can be considered as an alternative to multiple if statements.

**Syntax**

```c
switch (expression)
{
    case value1:
    <statement block>
    break;
    case value2:
    <statement block>
    break;
    case value3:
    <statement block>
    break;
    .
    .
    .
    default:
    <statement block>
}
```

In the above syntax:

*expression* is the expression to be matched.

*value1, value2,* etc., are constants, also known as case labels.

**FLOWCHART**

Figure 2.3 shows the flowchart of switch statement.

**Fig. 2.3** *Flowchart of switch statement*

**Example 2.3** Using switch statement, write a program to count the frequency of individual digits in a number.

**Program 2.3** *To count the frequency of individual digits in a number*

```c
#include <stdio.h>
#include <conio.h>

void main()
{
long num1,num2;
int temp,d0=0,d1=0,d2=0,d3=0,d4=0,d5=0,d6=0,d7=0,d8=0,d9=0,d0=0;
clrscr();

printf("\nEnter a number:");
scanf("%ld",&num1);

num2=num1;
while(num1!=0)
{
temp=num1%10;
switch(temp) /*Switch statement*/
{
case 1:
    d1++; /*Counting number of Ones*/
    break;
case 2:
    d2++; /*Counting number of Twos*/
    break;
case 3:
    d3++; /*Counting number of Threes*/
    break;
case 4:
    d4++; /*Counting number of Fours*/
    break;
case 5:
    d5++; /*Counting number of Fives*/
    break;
case 0:
    d0++; /*Counting number of Zeros*/
    break;
case 6:
    d6++; /*Counting number of Sixes*/
    break;
case 7:
    d7++; /*Counting number of Sevens*/
    break;
case 8:
    d8++; /*Counting number of Eights*/
    break;
```

```c
case 9:
    d9++; /*Counting number of Nines*/
    break;
default:
    ; /*Do-nothing*/
}
num1=num1/10;
}

/*Displaying the frequency of individual digits in a number*/
printf("\nThe no of 0s in %ld is %ld",num2,d0);
printf("\nThe no of 1s in %ld are %d",num2,d1);
printf("\nThe no of 2s in %ld are %d",num2,d2);
printf("\nThe no of 3s in %ld are %d",num2,d3);
printf("\nThe no of 4s in %ld are %d",num2,d4);
printf("\nThe no of 5s in %ld are %d",num2,d5);
printf("\nThe no of 6s in %ld are %d",num2,d6);
printf("\nThe no of 7s in %ld are %d",num2,d7);
printf("\nThe no of 8s in %ld are %d",num2,d8);
printf("\nThe no of 9s in %ld are %d",num2,d9);

getch();
}
```

**Output**

```text
Enter the number: 889653442

The no of 0s in 889653442 are 0
The no of 1s in 889653442 are 0
The no of 2s in 889653442 are 1
The no of 3s in 889653442 are 1
The no of 4s in 889653442 are 2
The no of 5s in 889653442 are 1
The no of 6s in 889653442 are 1
The no of 7s in 889653442 are 0
The no of 8s in 889653442 are 2
The no of 9s in 889653442 are 1
```

**Program analysis**

| Key Statement                                                               | Purpose                                                                                                                  |
| --------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **while(num1!=0)**                                                          | Uses the while statement to repetitively execute the enclosing statements until the value of *num1* is not equal to zero |
| **switch(temp)**<br>**{**<br>**case 1:**<br>    **d1++;**<br>    **break;** | Uses the switch statement to select the case-block that matches the given expression                                     |

> **Note** *The break statement is inserted with each case block so that the control exits from the switch construct immediately after meeting the true condition; otherwise, all the remaining case blocks will be sequentially validated.*


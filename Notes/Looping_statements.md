## 2.2.2  Looping Statements

C language supports the following looping statements:

1. **While**
2. **Do-While**
3. **For**

**1. While** loop is used for repetitively executing a set of instructions until the specified condition is true. As soon as the condition becomes false, the control is automatically transferred out of the loop. A **while** loop can be considered as an equivalent of a repetitive set of if statements.

**Syntax**

```c
while (expression)
{
    statement 1;
    statement 2;
    .
    .
    statement n;
}
```

Figure 2.4 shows the flowchart of while loop.

**Fig. 2.4** *Flowchart of while loop*

**Example 2.4** Using while loop, write a program to compute the sum of digits of a number.

**Program 2.4** *Sum of digits of a number*

```c
#include <stdio.h>
#include <conio.h>

void main()
{
long num, temp;
int sum=0;
clrscr();
printf("\nEnter an integer value: ");
scanf("%ld",&num);

temp=num;
/*Calculating sum of digits*/
while(temp!=0)
{
sum = sum+temp%10;
temp=temp/10;
}

printf("\nThe sum of digits of %ld is %d",num,sum);
getch();
}
```

**Output**

```text
Enter an integer value: 123456

The sum of digits of 123456 is 21
```

**Program analysis**

| Key Statement | Purpose |
|---|---|
| **while(temp!=0)** | Uses the while statement to repetitively execute the enclosing statements until the value of temp is not equal to zero |
| **temp=temp/10;** | Alters the value of the control variable temp at each iteration of the while loop |

**2. Do-While Loop** Similar to the **while** loop, the **do-while** loop is also used for repetitively executing a set of instructions until the specified condition is true. The difference between **while** loop and **do-while** loop is that in while loop the conditional expression is evaluated first and if it is true, the associated statement block is executed. However, in **do-while** loop the statement block is executed first and then the conditional expression is evaluated. If the expression evaluates to a true value, then the statement block is executed again; else the control is transferred out of the do-while loop. Hence, in case of **do-while** loop, the statement block is executed at least once even if the conditional expression evaluates to a false value at its very first attempt. This is in contrast to the while statement which executes the statement block if and only if the conditional expression is true.

**Syntax**

```c
do
{
    statement 1;
    statement 2;
    .
    .
    statement n;
}while(expression);
```

Figure 2.5 shows the flowchart of do-while loop.

**Fig. 2.5** *Flowchart of do-while loop*

**Example 2.5** Using do-while loop, write a program to compute the sum of digits of a number.

**Program 2.5** *Sum of digits of a number*

```c
#include <stdio.h>
#include <conio.h>

void main()
{
    long num, temp;
    int sum=0;
    clrscr();
    printf("\nEnter an integer value: ");
    scanf("%ld",&num);

    temp=num;
    /*Calculating sum of digits*/
    do
    {
    sum = sum+temp%10;
    temp=temp/10;
    } while(temp!=0);

    printf("\nThe sum of digits of %ld is %d",num,sum);
    getch();
}
```

**Output**

```text
Enter an integer value: 123456

The sum of digits of 123456 is 21
```

**Program analysis**

| Key Statement | Purpose |
|---|---|
| **do** | **do** statement marks the beginning of the do-while block |
| **} while(temp!=0);** | **while** statement, specified at the end of the do-while block, contains the conditional expression for the looping construct |

**3. For Loop** The functionality of **for** loop is exactly the same as **while** loop, however its specification is a little different. It includes the initialization statement, conditional expression and the modifier statement of the loop inside a single one-line **for** statement. At the end of each iteration, the value of the variable is updated as per the modifier expression and the condition is again evaluated. This process continues until the conditional expression holds true. The **for** loop is more compact and easy to implement in comparison to **while** loop.

**Syntax**

```c
for (expression1; expression2; expression3)
{
    statement 1;
    statement 2;
    .
    .
    statement n;
}
```

In the above syntax:

*Expression1* is the initialization statement that initializes the looping variable.

*Expression2* is the conditional expression that states the looping condition.

**Figure 2.6** *Flowchart of for loop*

**Example 2.6** Using for loop, write a program to print integers from 1 to 10.

**Program 2.6** *To print integers from 1 to 10*

```c
#include <stdio.h>
#include <conio.h>

void main()
{
    int i;
    clrscr();
    printf("Integers from 1 to 10:\n");
    for(i=1;i<=10;i++)
    printf("%d\n",i)
    getch();
}
```

**Output**

```text
Integers from 1 to 10
1
2
3
4
5
6
7
8
9
10
```

**Program analysis**

| Key Statement | Purpose |
|---|---|
| **for (i=1;i<=10;i++)** | Uses the **for** statement to repetitively execute the enclosing statements until the given expression is true |
*Expression3* is the modifier expression that modifies the looping variable.

Figure 2.6 shows the flowchart of for loop.

# 1.9  OPERATORS AND EXPRESSIONS

Operators are the symbols that are used to perform arithmetic and logical computations on operands. An operand can be an integer, floating point or character variable; or it can be a constant. Operators and operands together constitute an expression. The output of an expression depends on the data type of the operands.

    The following example illustrates the difference between operators, operands, and expressions:

|                | Example | A * B + 3 |
| -------------- | ------- | --------- |
| **Operators**  |         | *, +      |
| **Operands**   |         | A, B, 3   |
| **Expression** |         | A * B + 3 |

The various types of operators supported by C are:

1. Arithmetic
2. Assignment
3. Bitwise
4. Conditional
5. Increment and Decrement
6. Logical
7. Relational
8. Special

Depending on the number of operands required, the above operators can be classified as unary or binary operators. As the names suggest, unary operators act upon a single operand while binary operators are applied on two operands.

## 1.9.1  Arithmetic Operators

Table 1.9 lists the various arithmetic operators.

**Table 1.9** *Arithmetic operators*

| Name            | Symbol | Description                                                                         | Unary/Binary | Example<br>*(a = 10, b = 5)* |
| --------------- | ------ | ----------------------------------------------------------------------------------- | ------------ | ---------------------------- |
| Addition        | +      | To find sum of two or more operands<br>or<br>To represent a positive operand        | Both         | *a + b = 15*<br>or<br>*+ a*  |
| Subtraction     | −      | To find difference of two or more operands<br>or<br>To represent a negative operand | Both         | *a−b = 5*<br>or<br>*−a*      |
| Multiplication  | *      | To find product of two or more operands                                             | Binary       | *a*b = 50*                   |
| Division        | /      | To divide two or more operands                                                      | Binary       | *a/b = 2*                    |
| Modulo Division | %      | To find remainder of an integer division                                            | Binary       | *a%b = 0*                    |

If an expression has multiple operators with same precedence, then they are executed in the order of their appearance from left to right. That means, the operator, which appears first in the expression is executed first.

## 1.9.2  Assignment Operators

Table 1.10 lists the various assignment operators.

**Table 1.10** *Assignment operators*

| Name                 | Symbol | Description                                                                                                                              | Unary/Binary | Example<br>(a = 10, b = 5)                                                                                                                             |
| -------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------- | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Assignment           | =      | To assign the value of an expression, variable or constant to a variable                                                                 | Binary       | *b = a*<br>Thus, *b = 10*                                                                                                                              |
| Shorthand assignment | +=     | To assign the value of an expression, variable or constant to a variable and perform the specified arithmetic operation on that variable | Binary       | *b += a*<br>This means, that the value of *a* i.e., 10 is added to the value of *b* and the result is assigned to *b* as its new value. Thus, *b = 15* |

## 1.9.3  Bitwise Operators

Bitwise operators are used for manipulating the integers at bit level. The binary representation of the integer get altered as per the type of binary operator applied.

Table 1.11 lists the various bitwise operators.

**Table 1.11** *Bitwise operators*

| Name              | Symbol | Description                                            | Unary/Binary | Example (a = 10, b = 5)  |
| ----------------- | ------ | ------------------------------------------------------ | ------------ | ------------------------ |
| AND               | &      | To perform logical AND operation at bit level          | Binary       | 0101 & 0011 = 0001       |
| OR                | |      | To perform logical OR operation at bit level           | Binary       | 0101 | 0011 = 0111       |
| Exclusive OR      | ^      | To perform logical exclusive OR operation at bit level | Binary       | 0101 & 0011 = 0110       |
| Shift Left        | <<     | To shift the bits to the left                          | Unary        | 00010111 << 1 = 00101110 |
| Shift Right       | >>     | To shift the bits to the right                         | Unary        | 00010111 >> 1 = 00001011 |
| Complement or Not | ~      | To negate each bit of the binary number                | Unary        | ~ 0001 = 1110            |

## 1.9.4  Conditional Operator

Conditional operator (**? :**) is the only ternary operator supported by C. It requires three different expressions, as shown in the syntax below.

```text
<Conditional_Expression> ? <Expression1> : <Expression2>
```
If the conditional expression evaluates to TRUE, then Expression1 is evaluated, else Expression2 is evaluated.

For example, consider the following conditional expression. Assume, a =10 and b = 5:

```text
c = (a + b > 10) ? a : b;
```

When the above statement is executed, the expression (a + b > 10) is evaluated first. Since this condition is true, the value of a is assigned to c.

Now, again consider the following conditional expression:

```text
c = (a + b > 20) ? a : b;
```

When the above statement is executed, the expression (a + b > 20) is evaluated first. Since this condition is false, the value of b is assigned to c.

## 1.9.5  Increment and Decrement Operators

Table 1.12 lists the increment and decrement operators.

**Table 1.12** *Increment and decrement operators*

| Name      | Symbol | Description                           | Unary/Binary | Example<br>(a = 10, b = 5) |
| --------- | ------ | ------------------------------------- | ------------ | -------------------------- |
| Increment | ++     | To increase the value of operand by 1 | Unary        | b = ++a<br>b = 11          |
| Decrement | --     | To decrease the value of operand by 1 | Unary        | b = --a<br>b = 9           |

Increment and decrement operators may be used as a prefix or a postfix in an expression. When used as prefix (example ++a or --b), the operator first changes the variable’s value before the corresponding expression is evaluated. Alternatively, when it used as postfix (for example, a++ or b--), the operator changes the variable’s value after the expression has been evaluated.

For instance, consider the expression,

```text
b = ++a;
```

Assume a = 5

After the above expression is executed, the values of a and b become

```text
b = 6 and a = 6
```

Now, consider the expression

```text
b = a++;
```

Assume a = 5.

After the above expression is executed, the values of a and b become:

```text
b = 5 and a = 6
```

Note that since the increment operator was used as a postfix, the value of variable a changed after the expression was evaluated.

## 1.9.6  Logical Operators

The output of an expression containing logical operators is either 0 or 1. The output of 1 signifies a true condition while 0 signifies a false condition. Table 1.13 lists the various logical operators.
**Table 1.13** *Logical operators*

| Name | Symbol | Description                                              | Unary/Binary | Example<br>(a = 10, b = 5)                                          |
| ---- | ------ | -------------------------------------------------------- | ------------ | ------------------------------------------------------------------- |
| AND  | &&     | To return true if the conditions are true                | Binary       | *a < 20 && b > 6* will return 0 as both the conditions are not true |
| OR   | ||     | To return true if at least one of the conditions is true | Binary       | *a < 20 || b > 6* will return 1 as one of the conditions is true    |
| NOT  | !      | To negate the value of a relational expression           | Unary        | *a < 20* will return 0 as the negated value                         |

Logical operators are typically used in conjunction with relational operators to form logical expressions. Relational operators are explained in the next subsection.

## 1.9.7  Relational Operators

The output of relational operators is either 0 or 1. The output of 1 signifies a true condition while 0 signifies a false condition. Table 1.14 lists the various relational operators.

**Table 1.14** *Relational operators*

| Name                     | Symbol | Description                                                                          | Unary/Binary | Example<br>(a = 10, b = 5)                        |
| ------------------------ | ------ | ------------------------------------------------------------------------------------ | ------------ | ------------------------------------------------- |
| Less than                | <      | To check if the value of one variable is less than the other variable                | Binary       | *a < 20* will return 1 as the condition is true   |
| Less than or equal to    | <=     | To check if the value of one variable is less than or equal to the other variable    | Binary       | *a <= 20* will return 1 as the condition is true  |
| Greater than             | >      | To check if the value of one variable is greater than the other variable             | Binary       | *a > 20* will return 0 as the condition is false  |
| Greater than or equal to | >=     | To check if the value of one variable is greater than or equal to the other variable | Binary       | *a >= 20* will return 0 as the condition is false |
| Equal to                 | ==     | To check if the value of two variables is equal                                      | Binary       | *a == b* will return 0 as the condition is false  |
| Not equal to             | !=     | To check if the value of two variables is not equal                                  | Binary       | *a!=b*, it will return 1 as the condition is true |

As already explained, relational operators are used in conjunction with logical operators to form logical expressions.

## 1.9.8  Special Operators

Table 1.15 lists the special operators.

**Table 1.15** *Special operators*

| Name              | Symbol        | Description                                                                 | Unary/Binary | Example<br>(a = 10, b = 5)                                                                                       |
| ----------------- | ------------- | --------------------------------------------------------------------------- | ------------ | ---------------------------------------------------------------------------------------------------------------- |
| Comma             | ,             | To link the related expressions together                                    | Binary       | *x = (a = 10, b = 5, c = a−b);*<br>will assign *c = 5*<br>Comma operator is also used inside while and for loops |
| **Sizeof**        | **sizeof();** | To retrieve the number of bytes a variable or a constant occupies in memory | Unary        | *x = sizeof (a);* will assign the size of variable *a* to x                                                      |
| Pointer operators | &, *          | To work with pointers                                                       | Unary        | *&a* retrieves the address of variable *a*<br>**a* retrieves the value references by pointer variable *a*        |

## 1.9.9  Precedence of Operators

The precedence order of operators is the order in which operators are executed in an expression. Table 1.16 lists the precedence of operators from highest to lowest level.

**Table 1.16** *Precedence of operators*

| Precedence Level | Operators              |
| ---------------- | ---------------------- |
| 1                | -, ++, --, !, sizeof() |
| 2                | *, /, %                |
| 3                | +, −                   |
| 4                | <, <=, >, >=, =        |
| 5                | ==, !=                 |
| 6                | &&                     |
| 7                | ||                     |
| 8                | ,                      |

**Example 1.8** Write a program to accept two complex numbers and find their sum.

**Program 1.5** *To accept two complex numbers and find their sum*
```c
#include <stdio.h>
#include <conio.h>
#include <math.h>

void main()
{
struct complex
{
    double real;
    double img;
};

struct complex c1, c2, c3;
clrscr();
printf("\n Enter two Complex Numbers (x+iy):\n\n Real Part of First Number: ");
scanf("%lf",&c1.real);
printf("\n Imaginary Part of First Number: ");
scanf("%lf",&c1.img);
printf("\n Real Part of Second Number: ");
scanf("%lf",&c2.real);
printf("\n Imaginary Part of Second Number: ");
scanf("%lf",&c2.img);
c3.real=c1.real+c2.real;
c3.img=c1.img+c2.img;
printf("\n\n%.2lf+(%.2lf)i + %.2lf+(%.2lf)i = %.2lf+(%.2lf)i", c1.real,
c1.img, c2.real, c2.img, c3.real, c3.img);
getch();
}
```

**Output**

```text
Enter two Complex Numbers (x+iy):

    Real Part of First Number: 22

    Imaginary Part of First Number: 4

    Real Part of Second Number: 5

    Imaginary Part of Second Number: 3


22.00+(4.00)i + 5.00+(3.00)i = 27.00+(7.00)i
```

**Program analysis**

| Key Statement                                                                | Purpose                                            |
| ---------------------------------------------------------------------------- | -------------------------------------------------- |
| **struct complex**<br>**{**<br>**double real;**<br>**double img;**<br>**};** | Defines a structure named *complex*                |
| **struct complex c1, c2, c3;**                                               | Declares structure variables                       |
| **c3.real=c1.real+c2.real;**                                                 | Performs arithmetic operation on structure members |

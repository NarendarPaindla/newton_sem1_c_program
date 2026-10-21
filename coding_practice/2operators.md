# C Operators & Expressions — Hands-On Programming
---

## 1. Shopping Bill Calculator 🛒

### Question

A student buys a notebook for ₹50 and a pen for ₹20. He buys 3 notebooks and 2 pens.

Write a C program to calculate the **total bill**.

### Answer

```c
#include <stdio.h>

int main()
{
    int notebookPrice = 50;
    int penPrice = 20;

    int notebooks = 3;
    int pens = 2;

    int total;

    total = (notebookPrice * notebooks) +
            (penPrice * pens);

    printf("Total Bill = %d", total);

    return 0;
}
```

### Output

```text
Total Bill = 190
```

### Operators used

```text
*  → Multiplication
+  → Addition
=  → Assignment
```

---

# 2. Mini Calculator 🧮

### Question

Take two integers as input and display:

* Addition
* Subtraction
* Multiplication
* Division
* Remainder

### Answer

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    printf("Addition = %d\n", a + b);
    printf("Subtraction = %d\n", a - b);
    printf("Multiplication = %d\n", a * b);
    printf("Division = %d\n", a / b);
    printf("Remainder = %d", a % b);

    return 0;
}
```

### Input

```text
Enter two numbers: 20 6
```

### Output

```text
Addition = 26
Subtraction = 14
Multiplication = 120
Division = 3
Remainder = 2
```

### Operators used

```text
+  -  *  /  %
```

---

# 3. Even or Odd Detective 🔍

### Question

Take an integer from the user and determine whether it is **even or odd** using the modulus operator.

### Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number % 2 == 0)
    {
        printf("%d is Even", number);
    }
    else
    {
        printf("%d is Odd", number);
    }

    return 0;
}
```

### Input

```text
Enter a number: 27
```

### Output

```text
27 is Odd
```

### Important expression

```c
number % 2 == 0
```

This contains:

```text
%  → Modulus
== → Equality comparison
```

---

# 4. Student Pass or Fail 🎓

### Question

Take a student's marks as input.

If marks are **40 or above**, display:

```text
Pass
```

Otherwise display:

```text
Fail
```

### Answer

```c
#include <stdio.h>

int main()
{
    int marks;

    printf("Enter marks: ");
    scanf("%d", &marks);

    if (marks >= 40)
    {
        printf("Pass");
    }
    else
    {
        printf("Fail");
    }

    return 0;
}
```

### Input

```text
Enter marks: 67
```

### Output

```text
Pass
```

### Operator used

```text
>=
```

---

# 5. Bigger of Two Numbers 🏆

### Question

Take two numbers as input and display which number is bigger.

### Answer

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    if (a > b)
    {
        printf("%d is bigger", a);
    }
    else if (b > a)
    {
        printf("%d is bigger", b);
    }
    else
    {
        printf("Both numbers are equal");
    }

    return 0;
}
```

### Input

```text
Enter two numbers: 45 72
```

### Output

```text
72 is bigger
```

### Operators used

```text
>
```

---

# 6. Electricity Bill ⚡

### Question

An electricity company charges ₹5 per unit.

Take the number of units consumed as input and calculate the bill.

### Answer

```c
#include <stdio.h>

int main()
{
    int units;
    int rate = 5;
    int bill;

    printf("Enter units consumed: ");
    scanf("%d", &units);

    bill = units * rate;

    printf("Electricity Bill = Rs.%d", bill);

    return 0;
}
```

### Input

```text
Enter units consumed: 120
```

### Output

```text
Electricity Bill = Rs.600
```

### Expression

```c
bill = units * rate;
```

---

# 7. Student Eligibility Checker 🎯

### Question

A student is eligible for an examination only when:

* Attendance is at least 75%
* Assignment is submitted

Take attendance and assignment status as input.

Use:

```text
1 → Assignment submitted
0 → Assignment not submitted
```

### Answer

```c
#include <stdio.h>

int main()
{
    int attendance;
    int assignmentSubmitted;

    printf("Enter attendance percentage: ");
    scanf("%d", &attendance);

    printf("Assignment submitted? (1-Yes, 0-No): ");
    scanf("%d", &assignmentSubmitted);

    if (attendance >= 75 && assignmentSubmitted == 1)
    {
        printf("Eligible for examination");
    }
    else
    {
        printf("Not eligible for examination");
    }

    return 0;
}
```

### Input

```text
Enter attendance percentage: 82
Assignment submitted? (1-Yes, 0-No): 1
```

### Output

```text
Eligible for examination
```

### Operators used

```text
>=
&&
==
```

This is a good program for introducing **logical AND**.

---

# 8. Increment Counter 🔢

### Question

A counter starts from 5.

Increase it by 1 three times using the increment operator `++`.

Display the value after every increment.

### Answer

```c
#include <stdio.h>

int main()
{
    int counter = 5;

    counter++;
    printf("After first increment = %d\n", counter);

    counter++;
    printf("After second increment = %d\n", counter);

    counter++;
    printf("After third increment = %d", counter);

    return 0;
}
```

### Output

```text
After first increment = 6
After second increment = 7
After third increment = 8
```

### Operator

```c
counter++;
```

is equivalent to:

```c
counter = counter + 1;
```

---

# 9. Pre-Increment vs Post-Increment 🧠

### Question

Predict the output before running the program.

```c
#include <stdio.h>

int main()
{
    int x = 5;
    int a, b;

    a = x++;
    b = ++x;

    printf("a = %d\n", a);
    printf("b = %d\n", b);
    printf("x = %d", x);

    return 0;
}
```

### Answer

Let's trace it.

Initially:

```text
x = 5
```

First:

```c
a = x++;
```

`x++` uses the old value first:

```text
a = 5
x = 6
```

Then:

```c
b = ++x;
```

`++x` increments first:

```text
x = 7
b = 7
```

### Output

```text
a = 5
b = 7
x = 7
```

### Memory trick

```text
x++ → Use first, increase later

++x → Increase first, use later
```

---

# 10. Expression Challenge 🔥

### Question

Write a C program to take three integers `a`, `b`, and `c` and calculate:

```text
result = (a + b) * c
```

Then also calculate:

```text
result2 = a + b * c
```

Observe the difference caused by **operator precedence and parentheses**.

### Answer

```c
#include <stdio.h>

int main()
{
    int a, b, c;
    int result1, result2;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    result1 = (a + b) * c;
    result2 = a + b * c;

    printf("With parentheses = %d\n", result1);
    printf("Without parentheses = %d", result2);

    return 0;
}
```

### Input

```text
Enter three numbers: 10 5 2
```

### Calculation

With parentheses:

```text
(10 + 5) × 2
= 15 × 2
= 30
```

Without parentheses:

```text
10 + 5 × 2
= 10 + 10
= 20
```

### Output

```text
With parentheses = 30
Without parentheses = 20
```
---

# Quick Revision — Operators Covered

| Program | Main concept             |
| ------- | ------------------------ |
| 1       | `+`, `*`                 |
| 2       | `+`, `-`, `*`, `/`, `%`  |
| 3       | `%`, `==`                |
| 4       | `>=`                     |
| 5       | `>`                      |
| 6       | `*`, `=`                 |
| 7       | `>=`, `&&`, `==`         |
| 8       | `++`                     |
| 9       | `++x`, `x++`             |
| 10      | Parentheses & precedence |

---

## 11. Shopping Discount Calculator 🛍️

### Question

A product costs ₹2000. A discount of 15% is given.

Calculate and display:

* Discount amount
* Final price

### Answer

```c
#include <stdio.h>

int main()
{
    float price = 2000;
    float discount = 15;
    float discountAmount;
    float finalPrice;

    discountAmount = price * discount / 100;
    finalPrice = price - discountAmount;

    printf("Original Price = %.2f\n", price);
    printf("Discount Amount = %.2f\n", discountAmount);
    printf("Final Price = %.2f", finalPrice);

    return 0;
}
```

### Output

```text
Original Price = 2000.00
Discount Amount = 300.00
Final Price = 1700.00
```

### Operators

```text
*  /  -
```

---

# 12. Compound Assignment Challenge

### Question

Start with:

```text
x = 100
```

Perform the following operations:

```text
Add 20
Subtract 10
Multiply by 2
Divide by 5
```

Use **compound assignment operators**.

### Answer

```c
#include <stdio.h>

int main()
{
    int x = 100;

    x += 20;
    printf("After += 20: %d\n", x);

    x -= 10;
    printf("After -= 10: %d\n", x);

    x *= 2;
    printf("After *= 2: %d\n", x);

    x /= 5;
    printf("After /= 5: %d", x);

    return 0;
}
```

### Output

```text
After += 20: 120
After -= 10: 110
After *= 2: 220
After /= 5: 44
```

### Operators

```text
+=
-=
*=
/=
```

---

# 13. Multiple of 5 and 10

### Question

Take a number from the user.

Check whether the number is divisible by **both 5 and 10**.

### Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number % 5 == 0 && number % 10 == 0)
    {
        printf("The number is divisible by both 5 and 10");
    }
    else
    {
        printf("The number is not divisible by both 5 and 10");
    }

    return 0;
}
```

### Input

```text
Enter a number: 50
```

### Output

```text
The number is divisible by both 5 and 10
```

### Concepts

```text
%
==
&&
```

---

# 14. College Admission Eligibility 🎓

### Question

A student can get admission if:

* Marks are at least 60
* AND entrance test score is at least 50

Take both values as input and display whether the student is eligible.

### Answer

```c
#include <stdio.h>

int main()
{
    int marks;
    int entranceScore;

    printf("Enter marks: ");
    scanf("%d", &marks);

    printf("Enter entrance test score: ");
    scanf("%d", &entranceScore);

    if (marks >= 60 && entranceScore >= 50)
    {
        printf("Eligible for admission");
    }
    else
    {
        printf("Not eligible for admission");
    }

    return 0;
}
```

### Input

```text
Enter marks: 75
Enter entrance test score: 62
```

### Output

```text
Eligible for admission
```

### Main operator

```c
&&
```

---

# 15. Weekend Detector 📅

### Question

Take a number representing a day:

```text
1 → Monday
2 → Tuesday
3 → Wednesday
4 → Thursday
5 → Friday
6 → Saturday
7 → Sunday
```

Check whether the given day is a weekend.

### Answer

```c
#include <stdio.h>

int main()
{
    int day;

    printf("Enter day number: ");
    scanf("%d", &day);

    if (day == 6 || day == 7)
    {
        printf("It is a weekend");
    }
    else
    {
        printf("It is a working day");
    }

    return 0;
}
```

### Input

```text
Enter day number: 7
```

### Output

```text
It is a weekend
```

### Main operators

```text
==
||
```

---

# 16. Ternary Operator — Bigger Number 🏆

### Question

Take two numbers and find the bigger number using the **conditional/ternary operator**.

Do not use `if-else`.

### Answer

```c
#include <stdio.h>

int main()
{
    int a, b;
    int bigger;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    bigger = (a > b) ? a : b;

    printf("Bigger number = %d", bigger);

    return 0;
}
```

### Input

```text
Enter two numbers: 45 72
```

### Output

```text
Bigger number = 72
```

### Important expression

```c
(a > b) ? a : b
```

Meaning:

```text
condition?
   ↓
YES → a
NO  → b
```

---

# 17. Type Casting — Average Challenge

### Question

A student gets:

```text
English = 85
Maths = 90
Science = 88
```

Calculate the average using **type casting** and display it with two decimal places.

### Answer

```c
#include <stdio.h>

int main()
{
    int english = 85;
    int maths = 90;
    int science = 88;

    float average;

    average = (float)(english + maths + science) / 3;

    printf("Average = %.2f", average);

    return 0;
}
```

### Output

```text
Average = 87.67
```

### Important expression

```c
(float)(english + maths + science) / 3
```

Type casting converts the integer expression to `float` before division.

---

# 18. `sizeof()` Data Type Detective 🔍

### Question

Write a program to display the size of different data types.

Display the size of:

* `char`
* `short`
* `int`
* `long`
* `long long`
* `float`
* `double`

### Answer

```c
#include <stdio.h>

int main()
{
    printf("char      = %zu bytes\n", sizeof(char));
    printf("short     = %zu bytes\n", sizeof(short));
    printf("int       = %zu bytes\n", sizeof(int));
    printf("long      = %zu bytes\n", sizeof(long));
    printf("long long = %zu bytes\n", sizeof(long long));
    printf("float     = %zu bytes\n", sizeof(float));
    printf("double    = %zu bytes\n", sizeof(double));

    return 0;
}
```

### Typical Output

```text
char      = 1 bytes
short     = 2 bytes
int       = 4 bytes
long      = 8 bytes
long long = 8 bytes
float     = 4 bytes
double    = 8 bytes
```

**Note:** Sizes other than `char` are implementation-dependent and can vary by system/compiler.

---

# 19. Expression Mystery 🧠

### Question

Predict the output before running the program.

```c
#include <stdio.h>

int main()
{
    int result;

    result = 10 + 20 * 3 - 5;

    printf("Result = %d", result);

    return 0;
}
```

### Answer

First:

```text
20 × 3 = 60
```

Then:

```text
10 + 60 - 5
```

Therefore:

```text
65
```

### Output

```text
Result = 65
```

### Why?

Multiplication has higher precedence than addition/subtraction.

---

# 20. The Ultimate Expression Challenge 🔥

### Question

Predict the output **without executing the program**.

```c
#include <stdio.h>

int main()
{
    int a = 10;
    int b = 5;
    int c = 2;

    int result;

    result = a + b * c > 15 && a != c;

    printf("Result = %d", result);

    return 0;
}
```

### Answer

First:

```text
b * c
= 5 * 2
= 10
```

Then:

```text
a + 10
= 10 + 10
= 20
```

Then:

```text
20 > 15
```

Result:

```text
1
```

Next:

```text
a != c
```

```text
10 != 2
```

Result:

```text
1
```

Then:

```text
1 && 1
```

Result:

```text
1
```

### Output

```text
Result = 1
```

---

# 🔥 What Students Have Covered After 20 Programs

| Program | Main Concept             |
| ------- | ------------------------ |
| 1       | Arithmetic               |
| 2       | All basic arithmetic     |
| 3       | Modulus + equality       |
| 4       | Relational               |
| 5       | Comparison               |
| 6       | Arithmetic expressions   |
| 7       | Logical AND              |
| 8       | Increment                |
| 9       | Pre/Post increment       |
| 10      | Parentheses + precedence |
| 11      | Percentage expression    |
| 12      | Compound assignment      |
| 13      | Modulus + logical AND    |
| 14      | Logical AND              |
| 15      | Logical OR               |
| 16      | Ternary operator         |
| 17      | Type casting             |
| 18      | `sizeof`                 |
| 19      | Operator precedence      |
| 20      | Complex expression       |

### Final challenge for the class

After these 20, give students this **without the answer**:

```c
#include <stdio.h>

int main()
{
    int a = 5;
    int b = 10;
    int c = 2;

    int result;

    result = ++a + b * c--;

    printf("a = %d\n", a);
    printf("b = %d\n", b);
    printf("c = %d\n", c);
    printf("result = %d", result);

    return 0;
}
```

# C Operators & Expressions — Programs 21–30

## 21. Calculate Simple Interest

### Question

Take principal amount, rate of interest, and time as input. Calculate simple interest.

Formula:

```text
SI = (P × R × T) / 100
```

### Answer

```c
#include <stdio.h>

int main()
{
    float principal, rate, time, interest;

    printf("Enter principal: ");
    scanf("%f", &principal);

    printf("Enter rate: ");
    scanf("%f", &rate);

    printf("Enter time: ");
    scanf("%f", &time);

    interest = (principal * rate * time) / 100;

    printf("Simple Interest = %.2f", interest);

    return 0;
}
```

### Input

```text
Enter principal: 10000
Enter rate: 5
Enter time: 2
```

### Output

```text
Simple Interest = 1000.00
```

---

## 22. Calculate Remaining Balance

### Question

A bank account has an initial balance. Take the amount deposited and amount withdrawn. Calculate the final balance using compound assignment operators.

### Answer

```c
#include <stdio.h>

int main()
{
    float balance, deposit, withdrawal;

    printf("Enter initial balance: ");
    scanf("%f", &balance);

    printf("Enter deposit: ");
    scanf("%f", &deposit);

    printf("Enter withdrawal: ");
    scanf("%f", &withdrawal);

    balance += deposit;
    balance -= withdrawal;

    printf("Final Balance = %.2f", balance);

    return 0;
}
```

### Input

```text
Enter initial balance: 5000
Enter deposit: 2000
Enter withdrawal: 1500
```

### Output

```text
Final Balance = 5500.00
```

---

## 23. Check Positive, Negative or Zero

### Question

Take an integer and determine whether it is:

* Positive
* Negative
* Zero

### Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number > 0)
    {
        printf("Positive");
    }
    else if (number < 0)
    {
        printf("Negative");
    }
    else
    {
        printf("Zero");
    }

    return 0;
}
```

### Input

```text
Enter a number: -25
```

### Output

```text
Negative
```

---

## 24. Check Divisibility

### Question

Take a number and check whether it is divisible by both 3 and 5.

### Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number % 3 == 0 && number % 5 == 0)
    {
        printf("Divisible by both 3 and 5");
    }
    else
    {
        printf("Not divisible by both 3 and 5");
    }

    return 0;
}
```

### Input

```text
Enter a number: 45
```

### Output

```text
Divisible by both 3 and 5
```

---

## 25. Driving Eligibility 🚗

### Question

Take a person's age as input.

If the age is between 18 and 60 inclusive, display:

```text
Eligible to apply
```

Otherwise display:

```text
Not eligible
```

### Answer

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    if (age >= 18 && age <= 60)
    {
        printf("Eligible to apply");
    }
    else
    {
        printf("Not eligible");
    }

    return 0;
}
```

### Input

```text
Enter age: 25
```

### Output

```text
Eligible to apply
```

---

## 26. Find the Largest of Three Numbers

### Question

Take three integers and find the largest using relational and logical operators.

### Answer

```c
#include <stdio.h>

int main()
{
    int a, b, c;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a >= b && a >= c)
    {
        printf("Largest = %d", a);
    }
    else if (b >= a && b >= c)
    {
        printf("Largest = %d", b);
    }
    else
    {
        printf("Largest = %d", c);
    }

    return 0;
}
```

### Input

```text
Enter three numbers: 25 48 32
```

### Output

```text
Largest = 48
```

---

## 27. Pass, Fail or Distinction

### Question

Take marks as input.

Use the following rules:

```text
90 and above → Distinction
40 to 89     → Pass
Below 40     → Fail
```

### Answer

```c
#include <stdio.h>

int main()
{
    int marks;

    printf("Enter marks: ");
    scanf("%d", &marks);

    if (marks >= 90)
    {
        printf("Distinction");
    }
    else if (marks >= 40)
    {
        printf("Pass");
    }
    else
    {
        printf("Fail");
    }

    return 0;
}
```

### Input

```text
Enter marks: 94
```

### Output

```text
Distinction
```

---

## 28. Even Number and Positive Number

### Question

Take an integer and check whether it is **both positive and even**.

### Answer

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter a number: ");
    scanf("%d", &number);

    if (number > 0 && number % 2 == 0)
    {
        printf("Positive Even Number");
    }
    else
    {
        printf("Condition not satisfied");
    }

    return 0;
}
```

### Input

```text
Enter a number: 24
```

### Output

```text
Positive Even Number
```

---

## 29. Find the Smaller Number Using Ternary Operator

### Question

Take two integers and find the smaller number using the ternary operator.

### Answer

```c
#include <stdio.h>

int main()
{
    int a, b;
    int smaller;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    smaller = (a < b) ? a : b;

    printf("Smaller number = %d", smaller);

    return 0;
}
```

### Input

```text
Enter two numbers: 35 18
```

### Output

```text
Smaller number = 18
```

---

## 30. Expression Evaluation Challenge 🔥

### Question

Take three integers `a`, `b`, and `c`.

Calculate:

```text
result = a + b * c - a / b
```

Display the result.

Also calculate:

```text
result2 = (a + b) * (c - a) / b
```

### Answer

```c
#include <stdio.h>

int main()
{
    int a, b, c;
    int result1, result2;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    result1 = a + b * c - a / b;
    result2 = (a + b) * (c - a) / b;

    printf("Expression 1 = %d\n", result1);
    printf("Expression 2 = %d", result2);

    return 0;
}
```

### Input

```text
Enter three numbers: 10 5 4
```

### Calculation

First expression:

```text
10 + 5 * 4 - 10 / 5
= 10 + 20 - 2
= 28
```

Second expression:

```text
(10 + 5) * (4 - 10) / 5
= 15 * (-6) / 5
= -18
```

### Output

```text
Expression 1 = 28
Expression 2 = -18
```

---

## Programs 21–30 Coverage

| Program | Main concepts                          |
| ------- | -------------------------------------- |
| 21      | Arithmetic expression                  |
| 22      | `+=`, `-=`                             |
| 23      | `>`, `<`                               |
| 24      | `%`, `==`, `&&`                        |
| 25      | `>=`, `<=`, `&&`                       |
| 26      | Relational + logical                   |
| 27      | Relational + expressions               |
| 28      | `%`, `>`, `&&`                         |
| 29      | Ternary `?:`                           |
| 30      | Precedence + parentheses + expressions |


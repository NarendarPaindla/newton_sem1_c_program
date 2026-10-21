# C Programming — `for` Loop Practice
## Programs 1–10

---

## 1. Print Numbers from 1 to N

### Question
Write a C program to read a number `N` and print all numbers from `1` to `N`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

### Expected Input
```text
Enter N: 5
```

### Expected Output
```text
1
2
3
4
5
```

### Why this is important
This is the **basic counting pattern** of a `for` loop. It helps understand initialization, condition, and increment.

### Where it is used
Used whenever you need to process items **one by one from a starting point to an ending point**, such as student records, array elements, or numbered tasks.

---

# 2. Print Numbers from N to 1

### Question
Write a C program to read `N` and print numbers from `N` down to `1`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = n; i >= 1; i--)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

### Expected Input
```text
Enter N: 5
```

### Expected Output
```text
5
4
3
2
1
```

### Why this is important
This introduces **decrementing loops** and teaches you how to control the direction of a loop.

### Where it is used
Useful for **countdowns, reverse processing, rankings, and processing data from the end toward the beginning**.

---

# 3. Print Even Numbers from 1 to N

### Question
Write a C program to read `N` and print all even numbers from `1` to `N`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        if (i % 2 == 0)
        {
            printf("%d\n", i);
        }
    }

    return 0;
}
```

### Expected Input
```text
Enter N: 10
```

### Expected Output
```text
2
4
6
8
10
```

### Why this is important
This combines a **loop with a decision statement**. You learn how `for` and `if` work together.

### Where it is used
Used when processing only specific items from a collection, such as **even-numbered records, positions, or values**.

---

# 4. Print Odd Numbers from 1 to N

### Question
Write a C program to read `N` and print all odd numbers from `1` to `N`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        if (i % 2 != 0)
        {
            printf("%d\n", i);
        }
    }

    return 0;
}
```

### Expected Input
```text
Enter N: 10
```

### Expected Output
```text
1
3
5
7
9
```

### Why this is important
It gives practice with the **modulus operator `%` inside a loop**.

### Where it is used
Useful when separating data into categories such as **odd/even positions, alternating operations, or filtering values**.

---

# 5. Print Multiplication Table

### Question
Write a C program to read a number and print its multiplication table from `1` to `10`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter number: ");
    scanf("%d", &n);

    for (int i = 1; i <= 10; i++)
    {
        printf("%d x %d = %d\n", n, i, n * i);
    }

    return 0;
}
```

### Expected Input
```text
Enter number: 5
```

### Expected Output
```text
5 x 1 = 5
5 x 2 = 10
5 x 3 = 15
5 x 4 = 20
5 x 5 = 25
5 x 6 = 30
5 x 7 = 35
5 x 8 = 40
5 x 9 = 45
5 x 10 = 50
```

### Why this is important
This teaches how to perform a **calculation repeatedly** using a changing loop variable.

### Where it is used
The same concept is used in **repeated calculations, mathematical tables, billing systems, and data processing**.

---

# 6. Find the Sum of Numbers from 1 to N

### Question
Write a C program to read `N` and calculate the sum of all numbers from `1` to `N`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;
    int sum = 0;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        sum = sum + i;
    }

    printf("Sum = %d", sum);

    return 0;
}
```

### Expected Input
```text
Enter N: 5
```

### Expected Output
```text
Sum = 15
```

Because:

```text
1 + 2 + 3 + 4 + 5 = 15
```

### Why this is important
This introduces the **accumulator pattern**:

```c
sum = sum + i;
```

This is one of the most important patterns in programming.

### Where it is used
Used for **totals, marks calculation, sales totals, transaction amounts, statistics, and aggregation of data**.

---

# 7. Find the Sum of Even Numbers

### Question
Write a C program to read `N` and calculate the sum of all even numbers from `1` to `N`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;
    int sum = 0;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        if (i % 2 == 0)
        {
            sum = sum + i;
        }
    }

    printf("Sum of even numbers = %d", sum);

    return 0;
}
```

### Expected Input
```text
Enter N: 10
```

### Expected Output
```text
Sum of even numbers = 30
```

Because:

```text
2 + 4 + 6 + 8 + 10 = 30
```

### Why this is important
This combines three important concepts:

```text
for loop
   +
if condition
   +
accumulator
```

### Where it is used
This pattern is useful when you need to **filter data and then calculate something** from the selected values.

---

# 8. Count Even and Odd Numbers

### Question
Write a C program to read `N` and count how many even and odd numbers exist between `1` and `N`.

### Code
```c
#include <stdio.h>

int main()
{
    int n;
    int evenCount = 0;
    int oddCount = 0;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        if (i % 2 == 0)
        {
            evenCount++;
        }
        else
        {
            oddCount++;
        }
    }

    printf("Even numbers = %d\n", evenCount);
    printf("Odd numbers = %d", oddCount);

    return 0;
}
```

### Expected Input
```text
Enter N: 10
```

### Expected Output
```text
Even numbers = 5
Odd numbers = 5
```

### Why this is important
This introduces the **counter pattern**:

```c
count++;
```

Students need this pattern frequently in programming.

### Where it is used
Used for **counting students who passed, counting positive/negative values, counting search results, and analyzing data**.

---

# 9. Find the Factorial of a Number

### Question
Write a C program to read a number and calculate its factorial.

For example:

```text
5! = 5 × 4 × 3 × 2 × 1 = 120
```

### Code
```c
#include <stdio.h>

int main()
{
    int n;
    long long factorial = 1;

    printf("Enter number: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        factorial = factorial * i;
    }

    printf("Factorial = %lld", factorial);

    return 0;
}
```

### Expected Input
```text
Enter number: 5
```

### Expected Output
```text
Factorial = 120
```

### Why this is important
This teaches another important accumulation pattern:

```c
factorial = factorial * i;
```

It is also an excellent introduction to problems that later connect to **recursion**.

### Where it is used
Factorials appear in **combinations, permutations, probability, mathematics, and algorithm problems**.

---

# 10. Find the Largest Number Among N Numbers

### Question
Write a C program to read `N` numbers and find the largest number.

### Code
```c
#include <stdio.h>

int main()
{
    int n, number, largest;

    printf("Enter how many numbers: ");
    scanf("%d", &n);

    printf("Enter number 1: ");
    scanf("%d", &largest);

    for (int i = 2; i <= n; i++)
    {
        printf("Enter number %d: ", i);
        scanf("%d", &number);

        if (number > largest)
        {
            largest = number;
        }
    }

    printf("Largest = %d", largest);

    return 0;
}
```

### Expected Input
```text
Enter how many numbers: 5
Enter number 1: 25
Enter number 2: 78
Enter number 3: 42
Enter number 4: 91
Enter number 5: 36
```

### Expected Output
```text
Largest = 91
```

### Why this is important
This introduces the **search/comparison pattern**:

```text
Take first value as largest
        ↓
Compare next value
        ↓
If bigger → update largest
        ↓
Continue
```

This is a fundamental algorithmic pattern.

### Where it is used
It is directly useful for finding **highest marks, highest salary, maximum score, maximum price, largest array element**, and many other real-world values.

---

# Patterns Learned in Programs 1–10

```text
1. Counting
2. Reverse counting
3. Filtering even numbers
4. Filtering odd numbers
5. Repeated calculation
6. Accumulator — sum
7. Filter + accumulator
8. Counter
9. Multiplication accumulator — factorial
10. Searching for maximum
```

The important patterns to remember are:

```c
// Counting
i++;

// Reverse counting
i--;

// Counter
count++;

// Sum
sum = sum + value;

// Product
product = product * value;

// Find maximum
if (value > largest)
{
    largest = value;
}
```

## FOR LOOP — PROGRAMS 11–20

### 11. Find the Smallest Among N Numbers

**Question:**  
Write a C program to read N numbers and find the smallest number using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n, number, smallest;

    printf("Enter N: ");
    scanf("%d", &n);

    printf("Enter %d numbers:\n", n);
    scanf("%d", &smallest);

    for (int i = 2; i <= n; i++)
    {
        scanf("%d", &number);

        if (number < smallest)
        {
            smallest = number;
        }
    }

    printf("Smallest = %d", smallest);

    return 0;
}
```

**Expected Input:**
```text
Enter N: 5
Enter 5 numbers:
25 78 42 12 36
```

**Expected Output:**
```text
Smallest = 12
```

**Why this is important:**  
It teaches the **minimum-search pattern** using comparison.

**Where it is used:**  
Finding the lowest marks, minimum price, minimum temperature, shortest time, etc.

---

### 12. Calculate Average of N Numbers

**Question:**  
Write a C program to read N numbers and calculate their average using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n, number;
    int sum = 0;
    float average;

    printf("Enter N: ");
    scanf("%d", &n);

    printf("Enter %d numbers:\n", n);

    for (int i = 1; i <= n; i++)
    {
        scanf("%d", &number);
        sum = sum + number;
    }

    average = (float)sum / n;

    printf("Sum = %d\n", sum);
    printf("Average = %.2f", average);

    return 0;
}
```

**Expected Input:**
```text
Enter N: 5
Enter 5 numbers:
10 20 30 40 50
```

**Expected Output:**
```text
Sum = 150
Average = 30.00
```

**Why this is important:**  
It combines **loop + accumulator + type casting**.

**Where it is used:**  
Student marks, employee salaries, sales data, temperatures, ratings, etc.

---

### 13. Count Positive, Negative and Zero Numbers

**Question:**  
Write a C program to read N numbers and count how many are positive, negative, and zero.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n, number;
    int positive = 0, negative = 0, zero = 0;

    printf("Enter N: ");
    scanf("%d", &n);

    printf("Enter %d numbers:\n", n);

    for (int i = 1; i <= n; i++)
    {
        scanf("%d", &number);

        if (number > 0)
        {
            positive++;
        }
        else if (number < 0)
        {
            negative++;
        }
        else
        {
            zero++;
        }
    }

    printf("Positive = %d\n", positive);
    printf("Negative = %d\n", negative);
    printf("Zero = %d", zero);

    return 0;
}
```

**Expected Input:**
```text
Enter N: 6
Enter 6 numbers:
10 -5 0 20 -8 0
```

**Expected Output:**
```text
Positive = 2
Negative = 2
Zero = 2
```

**Why this is important:**  
It teaches **classification + counting** inside a loop.

**Where it is used:**  
Data analysis, result processing, sensor data, financial records, etc.

---

### 14. Find the Sum of Digits

**Question:**  
Write a C program to find the sum of all digits of a number using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n, digit, sum = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    for (; n > 0; n = n / 10)
    {
        digit = n % 10;
        sum = sum + digit;
    }

    printf("Sum of digits = %d", sum);

    return 0;
}
```

**Expected Input:**
```text
Enter a number: 12345
```

**Expected Output:**
```text
Sum of digits = 15
```

**Why this is important:**  
It introduces the important **digit-processing pattern** using `% 10` and `/ 10`.

**Where it is used:**  
Number processing, digit validation, checksum calculations, and mathematical algorithms.

---

### 15. Reverse a Number

**Question:**  
Write a C program to reverse a given number using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n, digit, reverse = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    for (; n > 0; n = n / 10)
    {
        digit = n % 10;
        reverse = reverse * 10 + digit;
    }

    printf("Reverse = %d", reverse);

    return 0;
}
```

**Expected Input:**
```text
Enter a number: 12345
```

**Expected Output:**
```text
Reverse = 54321
```

**Why this is important:**  
It teaches how to process a number **digit by digit**.

**Where it is used:**  
Palindrome checking, number manipulation, validation algorithms, and mathematical programming.

---

### 16. Check Whether a Number is Palindrome

**Question:**  
Write a C program to check whether a given number is a palindrome using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n, original, digit, reverse = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    original = n;

    for (; n > 0; n = n / 10)
    {
        digit = n % 10;
        reverse = reverse * 10 + digit;
    }

    if (original == reverse)
    {
        printf("%d is a Palindrome", original);
    }
    else
    {
        printf("%d is not a Palindrome", original);
    }

    return 0;
}
```

**Expected Input:**
```text
Enter a number: 121
```

**Expected Output:**
```text
121 is a Palindrome
```

**Why this is important:**  
It combines **digit extraction + reverse + comparison**.

**Where it is used:**  
String/number validation and algorithmic problem solving.

---

### 17. Calculate Power of a Number

**Question:**  
Write a C program to calculate `base^exponent` using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int base, exponent;
    int result = 1;

    printf("Enter base: ");
    scanf("%d", &base);

    printf("Enter exponent: ");
    scanf("%d", &exponent);

    for (int i = 1; i <= exponent; i++)
    {
        result = result * base;
    }

    printf("Result = %d", result);

    return 0;
}
```

**Expected Input:**
```text
Enter base: 2
Enter exponent: 5
```

**Expected Output:**
```text
Result = 32
```

**Why this is important:**  
It teaches the **repeated multiplication** pattern.

**Where it is used:**  
Mathematical calculations, scientific computing, algorithms, and numerical programming.

---

### 18. Check Whether a Number is Prime

**Question:**  
Write a C program to check whether a given number is prime using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n, count = 0;

    printf("Enter a number: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        if (n % i == 0)
        {
            count++;
        }
    }

    if (count == 2)
    {
        printf("%d is a Prime Number", n);
    }
    else
    {
        printf("%d is not a Prime Number", n);
    }

    return 0;
}
```

**Expected Input:**
```text
Enter a number: 17
```

**Expected Output:**
```text
17 is a Prime Number
```

**Why this is important:**  
It teaches **divisibility and counting factors**.

**Where it is used:**  
Number theory, cryptography, hashing, security algorithms, and competitive programming.

---

### 19. Print All Factors of a Number

**Question:**  
Write a C program to print all factors of a given number using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    printf("Factors of %d are:\n", n);

    for (int i = 1; i <= n; i++)
    {
        if (n % i == 0)
        {
            printf("%d ", i);
        }
    }

    return 0;
}
```

**Expected Input:**
```text
Enter a number: 24
```

**Expected Output:**
```text
Factors of 24 are:
1 2 3 4 6 8 12 24
```

**Why this is important:**  
It builds understanding of **divisibility and factors**, which is useful for prime-number problems.

**Where it is used:**  
Mathematics, number theory, GCD/LCM problems, and algorithm design.

---

### 20. Print the First N Natural Numbers and Their Squares

**Question:**  
Write a C program to print the first N natural numbers along with their squares using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    printf("Number\tSquare\n");

    for (int i = 1; i <= n; i++)
    {
        printf("%d\t%d\n", i, i * i);
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 5
```

**Expected Output:**
```text
Number  Square
1       1
2       4
3       9
4       16
5       25
```

**Why this is important:**  
It teaches repeated calculation and formatted output inside a loop.

**Where it is used:**  
Generating mathematical tables, reports, calculations, and data-processing programs.

---

### Important `for` loop patterns covered in 11–20

```c
// Minimum
if (number < smallest)
    smallest = number;

// Maximum
if (number > largest)
    largest = number;

// Sum
sum = sum + number;

// Average
average = (float)sum / n;

// Counter
count++;

// Digit extraction
digit = n % 10;

// Remove last digit
n = n / 10;

// Reverse
reverse = reverse * 10 + digit;

// Repeated multiplication
result = result * base;

// Factor checking
if (n % i == 0)
```

These patterns will be useful when moving to **nested `for` loops and pattern programs in 21–30**.

# FOR LOOP — PROGRAMS 21–30

### 21. Print Multiplication Tables from 1 to N

**Question:**  
Write a C program to print multiplication tables from `1` to `N`.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        printf("\nTable of %d:\n", i);

        for (int j = 1; j <= 10; j++)
        {
            printf("%d x %d = %d\n", i, j, i * j);
        }
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 3
```

**Expected Output:**
```text
Table of 1:
1 x 1 = 1
1 x 2 = 2
...
1 x 10 = 10

Table of 2:
2 x 1 = 2
2 x 2 = 4
...
2 x 10 = 20

Table of 3:
3 x 1 = 3
3 x 2 = 6
...
3 x 10 = 30
```

**Why this is important:**  
Introduces **nested `for` loops**, where one loop runs inside another.

**Where it is used:**  
Tables, matrices, grids, reports, and repeated multi-level processing.

---

### 22. Print a Square Pattern of Stars

**Question:**  
Write a C program to print a square pattern of `*` using nested `for` loops.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= n; j++)
        {
            printf("* ");
        }

        printf("\n");
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 4
```

**Expected Output:**
```text
* * * *
* * * *
* * * *
* * * *
```

**Why this is important:**  
Helps understand how **rows and columns** work with nested loops.

**Where it is used:**  
Pattern generation, grids, tables, matrix operations, and UI layouts.

---

### 23. Print a Right-Angled Triangle Pattern

**Question:**  
Write a C program to print a right-angled triangle using `*`.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= i; j++)
        {
            printf("* ");
        }

        printf("\n");
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 5
```

**Expected Output:**
```text
*
* *
* * *
* * * *
* * * * *
```

**Why this is important:**  
Shows how the **inner loop depends on the outer loop**.

**Where it is used:**  
Pattern problems and developing logic for nested-loop algorithms.

---

### 24. Print an Inverted Triangle Pattern

**Question:**  
Write a C program to print an inverted right-angled triangle.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = n; i >= 1; i--)
    {
        for (int j = 1; j <= i; j++)
        {
            printf("* ");
        }

        printf("\n");
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 5
```

**Expected Output:**
```text
* * * * *
* * * *
* * *
* *
*
```

**Why this is important:**  
Strengthens understanding of **decreasing loop limits**.

**Where it is used:**  
Pattern generation and problems involving reverse iteration.

---

### 25. Print a Number Triangle

**Question:**  
Write a C program to print the following number pattern.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= i; j++)
        {
            printf("%d ", j);
        }

        printf("\n");
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 5
```

**Expected Output:**
```text
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

**Why this is important:**  
Teaches how to control the **value printed by the inner loop**.

**Where it is used:**  
Pattern problems, nested iterations, and sequence generation.

---

### 26. Print Floyd's Triangle

**Question:**  
Write a C program to print Floyd's triangle.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;
    int number = 1;

    printf("Enter N: ");
    scanf("%d", &n);

    for (int i = 1; i <= n; i++)
    {
        for (int j = 1; j <= i; j++)
        {
            printf("%d ", number);
            number++;
        }

        printf("\n");
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 5
```

**Expected Output:**
```text
1
2 3
4 5 6
7 8 9 10
11 12 13 14 15
```

**Why this is important:**  
Introduces the concept of a **variable that continuously changes across nested loops**.

**Where it is used:**  
Sequence generation, matrix-style processing, and algorithmic pattern problems.

---

### 27. Print Prime Numbers from 1 to N

**Question:**  
Write a C program to print all prime numbers between `1` and `N`.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    printf("Prime numbers are:\n");

    for (int number = 2; number <= n; number++)
    {
        int count = 0;

        for (int i = 1; i <= number; i++)
        {
            if (number % i == 0)
            {
                count++;
            }
        }

        if (count == 2)
        {
            printf("%d ", number);
        }
    }

    return 0;
}
```

**Expected Input:**
```text
Enter N: 20
```

**Expected Output:**
```text
Prime numbers are:
2 3 5 7 11 13 17 19
```

**Why this is important:**  
Combines **nested loops, divisibility, counting, and decision making**.

**Where it is used:**  
Number theory, cryptography, security algorithms, and competitive programming.

---

### 28. Find GCD of Two Numbers

**Question:**  
Write a C program to find the GCD (Greatest Common Divisor) of two numbers using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int a, b, gcd = 1;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    for (int i = 1; i <= a && i <= b; i++)
    {
        if (a % i == 0 && b % i == 0)
        {
            gcd = i;
        }
    }

    printf("GCD = %d", gcd);

    return 0;
}
```

**Expected Input:**
```text
Enter two numbers: 24 36
```

**Expected Output:**
```text
GCD = 12
```

**Why this is important:**  
Teaches how to find a value satisfying **multiple conditions simultaneously**.

**Where it is used:**  
Fractions, number theory, cryptography, scheduling, and mathematical algorithms.

---

### 29. Find LCM of Two Numbers

**Question:**  
Write a C program to find the LCM (Least Common Multiple) of two numbers using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int a, b, lcm;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    for (int i = 1; ; i++)
    {
        int value = a * i;

        if (value % b == 0)
        {
            lcm = value;
            break;
        }
    }

    printf("LCM = %d", lcm);

    return 0;
}
```

**Expected Input:**
```text
Enter two numbers: 12 18
```

**Expected Output:**
```text
LCM = 36
```

**Why this is important:**  
Introduces a loop that continues until a required condition is satisfied and demonstrates `break`.

**Where it is used:**  
Scheduling repeated events, fractions, mathematics, and synchronization problems.

---

### 30. Generate Fibonacci Series

**Question:**  
Write a C program to print the first N terms of the Fibonacci series using a `for` loop.

**Code:**
```c
#include <stdio.h>

int main()
{
    int n;
    int first = 0, second = 1, next;

    printf("Enter number of terms: ");
    scanf("%d", &n);

    printf("Fibonacci Series:\n");

    for (int i = 1; i <= n; i++)
    {
        printf("%d ", first);

        next = first + second;
        first = second;
        second = next;
    }

    return 0;
}
```

**Expected Input:**
```text
Enter number of terms: 10
```

**Expected Output:**
```text
Fibonacci Series:
0 1 1 2 3 5 8 13 21 34
```

**Why this is important:**  
Teaches how to **update multiple variables inside a loop** and is an important step toward understanding recursion and dynamic programming.

**Where it is used:**  
Algorithm problems, recursion, dynamic programming, mathematical modeling, and sequence generation.

---

## Important patterns from Programs 21–30

```c
// Nested loop
for (int i = 1; i <= n; i++)
{
    for (int j = 1; j <= n; j++)
    {
        // work
    }
}
```

```c
// Increasing inner loop
for (int j = 1; j <= i; j++)
```

```c
// Decreasing outer loop
for (int i = n; i >= 1; i--)
```

```c
// Continue until condition becomes true
for (int i = 1; ; i++)
{
    if (condition)
    {
        break;
    }
}
```

```c
// Multiple variable update
next = first + second;
first = second;
second = next;
```

### Concepts covered across all 30 programs

1. Counting
2. Reverse counting
3. Even/odd filtering
4. Accumulators
5. Counters
6. Maximum/minimum
7. Average
8. Digit processing
9. Reverse number
10. Palindrome
11. Power
12. Prime numbers
13. Factors
14. Nested loops
15. Patterns
16. GCD
17. LCM
18. Fibonacci
19. `break`
20. Multiple-variable updates


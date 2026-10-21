# C Programming — Control Statements Practice

## Questions 1–10

### 1. Check Whether a Number is Positive or Negative

**Question:** Write a C program to read a number and check whether it is positive or negative.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter number: ");
    scanf("%d", &number);

    if (number >= 0)
    {
        printf("Positive");
    }
    else
    {
        printf("Negative");
    }

    return 0;
}
```

**Input:**

```text
Enter number: 25
```

**Output:**

```text
Positive
```

---

### 2. Check Even or Odd

**Question:** Write a C program to read an integer and check whether it is even or odd.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter number: ");
    scanf("%d", &number);

    if (number % 2 == 0)
    {
        printf("Even");
    }
    else
    {
        printf("Odd");
    }

    return 0;
}
```

**Input:**

```text
Enter number: 17
```

**Output:**

```text
Odd
```

---

### 3. Check Pass or Fail

**Question:** Write a C program to read marks. If marks are 40 or above, display `Pass`; otherwise display `Fail`.

**Answer:**

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

**Input:**

```text
Enter marks: 68
```

**Output:**

```text
Pass
```

---

### 4. Find the Bigger of Two Numbers

**Question:** Write a C program to read two numbers and display the bigger number. If both are equal, display `Both are equal`.

**Answer:**

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
        printf("Both are equal");
    }

    return 0;
}
```

**Input:**

```text
Enter two numbers: 45 72
```

**Output:**

```text
72 is bigger
```

---

### 5. Check Positive, Negative, or Zero

**Question:** Write a C program to read a number and display whether it is positive, negative, or zero.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter number: ");
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

**Input:**

```text
Enter number: -12
```

**Output:**

```text
Negative
```

---

### 6. Calculate Grade

**Question:** Write a C program to read marks and display the grade using the following conditions:

```text
90 and above → A
75 to 89     → B
60 to 74     → C
40 to 59     → D
Below 40     → F
```

**Answer:**

```c
#include <stdio.h>

int main()
{
    int marks;

    printf("Enter marks: ");
    scanf("%d", &marks);

    if (marks >= 90)
    {
        printf("Grade A");
    }
    else if (marks >= 75)
    {
        printf("Grade B");
    }
    else if (marks >= 60)
    {
        printf("Grade C");
    }
    else if (marks >= 40)
    {
        printf("Grade D");
    }
    else
    {
        printf("Grade F");
    }

    return 0;
}
```

**Input:**

```text
Enter marks: 82
```

**Output:**

```text
Grade B
```

---

### 7. Check Voting Eligibility

**Question:** Write a C program to read age. If age is 18 or above, display `Eligible to Vote`; otherwise display `Not Eligible to Vote`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    if (age >= 18)
    {
        printf("Eligible to Vote");
    }
    else
    {
        printf("Not Eligible to Vote");
    }

    return 0;
}
```

**Input:**

```text
Enter age: 20
```

**Output:**

```text
Eligible to Vote
```

---

### 8. Display Day Using `switch`

**Question:** Write a C program to read a number from 1 to 7 and display the corresponding day.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int day;

    printf("Enter day number: ");
    scanf("%d", &day);

    switch (day)
    {
        case 1:
            printf("Monday");
            break;

        case 2:
            printf("Tuesday");
            break;

        case 3:
            printf("Wednesday");
            break;

        case 4:
            printf("Thursday");
            break;

        case 5:
            printf("Friday");
            break;

        case 6:
            printf("Saturday");
            break;

        case 7:
            printf("Sunday");
            break;

        default:
            printf("Invalid day");
    }

    return 0;
}
```

**Input:**

```text
Enter day number: 5
```

**Output:**

```text
Friday
```

---

### 9. Simple Calculator Using `switch`

**Question:** Write a C program to read two integers and a choice.

```text
1 → Addition
2 → Subtraction
3 → Multiplication
4 → Division
```

Perform the selected operation.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int a, b, choice;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("3. Multiplication\n");
    printf("4. Division\n");

    printf("Enter choice: ");
    scanf("%d", &choice);

    switch (choice)
    {
        case 1:
            printf("Result = %d", a + b);
            break;

        case 2:
            printf("Result = %d", a - b);
            break;

        case 3:
            printf("Result = %d", a * b);
            break;

        case 4:
            printf("Result = %d", a / b);
            break;

        default:
            printf("Invalid choice");
    }

    return 0;
}
```

**Input:**

```text
Enter two numbers: 20 5
1. Addition
2. Subtraction
3. Multiplication
4. Division
Enter choice: 3
```

**Output:**

```text
Result = 100
```

---

### 10. Vowel or Consonant Using `switch`

**Question:** Write a C program to read a character and check whether it is a vowel or consonant.

**Answer:**

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    switch (ch)
    {
        case 'a':
        case 'e':
        case 'i':
        case 'o':
        case 'u':
        case 'A':
        case 'E':
        case 'I':
        case 'O':
        case 'U':
            printf("Vowel");
            break;

        default:
            printf("Consonant");
    }

    return 0;
}
```

**Input:**

```text
Enter a character: E
```

**Output:**

```text
Vowel
```

### Concepts covered in 1–10

```text
1. if-else
2. if-else
3. if-else
4. else-if
5. else-if
6. else-if ladder
7. if-else
8. switch + break + default
9. switch + arithmetic operations


# C Programming — Control Statements Practice

## Questions 11–20

### 11. Find the Largest of Three Numbers

**Question:** Write a C program to read three integers and display the largest number.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int a, b, c;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a >= b && a >= c)
    {
        printf("%d is largest", a);
    }
    else if (b >= a && b >= c)
    {
        printf("%d is largest", b);
    }
    else
    {
        printf("%d is largest", c);
    }

    return 0;
}
```

**Input:**

```text
Enter three numbers: 25 78 45
```

**Output:**

```text
78 is largest
```

---

### 12. Find the Smallest of Three Numbers

**Question:** Write a C program to read three integers and display the smallest number.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int a, b, c;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a <= b && a <= c)
    {
        printf("%d is smallest", a);
    }
    else if (b <= a && b <= c)
    {
        printf("%d is smallest", b);
    }
    else
    {
        printf("%d is smallest", c);
    }

    return 0;
}
```

**Input:**

```text
Enter three numbers: 25 78 12
```

**Output:**

```text
12 is smallest
```

---

### 13. Check Divisibility by 3 and 5

**Question:** Write a C program to read an integer and determine whether it is divisible by both 3 and 5, only by 3, only by 5, or neither.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter number: ");
    scanf("%d", &number);

    if (number % 3 == 0 && number % 5 == 0)
    {
        printf("Divisible by both 3 and 5");
    }
    else if (number % 3 == 0)
    {
        printf("Divisible only by 3");
    }
    else if (number % 5 == 0)
    {
        printf("Divisible only by 5");
    }
    else
    {
        printf("Not divisible by 3 or 5");
    }

    return 0;
}
```

**Input:**

```text
Enter number: 45
```

**Output:**

```text
Divisible by both 3 and 5
```

---

### 14. Age Category

**Question:** Read a person's age and display:

```text
Below 13  → Child
13–19     → Teenager
20–59     → Adult
60+       → Senior Citizen
```

**Answer:**

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    if (age < 13)
    {
        printf("Child");
    }
    else if (age <= 19)
    {
        printf("Teenager");
    }
    else if (age <= 59)
    {
        printf("Adult");
    }
    else
    {
        printf("Senior Citizen");
    }

    return 0;
}
```

**Input:**

```text
Enter age: 17
```

**Output:**

```text
Teenager
```

---

### 15. Check Leap Year

**Question:** Write a C program to read a year and check whether it is a leap year.

A year is a leap year if it is divisible by 400, or if it is divisible by 4 but not by 100.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int year;

    printf("Enter year: ");
    scanf("%d", &year);

    if (year % 400 == 0)
    {
        printf("Leap Year");
    }
    else if (year % 100 == 0)
    {
        printf("Not a Leap Year");
    }
    else if (year % 4 == 0)
    {
        printf("Leap Year");
    }
    else
    {
        printf("Not a Leap Year");
    }

    return 0;
}
```

**Input:**

```text
Enter year: 2024
```

**Output:**

```text
Leap Year
```

---

### 16. Check Uppercase, Lowercase, or Digit

**Question:** Read a character and determine whether it is an uppercase letter, lowercase letter, or digit.

**Answer:**

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    if (ch >= 'A' && ch <= 'Z')
    {
        printf("Uppercase Letter");
    }
    else if (ch >= 'a' && ch <= 'z')
    {
        printf("Lowercase Letter");
    }
    else if (ch >= '0' && ch <= '9')
    {
        printf("Digit");
    }
    else
    {
        printf("Special Character");
    }

    return 0;
}
```

**Input:**

```text
Enter a character: G
```

**Output:**

```text
Uppercase Letter
```

---

### 17. Month Days Using `switch`

**Question:** Read a month number and display the number of days.

For this problem:

```text
January, March, May, July, August, October, December → 31
April, June, September, November → 30
February → 28
```

**Answer:**

```c
#include <stdio.h>

int main()
{
    int month;

    printf("Enter month number: ");
    scanf("%d", &month);

    switch (month)
    {
        case 1:
        case 3:
        case 5:
        case 7:
        case 8:
        case 10:
        case 12:
            printf("31 days");
            break;

        case 4:
        case 6:
        case 9:
        case 11:
            printf("30 days");
            break;

        case 2:
            printf("28 days");
            break;

        default:
            printf("Invalid month");
    }

    return 0;
}
```

**Input:**

```text
Enter month number: 4
```

**Output:**

```text
30 days
```

---

### 18. Simple Menu Using `switch`

**Question:** Create a menu:

```text
1 → Display Hello
2 → Display Welcome
3 → Display Good Morning
4 → Exit
```

Read the user's choice and display the corresponding message.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int choice;

    printf("1. Hello\n");
    printf("2. Welcome\n");
    printf("3. Good Morning\n");
    printf("4. Exit\n");

    printf("Enter choice: ");
    scanf("%d", &choice);

    switch (choice)
    {
        case 1:
            printf("Hello");
            break;

        case 2:
            printf("Welcome");
            break;

        case 3:
            printf("Good Morning");
            break;

        case 4:
            printf("Exit");
            break;

        default:
            printf("Invalid Choice");
    }

    return 0;
}
```

**Input:**

```text
1. Hello
2. Welcome
3. Good Morning
4. Exit
Enter choice: 2
```

**Output:**

```text
Welcome
```

---

### 19. Electricity Bill Using `if-else if`

**Question:** Calculate an electricity bill based on units:

```text
0–100 units      → ₹2 per unit
101–200 units    → ₹4 per unit
201–300 units    → ₹6 per unit
Above 300        → ₹8 per unit
```

**Answer:**

```c
#include <stdio.h>

int main()
{
    int units;
    float bill;

    printf("Enter units: ");
    scanf("%d", &units);

    if (units <= 100)
    {
        bill = units * 2;
    }
    else if (units <= 200)
    {
        bill = units * 4;
    }
    else if (units <= 300)
    {
        bill = units * 6;
    }
    else
    {
        bill = units * 8;
    }

    printf("Electricity Bill = %.2f", bill);

    return 0;
}
```

**Input:**

```text
Enter units: 250
```

**Output:**

```text
Electricity Bill = 1500.00
```

---

### 20. Nested `if` — Admission Eligibility

**Question:** A student is eligible for admission only if:

* Marks are at least 60
* Attendance is at least 75%

Write a C program using **nested `if`**.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int marks, attendance;

    printf("Enter marks: ");
    scanf("%d", &marks);

    printf("Enter attendance percentage: ");
    scanf("%d", &attendance);

    if (marks >= 60)
    {
        if (attendance >= 75)
        {
            printf("Eligible for Admission");
        }
        else
        {
            printf("Not Eligible: Attendance is low");
        }
    }
    else
    {
        printf("Not Eligible: Marks are low");
    }

    return 0;
}
```

**Input:**

```text
Enter marks: 78
Enter attendance percentage: 82
```

**Output:**

```text
Eligible for Admission
```
# C Programming — Control Statements Practice

## Questions 21–30

### 21. Check Driving Eligibility

**Question:** Read the age of a person. Display `Eligible to Drive` if the age is between 18 and 60, otherwise display `Not Eligible`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    if (age >= 18 && age <= 60)
    {
        printf("Eligible to Drive");
    }
    else
    {
        printf("Not Eligible");
    }

    return 0;
}
```

**Input:**

```text
Enter age: 25
```

**Output:**

```text
Eligible to Drive
```

---

### 22. Check Divisibility by 5 and 10

**Question:** Read an integer and check whether it is divisible by both 5 and 10.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int number;

    printf("Enter number: ");
    scanf("%d", &number);

    if (number % 5 == 0 && number % 10 == 0)
    {
        printf("Divisible by both 5 and 10");
    }
    else
    {
        printf("Not divisible by both 5 and 10");
    }

    return 0;
}
```

**Input:**

```text
Enter number: 50
```

**Output:**

```text
Divisible by both 5 and 10
```

---

### 23. Find the Middle Number

**Question:** Read three different integers and display the number that lies between the other two.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int a, b, c;

    printf("Enter three numbers: ");
    scanf("%d %d %d", &a, &b, &c);

    if ((a > b && a < c) || (a < b && a > c))
    {
        printf("%d is the middle number", a);
    }
    else if ((b > a && b < c) || (b < a && b > c))
    {
        printf("%d is the middle number", b);
    }
    else
    {
        printf("%d is the middle number", c);
    }

    return 0;
}
```

**Input:**

```text
Enter three numbers: 10 30 20
```

**Output:**

```text
20 is the middle number
```

---

### 24. Student Result Classification

**Question:** Read marks and display:

```text
90–100 → Distinction
75–89  → First Class
60–74  → Second Class
40–59  → Pass
Below 40 → Fail
```

**Answer:**

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
    else if (marks >= 75)
    {
        printf("First Class");
    }
    else if (marks >= 60)
    {
        printf("Second Class");
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

**Input:**

```text
Enter marks: 93
```

**Output:**

```text
Distinction
```

---

### 25. Character Type Using `switch`

**Question:** Read a character and use `switch` to check whether it is a vowel.

**Answer:**

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    switch (ch)
    {
        case 'a':
        case 'e':
        case 'i':
        case 'o':
        case 'u':
        case 'A':
        case 'E':
        case 'I':
        case 'O':
        case 'U':
            printf("Vowel");
            break;

        default:
            printf("Not a Vowel");
    }

    return 0;
}
```

**Input:**

```text
Enter a character: o
```

**Output:**

```text
Vowel
```

---

### 26. Arithmetic Operator Using `switch`

**Question:** Read two numbers and an arithmetic operator (`+`, `-`, `*`, `/`). Perform the selected operation using `switch`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    float a, b;
    char op;

    printf("Enter two numbers: ");
    scanf("%f %f", &a, &b);

    printf("Enter operator: ");
    scanf(" %c", &op);

    switch (op)
    {
        case '+':
            printf("Result = %.2f", a + b);
            break;

        case '-':
            printf("Result = %.2f", a - b);
            break;

        case '*':
            printf("Result = %.2f", a * b);
            break;

        case '/':
            if (b != 0)
            {
                printf("Result = %.2f", a / b);
            }
            else
            {
                printf("Cannot divide by zero");
            }
            break;

        default:
            printf("Invalid operator");
    }

    return 0;
}
```

**Input:**

```text
Enter two numbers: 15 4
Enter operator: *
```

**Output:**

```text
Result = 60.00
```

---

### 27. Check Triangle Type

**Question:** Read three sides of a triangle and determine whether it is:

```text
Equilateral → all three sides equal
Isosceles   → any two sides equal
Scalene     → all sides different
```

**Answer:**

```c
#include <stdio.h>

int main()
{
    int a, b, c;

    printf("Enter three sides: ");
    scanf("%d %d %d", &a, &b, &c);

    if (a == b && b == c)
    {
        printf("Equilateral Triangle");
    }
    else if (a == b || b == c || a == c)
    {
        printf("Isosceles Triangle");
    }
    else
    {
        printf("Scalene Triangle");
    }

    return 0;
}
```

**Input:**

```text
Enter three sides: 5 5 8
```

**Output:**

```text
Isosceles Triangle
```

---

### 28. Traffic Signal Using `switch`

**Question:** Read a character representing a traffic signal:

```text
R → Stop
Y → Ready
G → Go
```

Use `switch`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    char signal;

    printf("Enter signal: ");
    scanf(" %c", &signal);

    switch (signal)
    {
        case 'R':
        case 'r':
            printf("Stop");
            break;

        case 'Y':
        case 'y':
            printf("Ready");
            break;

        case 'G':
        case 'g':
            printf("Go");
            break;

        default:
            printf("Invalid Signal");
    }

    return 0;
}
```

**Input:**

```text
Enter signal: G
```

**Output:**

```text
Go
```

---

### 29. Scholarship Eligibility

**Question:** A student is eligible for a scholarship if:

* Percentage is at least 85
* Attendance is at least 75

Read percentage and attendance and display the result.

**Answer:**

```c
#include <stdio.h>

int main()
{
    float percentage;
    int attendance;

    printf("Enter percentage: ");
    scanf("%f", &percentage);

    printf("Enter attendance: ");
    scanf("%d", &attendance);

    if (percentage >= 85 && attendance >= 75)
    {
        printf("Eligible for Scholarship");
    }
    else
    {
        printf("Not Eligible for Scholarship");
    }

    return 0;
}
```

**Input:**

```text
Enter percentage: 91.5
Enter attendance: 82
```

**Output:**

```text
Eligible for Scholarship
```

---

### 30. Menu-Driven Unit Converter

**Question:** Create a menu:

```text
1 → Kilometers to Meters
2 → Meters to Centimeters
3 → Kilograms to Grams
4 → Celsius to Fahrenheit
```

Read the choice and value, then perform the selected conversion using `switch`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int choice;
    float value, result;

    printf("1. Kilometers to Meters\n");
    printf("2. Meters to Centimeters\n");
    printf("3. Kilograms to Grams\n");
    printf("4. Celsius to Fahrenheit\n");

    printf("Enter choice: ");
    scanf("%d", &choice);

    printf("Enter value: ");
    scanf("%f", &value);

    switch (choice)
    {
        case 1:
            result = value * 1000;
            printf("Result = %.2f meters", result);
            break;

        case 2:
            result = value * 100;
            printf("Result = %.2f centimeters", result);
            break;

        case 3:
            result = value * 1000;
            printf("Result = %.2f grams", result);
            break;

        case 4:
            result = (value * 9 / 5) + 32;
            printf("Result = %.2f Fahrenheit", result);
            break;

        default:
            printf("Invalid Choice");
    }

    return 0;
}
```

**Input:**

```text
1. Kilometers to Meters
2. Meters to Centimeters
3. Kilograms to Grams
4. Celsius to Fahrenheit
Enter choice: 4
Enter value: 25
```

**Output:**

```text
Result = 77.00 Fahrenheit
```

10. switch + multiple cases
```

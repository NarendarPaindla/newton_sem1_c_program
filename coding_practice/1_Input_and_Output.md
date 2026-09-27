# C Programming — `printf()` and `scanf()` Practice

### 1. Read and Print an Integer

Write a C program to read the **age** of a person using `scanf()` and display it using `printf()`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int age;

    printf("Enter age: ");
    scanf("%d", &age);

    printf("Age = %d", age);

    return 0;
}
```

**Input:**

```text
Enter age: 21
```

**Output:**

```text
Age = 21
```

---

### 2. Read and Print a Float

Write a C program to read the **height** of a person in meters and print it with **2 decimal places**.

**Answer:**

```c
#include <stdio.h>

int main()
{
    float height;

    printf("Enter height: ");
    scanf("%f", &height);

    printf("Height = %.2f meters", height);

    return 0;
}
```

**Input:**

```text
Enter height: 1.75
```

**Output:**

```text
Height = 1.75 meters
```

---

### 3. Read and Print a Double

Write a C program to read a **bank balance** using `double` and display it with **2 decimal places**.

**Answer:**

```c
#include <stdio.h>

int main()
{
    double balance;

    printf("Enter balance: ");
    scanf("%lf", &balance);

    printf("Balance = %.2lf", balance);

    return 0;
}
```

**Input:**

```text
Enter balance: 45678.567
```

**Output:**

```text
Balance = 45678.57
```

---

### 4. Read and Print a Character

Write a C program to read a **single character** and display it.

**Answer:**

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    printf("Character = %c", ch);

    return 0;
}
```

**Input:**

```text
Enter a character: A
```

**Output:**

```text
Character = A
```

---

### 5. Read Multiple Data Types

Write a C program to read:

* Age → `int`
* Height → `float`
* Grade → `char`

Display all the values.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int age;
    float height;
    char grade;

    printf("Enter age: ");
    scanf("%d", &age);

    printf("Enter height: ");
    scanf("%f", &height);

    printf("Enter grade: ");
    scanf(" %c", &grade);

    printf("\nAge = %d", age);
    printf("\nHeight = %.2f", height);
    printf("\nGrade = %c", grade);

    return 0;
}
```

**Input:**

```text
Enter age: 20
Enter height: 5.8
Enter grade: A
```

**Output:**

```text
Age = 20
Height = 5.80
Grade = A
```

---

### 6. Read Two Integers and Print Their Sum

Write a C program to read two integers and display their sum.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int a, b, sum;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    sum = a + b;

    printf("Sum = %d", sum);

    return 0;
}
```

**Input:**

```text
Enter two numbers: 25 35
```

**Output:**

```text
Sum = 60
```

---

### 7. Read Two Float Values

Write a C program to read the **price of a product** and **quantity**, then calculate and display the total amount.

Use `float` for the price.

**Answer:**

```c
#include <stdio.h>

int main()
{
    float price;
    int quantity;
    float total;

    printf("Enter price: ");
    scanf("%f", &price);

    printf("Enter quantity: ");
    scanf("%d", &quantity);

    total = price * quantity;

    printf("Total = %.2f", total);

    return 0;
}
```

**Input:**

```text
Enter price: 125.50
Enter quantity: 4
```

**Output:**

```text
Total = 502.00
```

---

### 8. Read a Long Integer

Write a C program to read the **population of a city** using `long` and display it.

**Answer:**

```c
#include <stdio.h>

int main()
{
    long population;

    printf("Enter population: ");
    scanf("%ld", &population);

    printf("Population = %ld", population);

    return 0;
}
```

**Input:**

```text
Enter population: 1250000
```

**Output:**

```text
Population = 1250000
```

---

### 9. Read a Long Long Integer

Write a C program to read a very large number using `long long` and display it.

**Answer:**

```c
#include <stdio.h>

int main()
{
    long long number;

    printf("Enter number: ");
    scanf("%lld", &number);

    printf("Number = %lld", number);

    return 0;
}
```

**Input:**

```text
Enter number: 987654321012
```

**Output:**

```text
Number = 987654321012
```

---

### 10. Read and Print an Unsigned Integer

Write a C program to read the **number of students in a college** using `unsigned int` and display it.

**Answer:**

```c
#include <stdio.h>

int main()
{
    unsigned int students;

    printf("Enter number of students: ");
    scanf("%u", &students);

    printf("Number of students = %u", students);

    return 0;
}
```

**Input:**

```text
Enter number of students: 2500
```

**Output:**

```text
Number of students = 2500
```

### Quick Format Practice

| Data Type      | `scanf()` | `printf()`    |
| -------------- | --------- | ------------- |
| `char`         | `%c`      | `%c`          |
| `int`          | `%d`      | `%d`          |
| `unsigned int` | `%u`      | `%u`          |
| `float`        | `%f`      | `%f`          |
| `double`       | `%lf`     | `%f` / `%.2f` |
| `long`         | `%ld`     | `%ld`         |
| `long long`    | `%lld`    | `%lld`        |

**Important:** In `scanf()`, ordinary variables generally need `&`:

```c
scanf("%d", &age);
scanf("%f", &height);
scanf("%lf", &balance);
scanf(" %c", &grade);
```

For a character, `" %c"` has a leading space so that previous whitespace/newlines are skipped.

### 11. Read a Short Integer

Write a C program to read the **number of books** using `short int` and display it.

**Answer:**

```c
#include <stdio.h>

int main()
{
    short int books;

    printf("Enter number of books: ");
    scanf("%hd", &books);

    printf("Books = %hd", books);

    return 0;
}
```

**Input:**

```text
Enter number of books: 120
```

**Output:**

```text
Books = 120
```

---

### 12. Read an Unsigned Short Integer

Write a C program to read the **number of seats available** using `unsigned short int`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    unsigned short int seats;

    printf("Enter available seats: ");
    scanf("%hu", &seats);

    printf("Available seats = %hu", seats);

    return 0;
}
```

**Input:**

```text
Enter available seats: 500
```

**Output:**

```text
Available seats = 500
```

---

### 13. Read an Unsigned Long Integer

Write a C program to read the **population of a country** using `unsigned long`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    unsigned long population;

    printf("Enter population: ");
    scanf("%lu", &population);

    printf("Population = %lu", population);

    return 0;
}
```

**Input:**

```text
Enter population: 1450000000
```

**Output:**

```text
Population = 1450000000
```

---

### 14. Read an Unsigned Long Long Integer

Write a C program to read a large **ID number** using `unsigned long long`.

**Answer:**

```c
#include <stdio.h>

int main()
{
    unsigned long long id;

    printf("Enter ID: ");
    scanf("%llu", &id);

    printf("ID = %llu", id);

    return 0;
}
```

**Input:**

```text
Enter ID: 987654321012345
```

**Output:**

```text
ID = 987654321012345
```

---

### 15. Read a Long Double

Write a C program to read a highly precise value using `long double` and print it with **3 decimal places**.

**Answer:**

```c
#include <stdio.h>

int main()
{
    long double value;

    printf("Enter value: ");
    scanf("%Lf", &value);

    printf("Value = %.3Lf", value);

    return 0;
}
```

**Input:**

```text
Enter value: 12345.67891
```

**Output:**

```text
Value = 12345.679
```

---

### 16. Read Two Characters

Write a C program to read two characters and display both characters.

**Answer:**

```c
#include <stdio.h>

int main()
{
    char first, second;

    printf("Enter two characters: ");
    scanf(" %c %c", &first, &second);

    printf("First character = %c\n", first);
    printf("Second character = %c", second);

    return 0;
}
```

**Input:**

```text
Enter two characters: A B
```

**Output:**

```text
First character = A
Second character = B
```

---

### 17. Read a Character and Print Its Numeric Value

Write a C program to read a character and display the character and its numeric character code.

**Answer:**

```c
#include <stdio.h>

int main()
{
    char ch;

    printf("Enter a character: ");
    scanf(" %c", &ch);

    printf("Character = %c\n", ch);
    printf("Numeric value = %d", ch);

    return 0;
}
```

**Input:**

```text
Enter a character: A
```

**Output:**

```text
Character = A
Numeric value = 65
```

---

### 18. Read Three Different Data Types in One `scanf()`

Write a C program to read:

* Age → `int`
* Height → `float`
* Grade → `char`

Use a **single `scanf()` statement**.

**Answer:**

```c
#include <stdio.h>

int main()
{
    int age;
    float height;
    char grade;

    printf("Enter age, height and grade: ");
    scanf("%d %f %c", &age, &height, &grade);

    printf("Age = %d\n", age);
    printf("Height = %.2f\n", height);
    printf("Grade = %c", grade);

    return 0;
}
```

**Input:**

```text
Enter age, height and grade: 21 5.8 A
```

**Output:**

```text
Age = 21
Height = 5.80
Grade = A
```

---

### 19. Read Two Numbers and Display Different Results

Write a C program to read two integers and display their:

* Sum
* Difference
* Product
* Quotient
* Remainder

**Answer:**

```c
#include <stdio.h>

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    printf("Sum = %d\n", a + b);
    printf("Difference = %d\n", a - b);
    printf("Product = %d\n", a * b);
    printf("Quotient = %d\n", a / b);
    printf("Remainder = %d", a % b);

    return 0;
}
```

**Input:**

```text
Enter two numbers: 20 6
```

**Output:**

```text
Sum = 26
Difference = 14
Product = 120
Quotient = 3
Remainder = 2
```

---

### 20. Student Information Using Multiple Data Types

Write a C program to read and display:

* Roll number → `int`
* Age → `int`
* Percentage → `float`
* CGPA → `double`
* Grade → `char`

**Answer:**

```c
#include <stdio.h>

int main()
{
    int rollNo, age;
    float percentage;
    double cgpa;
    char grade;

    printf("Enter roll number: ");
    scanf("%d", &rollNo);

    printf("Enter age: ");
    scanf("%d", &age);

    printf("Enter percentage: ");
    scanf("%f", &percentage);

    printf("Enter CGPA: ");
    scanf("%lf", &cgpa);

    printf("Enter grade: ");
    scanf(" %c", &grade);

    printf("\n--- Student Details ---\n");
    printf("Roll Number = %d\n", rollNo);
    printf("Age = %d\n", age);
    printf("Percentage = %.2f\n", percentage);
    printf("CGPA = %.2lf\n", cgpa);
    printf("Grade = %c", grade);

    return 0;
}
```

**Input:**

```text
Enter roll number: 101
Enter age: 19
Enter percentage: 87.50
Enter CGPA: 8.7654
Enter grade: A
```

**Output:**

```text
--- Student Details ---
Roll Number = 101
Age = 19
Percentage = 87.50
CGPA = 8.77
Grade = A
```

### Format Specifiers Covered

| Data Type            | `scanf()` | `printf()` |
| -------------------- | --------- | ---------- |
| `char`               | `%c`      | `%c`       |
| `short`              | `%hd`     | `%hd`      |
| `unsigned short`     | `%hu`     | `%hu`      |
| `int`                | `%d`      | `%d`       |
| `unsigned int`       | `%u`      | `%u`       |
| `long`               | `%ld`     | `%ld`      |
| `unsigned long`      | `%lu`     | `%lu`      |
| `long long`          | `%lld`    | `%lld`     |
| `unsigned long long` | `%llu`    | `%llu`     |
| `float`              | `%f`      | `%f`       |
| `double`             | `%lf`     | `%f`       |
| `long double`        | `%Lf`     | `%Lf`      |


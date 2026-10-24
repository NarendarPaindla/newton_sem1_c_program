# C Programming: 30 Programs on `while` and `do-while` Loops

## Part 1: Programs 1–10

These first 10 programs cover basic repetition, counting, number calculations, and the difference between `while` and `do-while` loops.

## Program 1: Print Numbers from 1 to N Using `while`

Question: Write a C program to read a number `N` and print all numbers from 1 to `N` using a `while` loop.

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1;

    printf("Enter N: ");
    scanf("%d", &n);

    while (i <= n) {
        printf("%d ", i);
        i++;
    }

    return 0;
}
```

Expected Input

```
Enter N: 5
```

Expected Output

```
1 2 3 4 5
```

Why this is important: Helps understand the loop condition, initialization, and increment.

Where it is used: Generating serial numbers, displaying numbered lists, and repeating tasks a specific number of times.

## Program 2: Print Numbers from N to 1 Using `while`

Question: Write a C program to read a number `N` and print numbers in descending order from `N` to `1`.

Code:

```
#include <stdio.h>

int main() {
    int n;

    printf("Enter N: ");
    scanf("%d", &n);

    while (n >= 1) {
        printf("%d ", n);
        n--;
    }

    return 0;
}
```

Expected Input

```
Enter N: 5
```

Expected Output

```
5 4 3 2 1
```

Why this is important: Demonstrates how decrementing a variable changes the loop's progress.

Where it is used: Countdown timers, reverse numbering, and launching sequences.

## Program 3: Print Even Numbers from 1 to N Using `while`

Question: Write a C program to print all even numbers from `1` to `N`.

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1;

    printf("Enter N: ");
    scanf("%d", &n);

    while (i <= n) {
        if (i % 2 == 0) {
            printf("%d ", i);
        }
        i++;
    }

    return 0;
}
```

Expected Input

```
Enter N: 10
```

Expected Output

```
2 4 6 8 10
```

Why this is important: Combines a loop with an `if` condition and the modulus operator.

Where it is used: Filtering numbers, processing even-indexed elements, and applying conditional rules to data.

## Program 4: Print Odd Numbers from 1 to N Using `while`

Question: Write a C program to print all odd numbers from `1` to `N`.

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1;

    printf("Enter N: ");
    scanf("%d", &n);

    while (i <= n) {
        if (i % 2 != 0) {
            printf("%d ", i);
        }
        i++;
    }

    return 0;
}
```

Expected Input

```
Enter N: 10
```

Expected Output

```
1 3 5 7 9
```

Why this is important: Reinforces conditional filtering using `%` and `!=`.

Where it is used: Separating records by index, alternating patterns, and number classification.

## Program 5: Calculate the Sum of Numbers from 1 to N Using `while`

Question: Write a C program to calculate the sum of all integers from `1` to `N`.

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1, sum = 0;

    printf("Enter N: ");
    scanf("%d", &n);

    while (i <= n) {
        sum = sum + i;
        i++;
    }

    printf("Sum = %d", sum);

    return 0;
}
```

Expected Input

```
Enter N: 5
```

Expected Output

```
Sum = 15
```

Why this is important: Introduces an accumulator variable that stores a running total.

Where it is used: Calculating totals, billing amounts, and aggregating numerical data.

## Program 6: Calculate the Factorial of a Number Using `while`

Question: Write a C program to calculate the factorial of a non-negative integer using a `while` loop.

Factorial example: \\(5! = 5 \times 4 \times 3 \times 2 \times 1 = 120\\)

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1;
    unsigned long long fact = 1;

    printf("Enter a number (0 to 20): ");
    scanf("%d", &n);

    if (n < 0 || n > 20) {
        printf("Invalid input");
        return 0;
    }

    while (i <= n) {
        fact = fact * i;
        i++;
    }

    printf("Factorial = %llu", fact);

    return 0;
}
```

Expected Input

```
Enter a number (0 to 20): 5
```

Expected Output

```
Factorial = 120
```

Why this is important: Teaches repeated multiplication and shows why factorial needs an initial value of `1`. It also handles the special case `0! = 1`.

Where it is used: Combinatorics, probability calculations, and mathematical algorithms.

## Program 7: Count the Number of Digits Using `while`

Question: Write a C program to count the digits in an integer using a `while` loop.

Code:

```
#include <stdio.h>

int main() {
    int n, count = 0;

    printf("Enter an integer: ");
    scanf("%d", &n);

    if (n == 0) {
        count = 1;
    } else {
        while (n != 0) {
            n = n / 10;
            count++;
        }
    }

    printf("Number of digits = %d", count);

    return 0;
}
```

Expected Input

```
Enter an integer: 5832
```

Expected Output

```
Number of digits = 4
```

Why this is important: Demonstrates integer division and how repeatedly dividing by `10` removes the last digit. It also handles zero correctly.

Where it is used: Validating numeric input, processing identifiers, and solving digit-based problems.

## Program 8: Reverse a Number Using `while`

Question: Write a C program to reverse the digits of a positive integer.

Code:

```
#include <stdio.h>

int main() {
    int n, digit, reverse = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    while (n != 0) {
        digit = n % 10;
        reverse = reverse * 10 + digit;
        n = n / 10;
    }

    printf("Reversed number = %d", reverse);

    return 0;
}
```

Expected Input

```
Enter a positive integer: 1234
```

Expected Output

```
Reversed number = 4321
```

Why this is important: Combines `% 10`, `/ 10`, and a running result to process digits one by one.

Where it is used: Number manipulation, palindrome checks, and digit-processing algorithms.

## Program 9: Calculate the Sum of Digits Using `while`

Question: Write a C program to calculate the sum of the digits of a positive integer.

Code:

```
#include <stdio.h>

int main() {
    int n, digit, sum = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    while (n != 0) {
        digit = n % 10;
        sum = sum + digit;
        n = n / 10;
    }

    printf("Sum of digits = %d", sum);

    return 0;
}
```

Expected Input

```
Enter a positive integer: 582
```

Expected Output

```
Sum of digits = 15
```

Why this is important: Helps students understand digit extraction and accumulation within a loop.

Where it is used: Digit-based puzzles, numeric validation, and mathematical exercises.

## Program 10: Read Numbers Until the User Enters 0 Using `do-while`

Question: Write a C program that repeatedly accepts integers and calculates their sum. Stop when the user enters `0`. Use a `do-while` loop.

Code:

```
#include <stdio.h>

int main() {
    int num, sum = 0;

    do {
        printf("Enter a number (0 to stop): ");
        scanf("%d", &num);

        sum = sum + num;

    } while (num != 0);

    printf("Total sum = %d", sum);

    return 0;
}
```

Expected Input

```
Enter a number (0 to stop): 10
Enter a number (0 to stop): 20
Enter a number (0 to stop): 5
Enter a number (0 to stop): 0
```

Expected Output

```
Total sum = 35
```

Why this is important: Introduces the key feature of `do-while`: the loop body executes at least once before its condition is checked.

Where it is used: Menu-driven programs, repeated user input, and sentinel-controlled calculations.

## Quick Revision: `while` vs `do-while`

| Feature                   | `while`                          | `do-while`                                  |
| ------------------------- | -------------------------------- | ------------------------------------------- |
| Condition checked         | Before the loop body             | After the loop body                         |
| Minimum executions        | Zero                             | One                                         |
| Semicolon after condition | No                               | Yes                                         |
| Best suited for           | Repeat while a condition is true | Execute once, then decide whether to repeat |

Practice challenge: Modify Program 10 so that it also counts how many non-zero numbers the user entered.
# C Programming: `while` and `do-while` Loops

## Part 2: Programs 11–20

These programs introduce multiplication tables, number properties, GCD, and repeated input processing.

## Program 11: Print the Multiplication Table Using `while`

Question: Write a C program to read a number and print its multiplication table from 1 to 10 using a `while` loop.

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1;

    printf("Enter a number: ");
    scanf("%d", &n);

    while (i <= 10) {
        printf("%d x %d = %d\n", n, i, n * i);
        i++;
    }

    return 0;
}
```

Expected Input

```
Enter a number: 5
```

Expected Output

```
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

Why this is important: Demonstrates repeated calculations and formatted output inside a loop.

Where it is used: Educational math applications, report generation, and repetitive calculations.

## Program 12: Count Even and Odd Digits Using `while`

Question: Write a C program to count the number of even and odd digits in a positive integer.

Code:

```
#include <stdio.h>

int main() {
    int n, digit;
    int even = 0, odd = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    if (n == 0) {
        even = 1;
    }

    while (n > 0) {
        digit = n % 10;

        if (digit % 2 == 0) {
            even++;
        } else {
            odd++;
        }

        n = n / 10;
    }

    printf("Even digits = %d\n", even);
    printf("Odd digits = %d\n", odd);

    return 0;
}
```

Expected Input

```
Enter a positive integer: 123456
```

Expected Output

```
Even digits = 3
Odd digits = 3
```

Why this is important: Combines digit extraction, modulus, and conditional counting.

Where it is used: Numeric data analysis, number puzzles, and digit classification.

## Program 13: Check Whether a Number Is a Palindrome Using `while`

Question: Write a C program to check whether a non-negative integer reads the same forward and backward.

Code:

```
#include <stdio.h>

int main() {
    int n, original, digit;
    long long reverse = 0;

    printf("Enter a non-negative integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    original = n;

    while (n > 0) {
        digit = n % 10;
        reverse = reverse * 10 + digit;
        n = n / 10;
    }

    if (original == reverse) {
        printf("Palindrome number");
    } else {
        printf("Not a palindrome number");
    }

    return 0;
}
```

Expected Input

```
Enter a non-negative integer: 1221
```

Expected Output

```
Palindrome number
```

Why this is important: Teaches how to preserve an original value and compare it with a calculated result.

Where it is used: Number puzzles, algorithmic problem-solving, and introductory coding challenges.

## Program 14: Check Whether a Number Is an Armstrong Number Using `while`

Question: Write a C program to check whether a non-negative integer is an Armstrong number. For this program, an Armstrong number equals the sum of each digit raised to the number of digits.

Example: \\(153 = 1^3 + 5^3 + 3^3 = 153\\).

Code:

```
#include <stdio.h>

int main() {
    int n, original, temp, digit;
    int digits = 0;
    long long sum = 0, power;

    printf("Enter a non-negative integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    original = n;
    temp = n;

    do {
        digits++;
        temp = temp / 10;
    } while (temp > 0);

    temp = n;

    while (temp > 0) {
        digit = temp % 10;
        power = 1;

        for (int i = 1; i <= digits; i++) {
            power = power * digit;
        }

        sum = sum + power;
        temp = temp / 10;
    }

    if (sum == original) {
        printf("Armstrong number");
    } else {
        printf("Not an Armstrong number");
    }

    return 0;
}
```

Expected Input

```
Enter a non-negative integer: 153
```

Expected Output

```
Armstrong number
```

Why this is important: Demonstrates nested repetition, digit extraction, and the use of `do-while` to count digits, including when the input is zero.

Where it is used: Mathematical programming exercises and logic-building problems.

## Program 15: Find the Greatest Common Divisor (GCD) Using `while`

Question: Write a C program to find the GCD of two non-negative integers using the Euclidean algorithm. At least one number must be non-zero.

Code:

```
#include <stdio.h>

int main() {
    int a, b, remainder;

    printf("Enter two non-negative integers: ");
    scanf("%d %d", &a, &b);

    if (a < 0 || b < 0 || (a == 0 && b == 0)) {
        printf("Invalid input");
        return 0;
    }

    while (b != 0) {
        remainder = a % b;
        a = b;
        b = remainder;
    }

    printf("GCD = %d", a);

    return 0;
}
```

Expected Input

```
Enter two non-negative integers: 24 18
```

Expected Output

```
GCD = 6
```

Why this is important: Shows how a loop can repeatedly update variables until a mathematical condition becomes false.

Where it is used: Fraction simplification, number theory, and mathematical software.

## Program 16: Calculate the Power of a Number Using `while`

Question: Write a C program to calculate \\(a^b\\), where `a` is an integer and `b` is a non-negative integer, using repeated multiplication.

Code:

```
#include <stdio.h>

int main() {
    int a, b, i = 0;
    long long result = 1;

    printf("Enter base and exponent: ");
    scanf("%d %d", &a, &b);

    if (b < 0) {
        printf("Exponent must be non-negative");
        return 0;
    }

    while (i < b) {
        result = result * a;
        i++;
    }

    printf("Result = %lld", result);

    return 0;
}
```

Expected Input

```
Enter base and exponent: 2 5
```

Expected Output

```
Result = 32
```

Why this is important: Explains repeated multiplication and why initializing the result to `1` also handles exponent zero.

Where it is used: Mathematical calculations, scientific programs, and introductory numerical algorithms.

## Program 17: Keep Accepting Numbers Until a Negative Number Is Entered

Question: Write a C program using `do-while` to accept numbers until the user enters a negative number. Display the sum of all non-negative numbers entered.

Code:

```
#include <stdio.h>

int main() {
    int num;
    long long sum = 0;

    do {
        printf("Enter a number (negative to stop): ");
        scanf("%d", &num);

        if (num >= 0) {
            sum = sum + num;
        }

    } while (num >= 0);

    printf("Sum of non-negative numbers = %lld", sum);

    return 0;
}
```

Expected Input

```
Enter a number (negative to stop): 10
Enter a number (negative to stop): 20
Enter a number (negative to stop): 5
Enter a number (negative to stop): -1
```

Expected Output

```
Sum of non-negative numbers = 35
```

Why this is important: Demonstrates sentinel-controlled repetition and shows how to stop input based on a special value.

Where it is used: Interactive data entry, collecting measurements, and processing unknown quantities of input.

## Program 18: Display a Menu Until the User Chooses Exit

Question: Write a menu-driven C program using `do-while` that lets the user choose to display a greeting or exit.

Code:

```
#include <stdio.h>

int main() {
    int choice;

    do {
        printf("\n1. Display Greeting\n");
        printf("2. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Hello! Welcome to C programming.\n");
                break;

            case 2:
                printf("Exiting program.\n");
                break;

            default:
                printf("Invalid choice. Try again.\n");
        }

    } while (choice != 2);

    return 0;
}
```

Expected Input

```
Enter your choice: 1
Enter your choice: 7
Enter your choice: 2
```

Expected Output (menu text omitted for clarity)

```
Hello! Welcome to C programming.
Invalid choice. Try again.
Exiting program.
```

Why this is important: Combines `do-while`, `switch`, and repeated user interaction.

Where it is used: Banking menus, student management systems, calculator applications, and console-based software.

## Program 19: Find the First Digit of a Number Using `while`

Question: Write a C program to find the first digit of a non-negative integer using a `while` loop.

Code:

```
#include <stdio.h>

int main() {
    int n;

    printf("Enter a non-negative integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    while (n >= 10) {
        n = n / 10;
    }

    printf("First digit = %d", n);

    return 0;
}
```

Expected Input

```
Enter a non-negative integer: 5832
```

Expected Output

```
First digit = 5
```

Why this is important: Shows how repeated integer division reduces a number until only its leading digit remains.

Where it is used: Digit-based validation, numeric classification, and programming puzzles.

## Program 20: Calculate the Average Until the User Enters 0 Using `do-while`

Question: Write a C program that accepts numbers until the user enters `0`, then displays the average of the non-zero numbers. If no non-zero numbers are entered, display an appropriate message.

Code:

```
#include <stdio.h>

int main() {
    int num, count = 0;
    double sum = 0;

    do {
        printf("Enter a number (0 to stop): ");
        scanf("%d", &num);

        if (num != 0) {
            sum = sum + num;
            count++;
        }

    } while (num != 0);

    if (count > 0) {
        printf("Average = %.2f", sum / count);
    } else {
        printf("No numbers were entered.");
    }

    return 0;
}
```

Expected Input

```
Enter a number (0 to stop): 10
Enter a number (0 to stop): 20
Enter a number (0 to stop): 30
Enter a number (0 to stop): 0
```

Expected Output

```
Average = 20.00
```

Why this is important: Combines accumulation, counting, sentinel input, and division while handling the zero-count case.

Where it is used: Calculating average marks, sensor readings, survey results, and user-entered measurements.

## Summary: Programs 11–20

| Program | Concept                             |
| ------- | ----------------------------------- |
| 11      | Multiplication table                |
| 12      | Count even and odd digits           |
| 13      | Palindrome number                   |
| 14      | Armstrong number                    |
| 15      | GCD using Euclidean algorithm       |
| 16      | Power using repeated multiplication |
| 17      | Sentinel-controlled input           |   
| 18      | Menu-driven program                 |
| 19      | First digit of a number             |
| 20      | Average of entered numbers          |

The final 10 programs (21–30) can focus on stronger loop logic, including Fibonacci series, prime-number checking, repeated validation, and nested-loop patterns.

# C Programming: `while` and `do-while` Loops

## Part 3: Programs 21–30

These final 10 programs focus on Fibonacci series, prime numbers, input validation, number properties, and nested loops. Each program includes the question, C code, expected input/output, why it is important, and where it is used.

## Program 21: Print the Fibonacci Series Using `while`

Question: Write a C program to print the first `N` terms of the Fibonacci series using a `while` loop.

In the Fibonacci series, each term after the first two is the sum of the previous two terms.

Code:

```
#include <stdio.h>

int main() {
    int n, count = 0;
    long long first = 0, second = 1, next;

    printf("Enter number of terms (1 to 92): ");
    scanf("%d", &n);

    if (n < 1 || n > 92) {
        printf("Invalid input");
        return 0;
    }

    while (count < n) {
        printf("%lld ", first);

        next = first + second;
        first = second;
        second = next;

        count++;
    }

    return 0;
}
```

Expected Input

```
Enter number of terms (1 to 92): 7
```

Expected Output

```
0 1 1 2 3 5 8
```

Why this is important: Teaches how to update multiple variables during each iteration and generate a sequence.

Where it is used: Mathematical modeling, algorithm practice, and understanding recurrence relations.

## Program 22: Check Whether a Number Is Prime Using `while`

Question: Write a C program to check whether a positive integer is a prime number using a `while` loop.

A prime number has exactly two positive factors: 1 and itself.

Code:

```
#include <stdio.h>

int main() {
    int n, i = 2, isPrime = 1;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    if (n < 2) {
        isPrime = 0;
    } else {
        while (i <= n / i) {
            if (n % i == 0) {
                isPrime = 0;
                break;
            }
            i++;
        }
    }

    if (isPrime) {
        printf("Prime number");
    } else {
        printf("Not a prime number");
    }

    return 0;
}
```

Expected Input

```
Enter a positive integer: 17
```

Expected Output

```
Prime number
```

Why this is important: Demonstrates loop-based searching, conditional checking, and the `break` statement. Checking divisors only up to the square root makes the algorithm more efficient.

Where it is used: Number theory, competitive programming, and introductory cryptography concepts.

## Program 23: Print All Factors of a Number Using `while`

Question: Write a C program to display all positive factors of a positive integer.

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Invalid input");
        return 0;
    }

    printf("Factors: ");

    while (i <= n) {
        if (n % i == 0) {
            printf("%d ", i);
        }
        i++;
    }

    return 0;
}
```

Expected Input

```
Enter a positive integer: 12
```

Expected Output

```
Factors: 1 2 3 4 6 12
```

Why this is important: Helps students understand divisibility and how loops can examine a range of possible values.

Where it is used: Finding factors, studying number properties, and solving GCD-related problems.

## Program 24: Calculate the Product of Digits Using `while`

Question: Write a C program to calculate the product of all digits in a non-negative integer.

Code:

```
#include <stdio.h>

int main() {
    int n, digit;
    long long product = 1;

    printf("Enter a non-negative integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    if (n == 0) {
        product = 0;
    }

    while (n > 0) {
        digit = n % 10;
        product = product * digit;
        n = n / 10;
    }

    printf("Product of digits = %lld", product);

    return 0;
}
```

Expected Input

```
Enter a non-negative integer: 234
```

Expected Output

```
Product of digits = 24
```

Why this is important: Reinforces digit extraction and accumulation through multiplication rather than addition.

Where it is used: Digit-based mathematical puzzles and numeric processing algorithms.

## Program 25: Check Whether a Number Is a Perfect Number Using `while`

Question: Write a C program to check whether a positive integer is a perfect number.

A perfect number equals the sum of its positive factors excluding itself. For example, \\(6 = 1 + 2 + 3\\).

Code:

```
#include <stdio.h>

int main() {
    int n, i = 1, sum = 0;

    printf("Enter a positive integer: ");
    scanf("%d", &n);

    if (n <= 0) {
        printf("Invalid input");
        return 0;
    }

    while (i <= n / 2) {
        if (n % i == 0) {
            sum = sum + i;
        }
        i++;
    }

    if (sum == n) {
        printf("Perfect number");
    } else {
        printf("Not a perfect number");
    }

    return 0;
}
```

Expected Input

```
Enter a positive integer: 28
```

Expected Output

```
Perfect number
```

Why this is important: Combines factor checking, accumulation, and comparison to solve a number-classification problem.

Where it is used: Mathematical programming challenges and algorithm development practice.

## Program 26: Find the Largest Digit Using `while`

Question: Write a C program to find the largest digit in a non-negative integer.

Code:

```
#include <stdio.h>

int main() {
    int n, digit, largest = 0;

    printf("Enter a non-negative integer: ");
    scanf("%d", &n);

    if (n < 0) {
        printf("Invalid input");
        return 0;
    }

    while (n > 0) {
        digit = n % 10;

        if (digit > largest) {
            largest = digit;
        }

        n = n / 10;
    }

    printf("Largest digit = %d", largest);

    return 0;
}
```

Expected Input

```
Enter a non-negative integer: 5832
```

Expected Output

```
Largest digit = 8
```

Why this is important: Shows how to maintain a running maximum while processing data one digit at a time.

Where it is used: Numeric validation, digit analysis, and maximum-value searching.

## Program 27: Keep Asking Until the User Enters a Positive Number Using `do-while`

Question: Write a C program that repeatedly asks the user for a number until a positive number is entered.

Code:

```
#include <stdio.h>

int main() {
    int n;

    do {
        printf("Enter a positive number: ");
        scanf("%d", &n);

        if (n <= 0) {
            printf("Invalid input. Try again.\n");
        }

    } while (n <= 0);

    printf("Accepted number = %d", n);

    return 0;
}
```

Expected Input

```
Enter a positive number: -5
Enter a positive number: 0
Enter a positive number: 12
```

Expected Output

```
Invalid input. Try again.
Invalid input. Try again.
Accepted number = 12
```

Why this is important: Demonstrates input validation and the use of `do-while` when the user must enter data at least once.

Where it is used: Registration forms, age validation, quantity entry, and menu-driven applications.

## Program 28: Print a Right-Angled Triangle Using Nested `while` Loops

Question: Write a C program to print a right-angled triangle of stars using nested `while` loops.

Code:

```
#include <stdio.h>

int main() {
    int rows, i = 1;

    printf("Enter number of rows: ");
    scanf("%d", &rows);

    if (rows <= 0) {
        printf("Invalid input");
        return 0;
    }

    while (i <= rows) {
        int j = 1;

        while (j <= i) {
            printf("* ");
            j++;
        }

        printf("\n");
        i++;
    }

    return 0;
}
```

Expected Input

```
Enter number of rows: 4
```

Expected Output

```
*
* *
* * *
* * * *
```

Why this is important: Introduces nested loops: the outer loop controls rows, and the inner loop controls the number of stars in each row.

Where it is used: Pattern printing, grid generation, and understanding nested iteration in algorithms.

## Program 29: Create a Simple Guessing Game Using `do-while`

Question: Write a C program that asks the user to guess a fixed secret number. Continue until the correct number is entered.

Code:

```
#include <stdio.h>

int main() {
    int guess;
    const int secret = 7;
    int attempts = 0;

    do {
        printf("Guess the number (1 to 10): ");
        scanf("%d", &guess);

        attempts++;

        if (guess < secret) {
            printf("Too low!\n");
        } else if (guess > secret) {
            printf("Too high!\n");
        }

    } while (guess != secret);

    printf("Correct! Attempts = %d", attempts);

    return 0;
}
```

Expected Input

```
Guess the number (1 to 10): 3
Guess the number (1 to 10): 9
Guess the number (1 to 10): 7
```

Expected Output

```
Too low!
Too high!
Correct! Attempts = 3
```

Why this is important: Combines repeated input, decision-making, counting, and a termination condition.

Where it is used: Quiz applications, interactive games, and repeated user-input workflows.

## Program 30: Build a Calculator Using `do-while`

Question: Write a menu-driven calculator using `do-while` and `switch`. Allow the user to add, subtract, multiply, or divide two numbers repeatedly until they choose to exit.

Code:

```
#include <stdio.h>

int main() {
    int choice;
    double a, b;

    do {
        printf("\n--- Calculator ---\n");
        printf("1. Addition\n");
        printf("2. Subtraction\n");
        printf("3. Multiplication\n");
        printf("4. Division\n");
        printf("5. Exit\n");
        printf("Enter choice: ");
        scanf("%d", &choice);

        if (choice >= 1 && choice <= 4) {
            printf("Enter two numbers: ");
            scanf("%lf %lf", &a, &b);
        }

        switch (choice) {
            case 1:
                printf("Result = %.2f\n", a + b);
                break;

            case 2:
                printf("Result = %.2f\n", a - b);
                break;

            case 3:
                printf("Result = %.2f\n", a * b);
                break;

            case 4:
                if (b != 0) {
                    printf("Result = %.2f\n", a / b);
                } else {
                    printf("Cannot divide by zero.\n");
                }
                break;

            case 5:
                printf("Calculator closed.\n");
                break;

            default:
                printf("Invalid choice.\n");
        }

    } while (choice != 5);

    return 0;
}
```

Expected Input

```
Enter choice: 1
Enter two numbers: 10 5
Enter choice: 4
Enter two numbers: 10 2
Enter choice: 5
```

Expected Output (menu text omitted for clarity)

```
Result = 15.00
Result = 5.00
Calculator closed.
```

Why this is important: Integrates `do-while`, `switch`, arithmetic operators, conditional validation, and repeated menu interaction into one program.

Where it is used: Calculator applications, billing systems, banking menus, and other interactive console programs.

## Summary: All 30 `while` and `do-while` Programs

| Programs | Topics covered                                                       |
| -------- | -------------------------------------------------------------------- |
| 1–5      | Counting, even/odd numbers, sums                                     |
| 6–10     | Factorial, digit counting, reversing, digit sum, sentinel input      |
| 11–15    | Tables, digit classification, palindrome, Armstrong, GCD             |
| 16–20    | Powers, repeated input, menus, first digit, averages                 |
| 21–25    | Fibonacci, prime checking, factors, digit product, perfect numbers   |
| 26–30    | Largest digit, input validation, patterns, guessing game, calculator |

Important concepts to revise:

- Initialization, condition checking, and updating loop variables.
- Avoiding infinite loops.
- Using `break` when a search can stop early.
- Using `while` for condition-controlled repetition.
- Using `do-while` for tasks that must execute at least once.
- Combining loops with `if-else`, `switch`, and nested loops.

You have now completed all 30 programs on `while` and `do-while` loops.

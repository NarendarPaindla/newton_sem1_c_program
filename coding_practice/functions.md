# C Programming – Functions: 30 Hands-on Programs

## 1. Display a Welcome Message Using a Function

Question: Write a C program to display a welcome message using a user-defined function.

Concept: Function with no arguments and no return value.

```
#include <stdio.h>

void welcome()
{
    printf("Welcome to C Programming!");
}

int main()
{
    welcome();

    return 0;
}
```

Expected Output:

```
Welcome to C Programming!
```

Why is this important? Students understand how to create and call their first user-defined function.

Where is it used? Displaying welcome messages, instructions and notifications in applications.

## 2. Add Two Numbers Using a Function

Question: Write a C program to read two numbers and calculate their sum using a function.

Concept: Function with arguments and no return value.

```
#include <stdio.h>

void add(int a, int b)
{
    printf("Sum = %d", a + b);
}

int main()
{
    int x, y;

    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);

    add(x, y);

    return 0;
}
```

Expected Output:

```
Enter two numbers: 10 20
Sum = 30
```

Why is this important? Students understand how to pass values from `main()` to another function.

Where is it used? Calculator applications, billing systems and financial calculations.

## 3. Find the Square of a Number Using a Function

Question: Write a C program to read a number and calculate its square using a function.

Concept: Function with arguments and return value.

```
#include <stdio.h>

int square(int n)
{
    return n * n;
}

int main()
{
    int num, result;

    printf("Enter a number: ");
    scanf("%d", &num);

    result = square(num);

    printf("Square = %d", result);

    return 0;
}
```

Expected Output:

```
Enter a number: 5
Square = 25
```

Why is this important? Students learn how a function returns a calculated value to the calling function.

Where is it used? Mathematical applications, geometry calculations and scientific programs.

## 4. Find the Largest of Two Numbers Using a Function

Question: Write a C program to find the largest of two numbers using a user-defined function.

Concept: Function with arguments and return value, conditional statements.

```
#include <stdio.h>

int largest(int a, int b)
{
    if (a > b)
        return a;
    else
        return b;
}

int main()
{
    int x, y, result;

    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);

    result = largest(x, y);

    printf("Largest number = %d", result);

    return 0;
}
```

Expected Output:

```
Enter two numbers: 25 40
Largest number = 40
```

Why is this important? It teaches how to combine decision-making statements with functions.

Where is it used? Comparing student marks, product prices and employee salaries.

## 5. Check Whether a Number Is Even or Odd Using a Function

Question: Write a C program to check whether a given number is even or odd using a function.

Concept: Function with arguments and no return value.

```
#include <stdio.h>

void checkEvenOdd(int n)
{
    if (n % 2 == 0)
        printf("Even number");
    else
        printf("Odd number");
}

int main()
{
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    checkEvenOdd(num);

    return 0;
}
```

Expected Output:

```
Enter a number: 7
Odd number
```

Why is this important? Students understand how functions can perform operations and directly display results without returning values.

Where is it used? Number validation, record classification and mathematical applications.

## 6. Calculate the Factorial of a Number Using a Function

Question: Write a C program to calculate the factorial of a given number using a function.

Concept: Function with arguments and return value, loops.

Factorial example:

\\[ 5! = 5 \times 4 \times 3 \times 2 \times 1 = 120 \\]

```
#include <stdio.h>

int factorial(int n)
{
    int i, fact = 1;

    for (i = 1; i <= n; i++)
    {
        fact = fact * i;
    }

    return fact;
}

int main()
{
    int num, result;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (num < 0 || num > 12)
    {
        printf("Enter a number between 0 and 12");
    }
    else
    {
        result = factorial(num);

        printf("Factorial = %d", result);
    }

    return 0;
}
```

Expected Output:

```
Enter a number: 5
Factorial = 120
```

Why is this important? Students learn how to move an existing loop-based calculation into a reusable function.

Where is it used? Combinatorics, probability calculations and mathematical applications.

## 7. Find the Area of a Circle Using a Function

Question: Write a C program to calculate the area of a circle using a user-defined function.

Formula:

\\[ Area = \pi \times r \times r \\]

Concept: Function with arguments and return value using `float`.

```
#include <stdio.h>

float calculateArea(float radius)
{
    return 3.14f * radius * radius;
}

int main()
{
    float r, area;

    printf("Enter radius: ");
    scanf("%f", &r);

    area = calculateArea(r);

    printf("Area of circle = %.2f", area);

    return 0;
}
```

Expected Output:

```
Enter radius: 5
Area of circle = 78.50
```

Why is this important? Students understand how functions can accept decimal values and return decimal results.

Where is it used? Engineering calculations, construction applications and geometry software.

## 8. Find the Sum of Digits Using a Function

Question: Write a C program to find the sum of all digits of a given number using a function.

Concept: Function with arguments and return value, `while` loop and modulus operator.

Example:

\\[ 1234 = 1 + 2 + 3 + 4 = 10 \\]

```
#include <stdio.h>

int sumOfDigits(int n)
{
    int sum = 0;

    while (n > 0)
    {
        sum = sum + (n % 10);
        n = n / 10;
    }

    return sum;
}

int main()
{
    int num, result;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (num < 0)
        num = -num;

    result = sumOfDigits(num);

    printf("Sum of digits = %d", result);

    return 0;
}
```

Expected Output:

```
Enter a number: 1234
Sum of digits = 10
```

Why is this important? Students learn to combine loops, arithmetic operators and functions.

Where is it used? Number validation, digital root calculations and mathematical puzzles.

## 9. Find the Largest Element in an Array Using a Function

Question: Write a C program to read array elements and find the largest element using a function.

Concept: Passing an array to a function.

```
#include <stdio.h>

int findLargest(int arr[], int n)
{
    int i, max = arr[0];

    for (i = 1; i < n; i++)
    {
        if (arr[i] > max)
        {
            max = arr[i];
        }
    }

    return max;
}

int main()
{
    int arr[100], n, i, result;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n < 1 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }

    printf("Enter array elements:\n");

    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    result = findLargest(arr, n);

    printf("Largest element = %d", result);

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5
Enter array elements:
10 50 20 80 30
Largest element = 80
```

Why is this important? Students learn that arrays can be passed to functions, connecting two important C programming topics.

Where is it used? Finding highest marks, maximum sales and maximum sensor readings.

## 10. Swap Two Numbers Using a Function

Question: Write a C program to swap two numbers using a function so that the original variables are modified.

Concept: Passing addresses using pointers.

```
#include <stdio.h>

void swap(int *a, int *b)
{
    int temp;

    temp = *a;
    *a = *b;
    *b = temp;
}

int main()
{
    int x, y;

    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);

    printf("Before swapping: x = %d, y = %d\n", x, y);

    swap(&x, &y);

    printf("After swapping: x = %d, y = %d", x, y);

    return 0;
}
```

Expected Output:

```
Enter two numbers: 10 20
Before swapping: x = 10, y = 20
After swapping: x = 20, y = 10
```

Why is this important? Students understand how passing addresses allows a function to modify original variables.

Where is it used? Sorting algorithms, data manipulation and exchanging values in applications.

# Revision – Programs 1–10

| No. | Program               | Function category / concept |
| --- | --------------------- | --------------------------- |
| 1   | Welcome message       | No arguments, no return     |
| 2   | Addition              | Arguments, no return        |
| 3   | Square                | Arguments, return           |
| 4   | Largest of two        | Arguments, return           |
| 5   | Even or odd           | Arguments, no return        |
| 6   | Factorial             | Arguments, return           |
| 7   | Area of circle        | Arguments, return           |
| 8   | Sum of digits         | Arguments, return           |
| 9   | Largest array element | Array passed to function    |
| 10  | Swap two numbers      | Pointers with functions     |


# C Programming – Functions: 30 Hands-on Programs



Part 2 of 3

Programs 11–20



In this batch, students will learn to implement mathematical operations, number checking, arrays and strings using user-defined functions.

## 11. Check Whether a Number Is Prime Using a Function

Question: Write a C program to check whether a given number is prime or not using a function.

Concept: Function with arguments and return value, loops and conditional statements.

```
#include <stdio.h>

int isPrime(int n)
{
    int i;

    if (n <= 1)
        return 0;

    for (i = 2; i <= n / i; i++)
    {
        if (n % i == 0)
            return 0;
    }

    return 1;
}

int main()
{
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (isPrime(num))
        printf("Prime number");
    else
        printf("Not a prime number");

    return 0;
}
```

Expected Output:

```
Enter a number: 17
Prime number
```

Why is this important? Students learn how a function can return a Boolean-like result using integer values (`1` and `0`).

Where is it used? Number theory, mathematical applications and basic cryptography concepts.

## 12. Generate Fibonacci Series Using a Function

Question: Write a C program to generate the Fibonacci series for `n` terms using a function.

Concept: Function with arguments and no return value, loops.

Example: `0 1 1 2 3 5 8 13`

```
#include <stdio.h>

void fibonacci(int n)
{
    int a = 0, b = 1, c, i;

    for (i = 1; i <= n; i++)
    {
        printf("%d ", a);

        c = a + b;
        a = b;
        b = c;
    }
}

int main()
{
    int n;

    printf("Enter number of terms: ");
    scanf("%d", &n);

    fibonacci(n);

    return 0;
}
```

Expected Output:

```
Enter number of terms: 8
0 1 1 2 3 5 8 13
```

Why is this important? It teaches how a function can perform repeated operations and display multiple results.

Where is it used? Mathematical modelling, algorithm practice and recursive sequence problems.

## 13. Check Whether a Number Is a Palindrome Using a Function

Question: Write a C program to check whether a given number is a palindrome using a function.

A palindrome number reads the same forward and backward.

Example: `121`, `1331`, `454`.

Concept: Function with arguments and return value.

```
#include <stdio.h>

int isPalindrome(int n)
{
    int original = n;
    int reverse = 0, remainder;

    if (n < 0)
        return 0;

    while (n > 0)
    {
        remainder = n % 10;
        reverse = reverse * 10 + remainder;
        n = n / 10;
    }

    return original == reverse;
}

int main()
{
    int num;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (isPalindrome(num))
        printf("Palindrome number");
    else
        printf("Not a palindrome number");

    return 0;
}
```

Expected Output:

```
Enter a number: 121
Palindrome number
```

Why is this important? Students understand how to return the result of a comparison from a function.

Where is it used? Number validation and mathematical programming challenges.

## 14. Find the GCD of Two Numbers Using a Function

Question: Write a C program to find the Greatest Common Divisor (GCD) of two numbers using a function.

Concept: Function with arguments and return value, Euclidean algorithm.

```
#include <stdio.h>

int gcd(int a, int b)
{
    int temp;

    while (b != 0)
    {
        temp = b;
        b = a % b;
        a = temp;
    }

    return a;
}

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    if (a < 0)
        a = -a;

    if (b < 0)
        b = -b;

    if (a == 0 && b == 0)
    {
        printf("GCD is undefined");
    }
    else
    {
        printf("GCD = %d", gcd(a, b));
    }

    return 0;
}
```

Expected Output:

```
Enter two numbers: 12 18
GCD = 6
```

Why is this important? Students learn to implement an efficient mathematical algorithm inside a reusable function.

Where is it used? Fractions, number theory and mathematical applications.

## 15. Find the LCM of Two Numbers Using a Function

Question: Write a C program to calculate the Least Common Multiple (LCM) of two numbers using a function.

Formula:

\\[ LCM(a,b)=\frac{|a \times b|}{GCD(a,b)} \\]

```
#include <stdio.h>

int gcd(int a, int b)
{
    int temp;

    while (b != 0)
    {
        temp = b;
        b = a % b;
        a = temp;
    }

    return a;
}

int lcm(int a, int b)
{
    if (a == 0 || b == 0)
        return 0;

    return (a / gcd(a, b)) * b;
}

int main()
{
    int a, b;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    if (a < 0)
        a = -a;

    if (b < 0)
        b = -b;

    printf("LCM = %d", lcm(a, b));

    return 0;
}
```

Expected Output:

```
Enter two numbers: 12 18
LCM = 36
```

Why is this important? Students understand how one user-defined function can be reused inside another function.

Where is it used? Scheduling, fractions and problems involving repeating intervals.

## 16. Find the Sum of Array Elements Using a Function

Question: Write a C program to read array elements and calculate their sum using a function.

Concept: Passing an array to a function.

```
#include <stdio.h>

int arraySum(int arr[], int n)
{
    int i, sum = 0;

    for (i = 0; i < n; i++)
    {
        sum = sum + arr[i];
    }

    return sum;
}

int main()
{
    int arr[100], n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n < 1 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }

    printf("Enter array elements:\n");

    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Sum = %d", arraySum(arr, n));

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5
Enter array elements:
10 20 30 40 50
Sum = 150
```

Why is this important? Students learn how arrays are passed to functions and processed using loops.

Where is it used? Calculating total marks, sales totals and financial summaries.

## 17. Find the Average of Array Elements Using a Function

Question: Write a C program to calculate the average of array elements using a function.

Concept: Array passing and returning a floating-point value.

```
#include <stdio.h>

float calculateAverage(int arr[], int n)
{
    int i, sum = 0;

    for (i = 0; i < n; i++)
    {
        sum = sum + arr[i];
    }

    return (float)sum / n;
}

int main()
{
    int arr[100], n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n < 1 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }

    printf("Enter array elements:\n");

    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Average = %.2f", calculateAverage(arr, n));

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5
Enter array elements:
70 80 90 60 100
Average = 80.00
```

Why is this important? Students learn why a function may need a `float` return type instead of `int`.

Where is it used? Student result systems, performance analysis and financial calculations.

## 18. Reverse an Array Using a Function

Question: Write a C program to reverse an array using a user-defined function.

Concept: Passing arrays to functions and modifying the original array.

```
#include <stdio.h>

void reverseArray(int arr[], int n)
{
    int i, temp;

    for (i = 0; i < n / 2; i++)
    {
        temp = arr[i];
        arr[i] = arr[n - 1 - i];
        arr[n - 1 - i] = temp;
    }
}

int main()
{
    int arr[100], n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n < 1 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }

    printf("Enter array elements:\n");

    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    reverseArray(arr, n);

    printf("Reversed array:\n");

    for (i = 0; i < n; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5
Enter array elements:
10 20 30 40 50
Reversed array:
50 40 30 20 10
```

Why is this important? Students understand that modifying an array parameter can modify the original array because the function receives access to its elements.

Where is it used? Data manipulation, sorting and reversing sequences.

## 19. Find the Length of a String Using a Function

Question: Write a C program to find the length of a string without using `strlen()`, by creating a user-defined function.

Concept: Passing a character array to a function.

```
#include <stdio.h>

int stringLength(char str[])
{
    int i = 0;

    while (str[i] != '\0')
    {
        i++;
    }

    return i;
}

int main()
{
    char str[100];

    printf("Enter a string: ");
    scanf("%99s", str);

    printf("Length = %d", stringLength(str));

    return 0;
}
```

Expected Output:

```
Enter a string: Programming
Length = 11
```

Why is this important? Students connect their previous strings knowledge with functions.

Where is it used? Text validation, username length checking and string processing.

## 20. Compare Two Strings Using a Function

Question: Write a C program to compare two strings without using `strcmp()`, by creating a user-defined function.

Concept: Passing strings to functions and returning comparison results.

```
#include <stdio.h>

int compareStrings(char str1[], char str2[])
{
    int i = 0;

    while (str1[i] != '\0' || str2[i] != '\0')
    {
        if (str1[i] != str2[i])
        {
            return 0;
        }

        i++;
    }

    return 1;
}

int main()
{
    char str1[100], str2[100];

    printf("Enter first string: ");
    scanf("%99s", str1);

    printf("Enter second string: ");
    scanf("%99s", str2);

    if (compareStrings(str1, str2))
        printf("Strings are equal");
    else
        printf("Strings are not equal");

    return 0;
}
```

Expected Output:

```
Enter first string: Hello
Enter second string: Hello
Strings are equal
```

Why is this important? Students learn how to create reusable functions for string operations.

Where is it used? Login validation, username matching and record searching.

# Revision – Programs 11–20

| No. | Program           | Main concept                       |
| --- | ----------------- | ---------------------------------- |
| 11  | Prime number      | Function with return value         |
| 12  | Fibonacci series  | Function with arguments            |
| 13  | Palindrome number | Function and loops                 |
| 14  | GCD               | Euclidean algorithm                |
| 15  | LCM               | Function calling another function  |
| 16  | Sum of array      | Array as argument                  |
| 17  | Average of array  | Float return type                  |
| 18  | Reverse array     | Modifying array through function   |
| 19  | String length     | String as argument                 |
| 20  | Compare strings   | String comparison through function |

# C Programming – Functions: 30 Hands-on Programs



Part 3 of 3

Programs 21–30



In this final batch, students will practise recursion, sorting, searching, matrix operations and menu-driven programming using functions.

## 21. Calculate Factorial Using Recursion

Question: Write a C program to calculate the factorial of a number using a recursive function.

Concept: Recursion – a function calling itself.

```
#include <stdio.h>

int factorial(int n)
{
    if (n == 0 || n == 1)
        return 1;

    return n * factorial(n - 1);
}

int main()
{
    int num, result;

    printf("Enter a number: ");
    scanf("%d", &num);

    if (num < 0 || num > 12)
    {
        printf("Enter a number between 0 and 12");
    }
    else
    {
        result = factorial(num);
        printf("Factorial = %d", result);
    }

    return 0;
}
```

Expected Output:

```
Enter a number: 5
Factorial = 120
```

Why is this important? Students understand the base condition and recursive function calls.

Where is it used? Mathematical calculations, combinatorics and recursive problem-solving.

## 22. Find Fibonacci Series Using Recursion

Question: Write a C program to generate Fibonacci numbers using a recursive function.

Concept: Recursive function with arguments and return value.

```
#include <stdio.h>

int fibonacci(int n)
{
    if (n == 0)
        return 0;

    if (n == 1)
        return 1;

    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main()
{
    int n, i;

    printf("Enter number of terms: ");
    scanf("%d", &n);

    if (n < 1 || n > 20)
    {
        printf("Enter terms between 1 and 20");
        return 0;
    }

    for (i = 0; i < n; i++)
    {
        printf("%d ", fibonacci(i));
    }

    return 0;
}
```

Expected Output:

```
Enter number of terms: 7
0 1 1 2 3 5 8
```

Why is this important? It teaches how recursive functions can call themselves multiple times.

Where is it used? Recursive algorithms and mathematical sequence generation.

## 23. Find the Power of a Number Using Recursion

Question: Write a C program to calculate the power of a number using recursion.

Example: \\(2^4 = 2 \times 2 \times 2 \times 2 = 16\\).

Concept: Recursive multiplication.

```
#include <stdio.h>

int power(int base, int exponent)
{
    if (exponent == 0)
        return 1;

    return base * power(base, exponent - 1);
}

int main()
{
    int base, exponent;

    printf("Enter base: ");
    scanf("%d", &base);

    printf("Enter exponent: ");
    scanf("%d", &exponent);

    if (exponent < 0)
    {
        printf("Enter a non-negative exponent");
    }
    else
    {
        printf("Result = %d", power(base, exponent));
    }

    return 0;
}
```

Expected Output:

```
Enter base: 2
Enter exponent: 4
Result = 16
```

Why is this important? Students learn to identify a recursive pattern and its stopping condition.

Where is it used? Mathematical computations and exponentiation algorithms.

## 24. Find the Smallest Element in an Array Using a Function

Question: Write a C program to find the smallest element in an array using a user-defined function.

Concept: Passing arrays to functions.

```
#include <stdio.h>

int findSmallest(int arr[], int n)
{
    int i, min = arr[0];

    for (i = 1; i < n; i++)
    {
        if (arr[i] < min)
        {
            min = arr[i];
        }
    }

    return min;
}

int main()
{
    int arr[100], n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n < 1 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }

    printf("Enter array elements:\n");

    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Smallest element = %d", findSmallest(arr, n));

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5
Enter array elements:
40 20 10 50 30
Smallest element = 10
```

Why is this important? It reinforces array traversal and reusable functions.

Where is it used? Finding minimum prices, lowest marks and minimum sensor readings.

## 25. Sort an Array Using a Function

Question: Write a C program to sort an array in ascending order using a user-defined function.

Concept: Bubble sort and array modification through functions.

```
#include <stdio.h>

void sortArray(int arr[], int n)
{
    int i, j, temp;

    for (i = 0; i < n - 1; i++)
    {
        for (j = 0; j < n - i - 1; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main()
{
    int arr[100], n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n < 1 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }

    printf("Enter array elements:\n");

    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    sortArray(arr, n);

    printf("Sorted array:\n");

    for (i = 0; i < n; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5
Enter array elements:
50 10 40 20 30
Sorted array:
10 20 30 40 50
```

Why is this important? Students learn to separate sorting logic from the main program.

Where is it used? Ranking student marks, arranging prices and organizing records.

## 26. Search an Element in an Array Using a Function

Question: Write a C program to search for an element in an array using linear search implemented through a function.

Concept: Array passing and returning an index.

```
#include <stdio.h>

int linearSearch(int arr[], int n, int key)
{
    int i;

    for (i = 0; i < n; i++)
    {
        if (arr[i] == key)
        {
            return i;
        }
    }

    return -1;
}

int main()
{
    int arr[100], n, i, key, result;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if (n < 1 || n > 100)
    {
        printf("Invalid array size");
        return 0;
    }

    printf("Enter array elements:\n");

    for (i = 0; i < n; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Enter element to search: ");
    scanf("%d", &key);

    result = linearSearch(arr, n, key);

    if (result == -1)
        printf("Element not found");
    else
        printf("Element found at index %d", result);

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5
Enter array elements:
10 20 30 40 50
Enter element to search: 30
Element found at index 2
```

Why is this important? Students understand how functions can return positions and status values.

Where is it used? Searching student roll numbers, product IDs and employee records.

## 27. Add Two Matrices Using a Function

Question: Write a C program to add two matrices using a user-defined function.

Concept: Passing two-dimensional arrays to functions.

```
#include <stdio.h>

void addMatrices(int a[10][10], int b[10][10],
                 int result[10][10], int rows, int cols)
{
    int i, j;

    for (i = 0; i < rows; i++)
    {
        for (j = 0; j < cols; j++)
        {
            result[i][j] = a[i][j] + b[i][j];
        }
    }
}

int main()
{
    int a[10][10], b[10][10], result[10][10];
    int rows, cols, i, j;

    printf("Enter rows and columns: ");
    scanf("%d %d", &rows, &cols);

    if (rows < 1 || rows > 10 || cols < 1 || cols > 10)
    {
        printf("Invalid matrix size");
        return 0;
    }

    printf("Enter first matrix:\n");

    for (i = 0; i < rows; i++)
    {
        for (j = 0; j < cols; j++)
        {
            scanf("%d", &a[i][j]);
        }
    }

    printf("Enter second matrix:\n");

    for (i = 0; i < rows; i++)
    {
        for (j = 0; j < cols; j++)
        {
            scanf("%d", &b[i][j]);
        }
    }

    addMatrices(a, b, result, rows, cols);

    printf("Result matrix:\n");

    for (i = 0; i < rows; i++)
    {
        for (j = 0; j < cols; j++)
        {
            printf("%d ", result[i][j]);
        }

        printf("\n");
    }

    return 0;
}
```

Expected Output:

```
Enter rows and columns: 2 2
Enter first matrix:
1 2
3 4
Enter second matrix:
5 6
7 8
Result matrix:
6 8
10 12
```

Why is this important? Students learn how to pass matrices and multiple arrays to a function.

Where is it used? Engineering computations, scientific applications and image processing.

## 28. Create a Calculator Using Multiple Functions

Question: Write a C program to create a simple calculator using separate functions for addition, subtraction, multiplication and division.

Concept: Multiple user-defined functions.

```
#include <stdio.h>

float add(float a, float b)
{
    return a + b;
}

float subtract(float a, float b)
{
    return a - b;
}

float multiply(float a, float b)
{
    return a * b;
}

float divide(float a, float b)
{
    return a / b;
}

int main()
{
    float a, b;
    int choice;

    printf("1. Addition\n");
    printf("2. Subtraction\n");
    printf("3. Multiplication\n");
    printf("4. Division\n");

    printf("Enter your choice: ");
    scanf("%d", &choice);

    printf("Enter two numbers: ");
    scanf("%f %f", &a, &b);

    switch (choice)
    {
        case 1:
            printf("Result = %.2f", add(a, b));
            break;

        case 2:
            printf("Result = %.2f", subtract(a, b));
            break;

        case 3:
            printf("Result = %.2f", multiply(a, b));
            break;

        case 4:
            if (b != 0)
                printf("Result = %.2f", divide(a, b));
            else
                printf("Division by zero is not possible");
            break;

        default:
            printf("Invalid choice");
    }

    return 0;
}
```

Expected Output:

```
1. Addition
2. Subtraction
3. Multiplication
4. Division
Enter your choice: 1
Enter two numbers: 20 10
Result = 30.00
```

Why is this important? Students understand modular programming by dividing one application into multiple functions.

Where is it used? Calculator applications, billing software and financial systems.

## 29. Calculate Student Total and Average Using Functions

Question: Write a C program to read marks of five subjects and calculate total and average using separate functions.

Concept: Multiple functions, arrays and return values.

```
#include <stdio.h>

int calculateTotal(int marks[], int n)
{
    int i, total = 0;

    for (i = 0; i < n; i++)
    {
        total += marks[i];
    }

    return total;
}

float calculateAverage(int total, int n)
{
    return (float)total / n;
}

int main()
{
    int marks[5], i, total;
    float average;

    printf("Enter marks of five subjects:\n");

    for (i = 0; i < 5; i++)
    {
        scanf("%d", &marks[i]);

        if (marks[i] < 0 || marks[i] > 100)
        {
            printf("Invalid marks");
            return 0;
        }
    }

    total = calculateTotal(marks, 5);
    average = calculateAverage(total, 5);

    printf("Total marks = %d\n", total);
    printf("Average = %.2f", average);

    return 0;
}
```

Expected Output:

```
Enter marks of five subjects:
80
90
75
85
70
Total marks = 400
Average = 80.00
```

Why is this important? Students learn how to divide a real application into smaller independent functions.

Where is it used? College result processing, examination systems and student management applications.

## 30. Menu-Driven Student Utility Program Using Functions

Question: Write a C program that displays a menu to perform the following operations using separate functions:

1. Find square of a number.
2. Check even or odd.
3. Find factorial.
4. Check prime number.
5. Exit.

Concept: Menu-driven programming, multiple functions, `switch` and loops.

```
#include <stdio.h>

int square(int n)
{
    return n * n;
}

void checkEvenOdd(int n)
{
    if (n % 2 == 0)
        printf("Even number\n");
    else
        printf("Odd number\n");
}

int factorial(int n)
{
    int i, fact = 1;

    for (i = 1; i <= n; i++)
    {
        fact = fact * i;
    }

    return fact;
}

int isPrime(int n)
{
    int i;

    if (n <= 1)
        return 0;

    for (i = 2; i <= n / i; i++)
    {
        if (n % i == 0)
            return 0;
    }

    return 1;
}

int main()
{
    int choice, num;

    do
    {
        printf("\n--- MENU ---\n");
        printf("1. Square\n");
        printf("2. Even or Odd\n");
        printf("3. Factorial\n");
        printf("4. Prime Check\n");
        printf("5. Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        if (choice >= 1 && choice <= 4)
        {
            printf("Enter a number: ");
            scanf("%d", &num);
        }

        switch (choice)
        {
            case 1:
                printf("Square = %d\n", square(num));
                break;

            case 2:
                checkEvenOdd(num);
                break;

            case 3:
                if (num < 0 || num > 12)
                    printf("Enter a number between 0 and 12\n");
                else
                    printf("Factorial = %d\n", factorial(num));
                break;

            case 4:
                if (isPrime(num))
                    printf("Prime number\n");
                else
                    printf("Not a prime number\n");
                break;

            case 5:
                printf("Exiting program...\n");
                break;

            default:
                printf("Invalid choice\n");
        }

    } while (choice != 5);

    return 0;
}
```

Expected Output:

```
--- MENU ---
1. Square
2. Even or Odd
3. Factorial
4. Prime Check
5. Exit
Enter your choice: 1
Enter a number: 5
Square = 25

--- MENU ---
1. Square
2. Even or Odd
3. Factorial
4. Prime Check
5. Exit
Enter your choice: 5
Exiting program...
```

Why is this important? This program combines functions, loops, conditions and modular programming into one application.

Where is it used? Banking applications, student management systems, billing software and utility applications.

# Complete Functions Practice – 30 Programs

| Programs | Topics covered                                                       |
| -------- | -------------------------------------------------------------------- |
| 1–10     | Function basics, four types, arrays and pointers                     |
| 11–20    | Prime, Fibonacci, palindrome, GCD, LCM, arrays and strings           |
| 21–30    | Recursion, sorting, searching, matrices and menu-driven applications |

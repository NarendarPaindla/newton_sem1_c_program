# C Programming – Functions (Complete Beginner-Friendly Teaching Notes)


<img width="1574" height="974" alt="image" src="https://github.com/user-attachments/assets/3e509c17-ce9a-409b-a225-02b2bfc34a3a" />


## 1. What is a function?

Definition: A function is a block of code that performs a specific task. It can be called whenever that task needs to be performed.

### Real-time example

Imagine a college:

- Principal manages the college.
- HOD manages a department.
- Faculty members handle classes.
- Lab assistants manage laboratory activities.

Each person performs a specific responsibility.

Similarly, in C programming, each function performs a particular task.

For example, in a student management application:

- `readMarks()` – reads student marks.
- `calculateTotal()` – calculates total marks.
- `calculateAverage()` – calculates average marks.
- `displayResult()` – displays the result.

Instead of writing all the code inside `main()`, we divide the program into smaller functions.

## 2. Why do we need functions?

Consider a program that calculates the square of three numbers.

Without functions:

```
#include <stdio.h>

int main()
{
    int a = 5, b = 10, c = 15;

    printf("Square of a = %d\n", a * a);
    printf("Square of b = %d\n", b * b);
    printf("Square of c = %d\n", c * c);

    return 0;
}
```

The same calculation is repeated multiple times.

With functions:

```
#include <stdio.h>

void square(int n)
{
    printf("Square = %d\n", n * n);
}

int main()
{
    square(5);
    square(10);
    square(15);

    return 0;
}
```

Now we write the calculation once and reuse it whenever required.

### Advantages of functions

1. Code reusability.
2. Reduces code duplication.
3. Makes programs easier to understand.
4. Makes debugging easier.
5. Improves code organization.
6. Supports modular programming.

## 3. Structure of a function in C

A function generally involves three important parts:

<img width="1916" height="1044" alt="image" src="https://github.com/user-attachments/assets/22eca9a2-1e09-40ea-9058-0beeb28beed8" />


### General syntax

```
return_type function_name(parameters)
{
    // Statements

    return value;
}
```

Example:

```
int add(int a, int b)
{
    int sum = a + b;

    return sum;
}
```

| Component      | Meaning           |
| -------------- | ----------------- |
| `int`          | Return type       |
| `add`          | Function name     |
| `int a, int b` | Parameters        |
| `{ }`          | Function body     |
| `return sum`   | Sends result back |

## 4. Three important parts of functions

### A. Function declaration (prototype)

It informs the compiler about the function name, return type and parameters before the function is called.

```
int add(int, int);
```

### B. Function call

It executes the function.

```
result = add(10, 20);
```

### C. Function definition

It contains the actual implementation.

```
int add(int a, int b)
{
    return a + b;
}
```

### Complete example

```
#include <stdio.h>

// Function declaration
int add(int, int);

int main()
{
    int result;

    // Function call
    result = add(10, 20);

    printf("Sum = %d", result);

    return 0;
}

// Function definition
int add(int a, int b)
{
    return a + b;
}
```

Output:

```
Sum = 30
```

Explain this execution to students:

1. Program execution starts from `main()`.
2. `add(10, 20)` is called.
3. Values 10 and 20 are passed to the function.
4. The function calculates 30.
5. `return` sends 30 back to `main()`.
6. The result is printed.

## 5. Types of functions in C

Functions are broadly classified into two categories.

<img width="1902" height="988" alt="image" src="https://github.com/user-attachments/assets/bd42caab-b237-4902-903e-161ae3049f90" />


### A. Library functions

These are predefined functions provided by C libraries.

Examples:

| Function    | Purpose                         | Header file |
| ----------- | ------------------------------- | ----------- |
| `printf()`  | Displays output                 | `stdio.h`   |
| `scanf()`   | Reads input                     | `stdio.h`   |
| `strlen()`  | Finds string length             | `string.h`  |
| `sqrt()`    | Calculates square root          | `math.h`    |
| `toupper()` | Converts character to uppercase | `ctype.h`   |
| `strcmp()`  | Compares strings                | `string.h`  |

### B. User-defined functions

These are functions created by programmers according to their requirements.

Example:

```
void welcome()
{
    printf("Welcome to C Programming!");
}
```

Here, `welcome()` is a user-defined function.

## 6. Four categories of user-defined functions

This is one of the most important concepts for examinations and practical programming.

Functions are classified based on:

- Whether they accept arguments.
- Whether they return a value.

Four types of functions

1\. No arguments and no return value

`void display(void)`

2\. Arguments and no return value

`void add(int a, int b)`

3\. No arguments but returns a value

`int getNumber(void)`

4\. Arguments and returns a value

`int add(int a, int b)`

### Type 1: No arguments and no return value

The function does not receive any input from the calling function and does not return any result.

```
#include <stdio.h>

void greet()
{
    printf("Welcome Students!");
}

int main()
{
    greet();

    return 0;
}
```

Output:

```
Welcome Students!
```

Explanation:

- `void` means the function does not return a value.
- `greet()` does not receive arguments.
- It directly displays the message.

### Type 2: Arguments and no return value

The function receives values but does not return any result.

```
#include <stdio.h>

void add(int a, int b)
{
    printf("Sum = %d", a + b);
}

int main()
{
    add(10, 20);

    return 0;
}
```

Output:

```
Sum = 30
```

Explanation:

- `10` and `20` are passed to the function.
- `a` receives 10.
- `b` receives 20.
- The function prints the sum.
- It does not return a value.

### Type 3: No arguments but returns a value

The function does not receive input from the calling function but returns a result.

```
#include <stdio.h>

int getNumber()
{
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    return n;
}

int main()
{
    int result;

    result = getNumber();

    printf("Number = %d", result);

    return 0;
}
```

Output:

```
Enter a number: 25
Number = 25
```

Explanation:

- `getNumber()` reads input internally.
- It returns the entered number.
- `main()` receives the returned value.

### Type 4: Arguments and returns a value

The function receives values and returns the calculated result.

```
#include <stdio.h>

int add(int a, int b)
{
    return a + b;
}

int main()
{
    int result;

    result = add(10, 20);

    printf("Sum = %d", result);

    return 0;
}
```

Output:

```
Sum = 30
```

Explanation:

- Two values are passed to the function.
- The function calculates their sum.
- It returns the sum to `main()`.

### Comparison of four types

| Type   | Arguments | Return value |
| ------ | --------- | ------------ |
| Type 1 | No        | No           |
| Type 2 | Yes       | No           |
| Type 3 | No        | Yes          |
| Type 4 | Yes       | Yes          |

## 7. Actual arguments and formal arguments

This is another important concept.

Consider:

```
int add(int a, int b)
{
    return a + b;
}

int main()
{
    int result = add(10, 20);

    printf("%d", result);

    return 0;
}
```

- Actual arguments: Values passed during the function call: `10, 20`.
- Formal arguments: Variables receiving those values in the function definition: `a, b`.

<img width="1908" height="1070" alt="image" src="https://github.com/user-attachments/assets/701e8dbe-0542-44e6-96bf-23e7e5cbdb3d" />


## 8. Call by value

Definition: In call by value, a copy of the actual argument is passed to the function. Changes made to the function's parameter do not change the original variable.

### Real-time example

Suppose you give a photocopy of a document to someone.

If that person modifies the photocopy, your original document remains unchanged.

Similarly, C passes copies of values in ordinary function calls.

```
#include <stdio.h>

void change(int x)
{
    x = 100;
    printf("Inside function = %d\n", x);
}

int main()
{
    int a = 10;

    change(a);

    printf("Inside main = %d", a);

    return 0;
}
```

Output:

```
Inside function = 100
Inside main = 10
```

Important observation: The original variable `a` remains 10.

## 9. Call by reference using pointers

C does not have a separate formal call-by-reference mechanism. We achieve similar behavior by passing addresses using pointers.

```
#include <stdio.h>

void change(int *x)
{
    *x = 100;
}

int main()
{
    int a = 10;

    change(&a);

    printf("Value of a = %d", a);

    return 0;
}
```

Output:

```
Value of a = 100
```

Explanation:

- `&a` passes the address of `a`.
- `int *x` receives that address.
- `*x = 100` modifies the original variable.

This topic connects functions with pointers, which students will learn in detail in the pointers unit.

## 10. Local and global variables

### Local variable

A variable declared inside a function or block is called a local variable. It can be accessed only within its scope.

```
#include <stdio.h>

void display()
{
    int a = 10;

    printf("Inside function = %d\n", a);
}

int main()
{
    display();

    return 0;
}
```

### Global variable

A variable declared outside all functions is called a global variable.

```
#include <stdio.h>

int a = 100;

void display()
{
    printf("Inside function = %d\n", a);
}

int main()
{
    printf("Inside main = %d\n", a);

    display();

    return 0;
}
```

Output:

```
Inside main = 100
Inside function = 100
```

| Local variable                        | Global variable                                                 |
| ------------------------------------- | --------------------------------------------------------------- |
| Declared inside a function or block   | Declared outside functions                                      |
| Accessible within its scope           | Accessible by functions after its declaration                   |
| Exists during its block's execution   | Exists throughout program execution                             |
| Usually not initialized automatically | Automatically initialized to zero if not explicitly initialized |

# 11. Practical examples to demonstrate in class

### Example 1: Find the square of a number using a function

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

Input:

```
Enter a number: 5
```

Output:

```
Square = 25
```

### Example 2: Check even or odd using a function

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

Input:

```
Enter a number: 7
```

Output:

```
Odd number
```

### Example 3: Find the largest of two numbers using a function

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
    int x, y;

    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);

    printf("Largest = %d", largest(x, y));

    return 0;
}
```

Input:

```
Enter two numbers: 25 40
```

Output:

```
Largest = 40
```

# 12. Introduction to recursion

Definition: Recursion is a programming technique in which a function calls itself to solve a problem.

Real-world analogy: Imagine standing between two mirrors. You can see repeated reflections of the same image.

In programming, a recursive function repeatedly calls itself until a stopping condition is reached.

### Example: Factorial using recursion

Factorial of 5:

\\[ 5! = 5 \times 4 \times 3 \times 2 \times 1 = 120 \\]

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
    int n;

    printf("Enter a number: ");
    scanf("%d", &n);

    printf("Factorial = %d", factorial(n));

    return 0;
}
```

Input:

```
Enter a number: 5
```

Output:

```
Factorial = 120
```

Important: Every recursive function must have a base condition to stop recursion.

# 13. Common mistakes students should avoid

1. Forgetting the function declaration when the function definition appears after `main()`.
2. Using an incorrect return type.
3. Forgetting the `return` statement in a non-void function.
4. Passing the wrong number of arguments.
5. Confusing actual arguments with formal parameters.
6. Expecting call-by-value changes to modify original variables.
7. Writing a recursive function without a base condition.

# 14. Viva questions

1. What is a function in C?
2. Why do we use functions?
3. What is a function prototype?
4. What is a function call?
5. What is a function definition?
6. What is the difference between library and user-defined functions?
7. What is a return type?
8. What is the purpose of the `void` keyword?
9. What are actual arguments?
10. What are formal arguments?
11. What are the four categories of functions?
12. What is call by value?
13. How can we modify the original variable through a function in C?
14. What is recursion?
15. What is a base condition?
16. What is the difference between local and global variables?

# 15. Suggested teaching sequence

| Class | Topic                            | Practical activity      |
| ----- | -------------------------------- | ----------------------- |
| 1     | Introduction to functions        | Greeting and square     |
| 2     | Declaration, definition and call | Addition                |
| 3     | Four types of functions          | Four addition examples  |
| 4     | Arguments and return values      | Largest of two numbers  |
| 5     | Call by value                    | Variable modification   |
| 6     | Pointers with functions          | Swap two numbers        |
| 7     | Local and global variables       | Scope demonstration     |
| 8     | Recursion                        | Factorial and Fibonacci |

My recommendation: Spend sufficient time on the four types of functions.

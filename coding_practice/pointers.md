# Pointers in C – 30 Hands-on Programs

## Batch 1: Programs 1–10

These first 10 programs cover pointer declaration, initialization, dereferencing, modifying values, pointer arithmetic, arrays, and functions.

## 1. Display Value and Address of a Variable Using Pointer

Question: Write a C program to declare an integer variable and a pointer. Display the variable's value, its address, and the value accessed through the pointer.

Concept: Pointer declaration, initialization, address-of (`&`) and dereference (`*`) operators.

C Program:

```
#include <stdio.h>

int main() {

    int a = 10;

    int *ptr;

    ptr = &a;

    printf("Value of a: %d\n", a);

    printf("Address of a: %p\n", (void *)&a);

    printf("Address stored in ptr: %p\n", (void *)ptr);

    printf("Value using pointer: %d\n", *ptr);

    return 0;
}
```

Expected Output (sample):

```
Value of a: 10
Address of a: 0061FF1C
Address stored in ptr: 0061FF1C
Value using pointer: 10
```

Why is this important?

It introduces the basic relationship between variables, memory addresses, and pointers.

Where is it used?

Memory management and accessing variables indirectly.

## 2. Modify a Variable's Value Using a Pointer

Question: Write a C program to change the value of an integer variable using a pointer.

Concept: Dereferencing a pointer to modify the original variable.

C Program:

```
#include <stdio.h>

int main() {

    int a = 20;

    int *ptr = &a;

    printf("Before modification: %d\n", a);

    *ptr = 100;

    printf("After modification: %d\n", a);

    return 0;
}
```

Expected Output:

```
Before modification: 20
After modification: 100
```

Why is this important?

It demonstrates how a pointer can modify the original variable without accessing it directly.

Where is it used?

Updating values through functions and modifying data in memory.

## 3. Add Two Numbers Using Pointers

Question: Write a C program to read two integers and calculate their sum using pointers.

Concept: Accessing variable values through pointers.

C Program:

```
#include <stdio.h>

int main() {

    int a, b, sum;

    int *p1, *p2;

    p1 = &a;
    p2 = &b;

    printf("Enter two numbers: ");
    scanf("%d %d", p1, p2);

    sum = *p1 + *p2;

    printf("First number: %d\n", *p1);

    printf("Second number: %d\n", *p2);

    printf("Sum: %d\n", sum);

    return 0;
}
```

Expected Output:

```
Enter two numbers: 10 20

First number: 10
Second number: 20
Sum: 30
```

Why is this important?

It teaches how pointers can be used to read and process values.

Where is it used?

Mathematical calculations and memory-based data processing.

## 4. Swap Two Numbers Using Pointers

Question: Write a C program to swap two numbers using pointers.

Concept: Pointer dereferencing and temporary variables.

C Program:

```
#include <stdio.h>

int main() {

    int a = 10, b = 20;

    int *p1 = &a;
    int *p2 = &b;

    int temp;

    printf("Before swapping:\n");

    printf("a = %d\n", a);
    printf("b = %d\n", b);

    temp = *p1;

    *p1 = *p2;

    *p2 = temp;

    printf("\nAfter swapping:\n");

    printf("a = %d\n", a);
    printf("b = %d\n", b);

    return 0;
}
```

Expected Output:

```
Before swapping:
a = 10
b = 20

After swapping:
a = 20
b = 10
```

Why is this important?

It demonstrates how pointers can modify two original variables.

Where is it used?

Sorting algorithms and data manipulation.

## 5. Find the Largest of Two Numbers Using Pointers

Question: Write a C program to read two numbers and find the largest number using pointers.

Concept: Pointer dereferencing with conditional statements.

C Program:

```
#include <stdio.h>

int main() {

    int a, b;

    int *p1 = &a;
    int *p2 = &b;

    printf("Enter two numbers: ");
    scanf("%d %d", p1, p2);

    if(*p1 > *p2) {

        printf("Largest number: %d\n", *p1);
    }
    else if(*p2 > *p1) {

        printf("Largest number: %d\n", *p2);
    }
    else {

        printf("Both numbers are equal.\n");
    }

    return 0;
}
```

Expected Output:

```
Enter two numbers: 50 30

Largest number: 50
```

Why is this important?

It combines pointer operations with decision-making.

Where is it used?

Comparing values in applications and processing records.

## 6. Print Array Elements Using a Pointer

Question: Write a C program to read five integers into an array and display all elements using a pointer.

Concept: Pointers and arrays.

C Program:

```
#include <stdio.h>

int main() {

    int arr[5];

    int *ptr = arr;

    int i;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {

        scanf("%d", &arr[i]);
    }

    printf("\nArray Elements:\n");

    for(i = 0; i < 5; i++) {

        printf("%d ", *(ptr + i));
    }

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
10 20 30 40 50

Array Elements:
10 20 30 40 50
```

Why is this important?

It teaches how array elements can be accessed using pointer arithmetic.

Where is it used?

Array processing, sorting, searching, and data structures.

## 7. Find the Sum of Array Elements Using Pointers

Question: Write a C program to read five integers and calculate their sum using pointers.

Concept: Pointer arithmetic and array traversal.

C Program:

```
#include <stdio.h>

int main() {

    int arr[5];

    int *ptr = arr;

    int i, sum = 0;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {

        scanf("%d", &arr[i]);
    }

    for(i = 0; i < 5; i++) {

        sum = sum + *(ptr + i);
    }

    printf("Sum of array elements: %d\n", sum);

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
10 20 30 40 50

Sum of array elements: 150
```

Why is this important?

It demonstrates how pointers can traverse an array and perform calculations.

Where is it used?

Statistical calculations and processing large collections of data.

## 8. Find the Largest Array Element Using Pointers

Question: Write a C program to read five integers and find the largest element using pointers.

Concept: Pointer arithmetic and comparison.

C Program:

```
#include <stdio.h>

int main() {

    int arr[5];

    int *ptr = arr;

    int i, largest;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {

        scanf("%d", &arr[i]);
    }

    largest = *ptr;

    for(i = 1; i < 5; i++) {

        if(*(ptr + i) > largest) {

            largest = *(ptr + i);
        }
    }

    printf("Largest element: %d\n", largest);

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
10 45 20 80 30

Largest element: 80
```

Why is this important?

It teaches how to compare array elements using pointers.

Where is it used?

Finding maximum values in marks lists, sales records, and datasets.

## 9. Reverse an Array Using Pointers

Question: Write a C program to read five integers and reverse the array using pointers.

Concept: Pointer arithmetic and swapping array elements.

C Program:

```
#include <stdio.h>

int main() {

    int arr[5];

    int *ptr = arr;

    int i, temp;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {

        scanf("%d", &arr[i]);
    }

    for(i = 0; i < 5 / 2; i++) {

        temp = *(ptr + i);

        *(ptr + i) = *(ptr + (4 - i));

        *(ptr + (4 - i)) = temp;
    }

    printf("\nReversed Array:\n");

    for(i = 0; i < 5; i++) {

        printf("%d ", *(ptr + i));
    }

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
10 20 30 40 50

Reversed Array:
50 40 30 20 10
```

Why is this important?

It combines pointer arithmetic with swapping operations.

Where is it used?

Reversing data sequences, processing strings, and array manipulation.

## 10. Swap Two Numbers Using a Function and Pointers

Question: Write a C program to swap two numbers using a user-defined function that accepts pointers as arguments.

Concept: Passing pointers to functions and modifying original variables.

C Program:

```
#include <stdio.h>

void swap(int *a, int *b) {

    int temp;

    temp = *a;

    *a = *b;

    *b = temp;
}

int main() {

    int x, y;

    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);

    printf("\nBefore swapping:\n");

    printf("x = %d\n", x);
    printf("y = %d\n", y);

    swap(&x, &y);

    printf("\nAfter swapping:\n");

    printf("x = %d\n", x);
    printf("y = %d\n", y);

    return 0;
}
```

Expected Output:

```
Enter two numbers: 100 200

Before swapping:
x = 100
y = 200

After swapping:
x = 200
y = 100
```

Why is this important?

It demonstrates how functions can modify original variables by receiving their addresses. C uses pass-by-value, but passing addresses allows a function to modify the pointed-to objects.

Where is it used?

Sorting algorithms, swapping array elements, and modifying data through functions.

## Batch 1 – Concepts Covered

| Program | Concept                                |
| ------- | -------------------------------------- |
| 1       | Pointer declaration and initialization |
| 2       | Modifying variables using pointers     |
| 3       | Arithmetic using pointers              |
| 4       | Swapping using pointers                |
| 5       | Comparison using pointers              |
| 6       | Pointers and arrays                    |
| 7       | Sum of array using pointers            |
| 8       | Largest element using pointers         |
| 9       | Reverse array using pointers           |
| 10      | Pointers with functions                |



# Pointers in C – Batch 2: Programs 11–20

In this batch, we will cover pointer arithmetic, strings using pointers, pointer-to-pointer, and pointers with functions.

## 11. Print Array Elements Using Pointer Increment

Question: Write a C program to read five integers into an array and display them using pointer increment (`ptr++`).

Concept: Pointer arithmetic – increment operator.

C Program:

```
#include <stdio.h>

int main() {

    int arr[5];

    int *ptr = arr;

    int i;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {
        scanf("%d", &arr[i]);
    }

    printf("\nArray Elements:\n");

    for(i = 0; i < 5; i++) {

        printf("%d ", *ptr);

        ptr++;
    }

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
10 20 30 40 50

Array Elements:
10 20 30 40 50
```

Explanation:

- Initially, `ptr` points to `arr[0]`.
- `*ptr` accesses the current element.
- `ptr++` moves to the next array element.
- The loop repeats until all five elements are displayed.

Why is this important?

It teaches students how pointers move through consecutive array elements.

Where is it used?

Array traversal, data processing, and low-level memory operations.

## 12. Find the Smallest Element in an Array Using Pointers

Question: Write a C program to read five integers and find the smallest element using pointers.

Concept: Pointer arithmetic and comparison.

C Program:

```
#include <stdio.h>

int main() {

    int arr[5];

    int *ptr = arr;

    int i, smallest;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {
        scanf("%d", &arr[i]);
    }

    smallest = *ptr;

    for(i = 1; i < 5; i++) {

        if(*(ptr + i) < smallest) {
            smallest = *(ptr + i);
        }
    }

    printf("Smallest element: %d\n", smallest);

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
40 10 50 20 30

Smallest element: 10
```

Why is this important?

It reinforces how pointers can access and compare array elements.

Where is it used?

Finding minimum prices, lowest marks, and minimum values in datasets.

## 13. Count Even and Odd Numbers Using Pointers

Question: Write a C program to read ten integers and count the number of even and odd elements using pointers.

Concept: Pointer arithmetic and conditional statements.

C Program:

```
#include <stdio.h>

int main() {

    int arr[10];

    int *ptr = arr;

    int i, even = 0, odd = 0;

    printf("Enter 10 numbers:\n");

    for(i = 0; i < 10; i++) {
        scanf("%d", &arr[i]);
    }

    for(i = 0; i < 10; i++) {

        if(*(ptr + i) % 2 == 0) {
            even++;
        }
        else {
            odd++;
        }
    }

    printf("\nEven numbers: %d\n", even);

    printf("Odd numbers: %d\n", odd);

    return 0;
}
```

Expected Output:

```
Enter 10 numbers:
1 2 3 4 5 6 7 8 9 10

Even numbers: 5
Odd numbers: 5
```

Why is this important?

It combines pointers, loops, and decision-making.

Where is it used?

Data classification and number processing applications.

## 14. Copy One Array into Another Using Pointers

Question: Write a C program to read five integers into one array and copy all elements into another array using pointers.

Concept: Pointer arithmetic and array copying.

C Program:

```
#include <stdio.h>

int main() {

    int arr1[5], arr2[5];

    int *p1 = arr1;
    int *p2 = arr2;

    int i;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {
        scanf("%d", p1 + i);
    }

    for(i = 0; i < 5; i++) {

        *(p2 + i) = *(p1 + i);
    }

    printf("\nCopied Array Elements:\n");

    for(i = 0; i < 5; i++) {
        printf("%d ", *(p2 + i));
    }

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
10 20 30 40 50

Copied Array Elements:
10 20 30 40 50
```

Why is this important?

It teaches students how to transfer data between memory locations using pointers.

Where is it used?

Data copying, backup operations, and array processing.

## 15. Reverse a String Using Pointers

Question: Write a C program to read a string and reverse it using pointers.

Concept: Character pointers and pointer arithmetic.

C Program:

```
#include <stdio.h>
#include <string.h>

int main() {

    char str[100];

    char *start, *end;

    char temp;

    printf("Enter a string: ");
    scanf("%99s", str);

    start = str;

    end = str + strlen(str) - 1;

    while(start < end) {

        temp = *start;

        *start = *end;

        *end = temp;

        start++;

        end--;
    }

    printf("Reversed string: %s\n", str);

    return 0;
}
```

Expected Output:

```
Enter a string: HELLO

Reversed string: OLLEH
```

Explanation:

Suppose the string is `HELLO`.

- `start` points to `H`.
- `end` points to `O`.
- Swap the first and last characters.
- Move `start` forward and `end` backward.
- Continue until both pointers meet or cross.

Why is this important?

It teaches how strings are stored as character arrays and manipulated using pointers.

Where is it used?

Text processing, string manipulation, and palindrome checking.

## 16. Find String Length Using Pointers

Question: Write a C program to calculate the length of a string using pointers without using `strlen()`.

Concept: Character pointer traversal.

C Program:

```
#include <stdio.h>

int main() {

    char str[100];

    char *ptr;

    int length = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    ptr = str;

    while(*ptr != '\0') {

        length++;

        ptr++;
    }

    printf("Length of string: %d\n", length);

    return 0;
}
```

Expected Output:

```
Enter a string: PROGRAMMING

Length of string: 11
```

Explanation:

- `ptr = str` points to the first character.
- `*ptr` accesses the current character.
- `'\0'` represents the end of a C string.
- `ptr++` moves to the next character.
- Every character is counted until the null character is reached.

Why is this important?

It helps students understand how C strings are terminated and traversed.

Where is it used?

Text processing and string-handling functions.

## 17. Compare Two Strings Using Pointers

Question: Write a C program to compare two strings using pointers without using `strcmp()`.

Concept: String comparison using character pointers.

C Program:

```
#include <stdio.h>

int main() {

    char str1[100], str2[100];

    char *p1, *p2;

    int equal = 1;

    printf("Enter first string: ");
    scanf("%99s", str1);

    printf("Enter second string: ");
    scanf("%99s", str2);

    p1 = str1;
    p2 = str2;

    while(*p1 != '\0' || *p2 != '\0') {

        if(*p1 != *p2) {

            equal = 0;

            break;
        }

        p1++;
        p2++;
    }

    if(equal == 1) {
        printf("Strings are equal.\n");
    }
    else {
        printf("Strings are not equal.\n");
    }

    return 0;
}
```

Expected Output:

```
Enter first string: HELLO
Enter second string: HELLO

Strings are equal.
```

Why is this important?

It demonstrates how two strings can be compared character by character using pointers.

Where is it used?

Password checking, username comparison, and text matching.

## 18. Find the Sum of Two Numbers Using a Function and Pointers

Question: Write a C program to calculate the sum of two numbers using a function that accepts pointers as arguments.

Concept: Passing pointer arguments to functions.

C Program:

```
#include <stdio.h>

int add(int *a, int *b) {

    return *a + *b;
}

int main() {

    int x, y, result;

    printf("Enter two numbers: ");
    scanf("%d %d", &x, &y);

    result = add(&x, &y);

    printf("Sum = %d\n", result);

    return 0;
}
```

Expected Output:

```
Enter two numbers: 20 30

Sum = 50
```

Why is this important?

It teaches how functions can receive addresses and access the values stored at those addresses.

Where is it used?

Modular programming and functions that process arrays or records.

## 19. Demonstrate Pointer to Pointer

Question: Write a C program to declare a normal integer variable, a pointer, and a pointer to pointer. Display the integer value using all three levels.

Concept: Double pointers (`**`).

C Program:

```
#include <stdio.h>

int main() {

    int a = 100;

    int *ptr = &a;

    int **pptr = &ptr;

    printf("Value of a: %d\n", a);

    printf("Using pointer: %d\n", *ptr);

    printf("Using pointer to pointer: %d\n", **pptr);

    return 0;
}
```

Expected Output:

```
Value of a: 100
Using pointer: 100
Using pointer to pointer: 100
```

Explanation:

```
int *ptr = &a;
```

The pointer stores the address of `a`.

```
int **pptr = &ptr;
```

The double pointer stores the address of `ptr`.

```
**pptr
```

Accesses the original integer value.

Why is this important?

It introduces multiple levels of indirection.

Where is it used?

Dynamic memory allocation, modifying pointers through functions, and complex data structures.

## 20. Find the Sum and Average of Array Elements Using a Pointer Function

Question: Write a C program to read five integers and calculate their sum and average using a user-defined function that receives an array pointer.

Concept: Arrays as function arguments, pointers, and return values.

C Program:

```
#include <stdio.h>

float calculateAverage(int *ptr, int size) {

    int i, sum = 0;

    for(i = 0; i < size; i++) {

        sum = sum + *(ptr + i);
    }

    return (float)sum / size;
}

int main() {

    int arr[5];

    int i, sum = 0;

    float average;

    printf("Enter 5 elements:\n");

    for(i = 0; i < 5; i++) {
        scanf("%d", &arr[i]);
    }

    for(i = 0; i < 5; i++) {
        sum = sum + arr[i];
    }

    average = calculateAverage(arr, 5);

    printf("\nSum: %d\n", sum);

    printf("Average: %.2f\n", average);

    return 0;
}
```

Expected Output:

```
Enter 5 elements:
10 20 30 40 50

Sum: 150
Average: 30.00
```

Why is this important?

It demonstrates how an array's address can be passed to a function for processing without copying the entire array.

Where is it used?

Statistical applications, marks processing, and large-scale array calculations.

## Batch 2 – Concepts Covered

| Program | Concept                           |
| ------- | --------------------------------- |
| 11      | Pointer increment                 |
| 12      | Smallest element using pointers   |
| 13      | Even and odd counting             |
| 14      | Array copying                     |
| 15      | String reversal using pointers    |
| 16      | String length using pointers      |
| 17      | String comparison using pointers  |
| 18      | Pointer arguments in functions    |
| 19      | Pointer to pointer                |
| 20      | Pointer-based function and arrays |

# Pointers in C – Batch 3: Programs 21–30

In this final batch, we will cover dynamic memory allocation and practical pointer applications.

These concepts are particularly important because they form the foundation for Linked Lists, Trees, Graphs, and other Data Structures.

## 21. Allocate Memory Using malloc()

Question: Write a C program to dynamically allocate memory for one integer using `malloc()`, accept a value, and display it.

Concept: Dynamic memory allocation using `malloc()`.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *ptr;

    ptr = (int *)malloc(sizeof(int));

    if(ptr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Enter a number: ");
    scanf("%d", ptr);

    printf("Entered number: %d\n", *ptr);

    free(ptr);

    return 0;
}
```

Expected Output:

```
Enter a number: 100

Entered number: 100
```

Explanation:

- `malloc()` dynamically allocates memory.
- `sizeof(int)` specifies how many bytes are needed for one integer.
- `ptr` stores the address of the allocated memory.
- `*ptr` accesses the allocated integer.
- `free(ptr)` releases the allocated memory.

Why is this important?

It teaches students how to allocate memory during program execution instead of declaring every variable in advance.

Where is it used?

Dynamic data structures, memory management, and applications that handle variable-sized data.

## 22. Allocate Memory for an Array Using malloc()

Question: Write a C program to dynamically allocate memory for five integers using `malloc()`, read the elements, and display them.

Concept: Dynamic array allocation.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *ptr;

    int n, i;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if(n <= 0) {
        printf("Invalid size!\n");
        return 1;
    }

    ptr = (int *)malloc(n * sizeof(int));

    if(ptr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Enter %d elements:\n", n);

    for(i = 0; i < n; i++) {
        scanf("%d", &ptr[i]);
    }

    printf("\nArray Elements:\n");

    for(i = 0; i < n; i++) {
        printf("%d ", ptr[i]);
    }

    free(ptr);

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5

Enter 5 elements:
10 20 30 40 50

Array Elements:
10 20 30 40 50
```

Explanation:

```
ptr = (int *)malloc(n * sizeof(int));
```

If `n = 5` and an integer occupies 4 bytes:

\\[ 5 \times 4 = 20 \text{ bytes} \\]

The program requests enough memory for five integers.

Why is this important?

It allows the program to decide the array size at runtime.

Where is it used?

Student marks processing, dynamic lists, and applications handling unknown numbers of records.

## 23. Allocate Memory Using calloc()

Question: Write a C program to allocate memory for five integers using `calloc()` and display their initial values.

Concept: Dynamic memory allocation using `calloc()`.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *ptr;

    int i, n = 5;

    ptr = (int *)calloc(n, sizeof(int));

    if(ptr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Initial Array Elements:\n");

    for(i = 0; i < n; i++) {
        printf("%d ", ptr[i]);
    }

    free(ptr);

    return 0;
}
```

Expected Output:

```
Initial Array Elements:
0 0 0 0 0
```

Explanation:

- `calloc()` allocates memory for multiple elements.
- It initializes all allocated bytes to zero.
- Therefore, the integer elements initially have the value zero.

Difference between malloc() and calloc():

| malloc()                      | calloc()                                  |
| ----------------------------- | ----------------------------------------- |
| Allocates one block of memory | Allocates memory for multiple elements    |
| Takes one size argument       | Takes number of elements and size of each |
| Memory is uninitialized       | Allocated bytes are initialized to zero   |

Why is this important?

It teaches the difference between two commonly used dynamic memory allocation functions.

Where is it used?

Initializing arrays and dynamically creating data structures.

## 24. Resize Memory Using realloc()

Question: Write a C program to allocate memory for three integers using `malloc()` and increase the size to five integers using `realloc()`.

Concept: Resizing dynamically allocated memory.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *ptr;
    int *temp;

    int i;

    ptr = (int *)malloc(3 * sizeof(int));

    if(ptr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Enter 3 elements:\n");

    for(i = 0; i < 3; i++) {
        scanf("%d", &ptr[i]);
    }

    temp = (int *)realloc(ptr, 5 * sizeof(int));

    if(temp == NULL) {
        printf("Memory resizing failed!\n");

        free(ptr);

        return 1;
    }

    ptr = temp;

    printf("\nEnter 2 more elements:\n");

    for(i = 3; i < 5; i++) {
        scanf("%d", &ptr[i]);
    }

    printf("\nFinal Array:\n");

    for(i = 0; i < 5; i++) {
        printf("%d ", ptr[i]);
    }

    free(ptr);

    return 0;
}
```

Expected Output:

```
Enter 3 elements:
10 20 30

Enter 2 more elements:
40 50

Final Array:
10 20 30 40 50
```

Explanation:

Initially:

```
malloc(3 * sizeof(int));
```

Memory is allocated for three integers.

Later:

```
realloc(ptr, 5 * sizeof(int));
```

The allocated memory is resized to hold five integers.

The original three values are preserved if resizing succeeds.

Important: Using a temporary pointer prevents losing the original allocated address if `realloc()` fails.

Why is this important?

It teaches how memory requirements can change during program execution.

Where is it used?

Dynamic arrays, growing lists, and applications where the amount of data changes.

## 25. Release Dynamically Allocated Memory Using free()

Question: Write a C program to allocate memory for an integer, assign a value, display it, and release the memory using `free()`.

Concept: Deallocating dynamically allocated memory.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *ptr;

    ptr = (int *)malloc(sizeof(int));

    if(ptr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    *ptr = 500;

    printf("Value: %d\n", *ptr);

    free(ptr);

    ptr = NULL;

    printf("Memory released successfully.\n");

    return 0;
}
```

Expected Output:

```
Value: 500
Memory released successfully.
```

Explanation:

```
free(ptr);
```

Releases the dynamically allocated memory.

```
ptr = NULL;
```

Clears the pointer so it no longer holds the old address.

Why is this important?

It prevents memory leaks when dynamically allocated memory is no longer required.

Where is it used?

Memory management in operating systems, applications, and data structures.

## 26. Find the Sum of Array Elements Using Dynamic Memory Allocation

Question: Write a C program to dynamically allocate memory for an array, read its elements, and calculate their sum.

Concept: `malloc()`, pointers, loops, and arithmetic operations.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *ptr;

    int n, i, sum = 0;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if(n <= 0) {
        printf("Invalid size!\n");
        return 1;
    }

    ptr = (int *)malloc(n * sizeof(int));

    if(ptr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Enter elements:\n");

    for(i = 0; i < n; i++) {

        scanf("%d", &ptr[i]);

        sum = sum + ptr[i];
    }

    printf("Sum of elements: %d\n", sum);

    free(ptr);

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5

Enter elements:
10 20 30 40 50

Sum of elements: 150
```

Why is this important?

It combines dynamic memory allocation with array processing.

Where is it used?

Processing large datasets and dynamically sized collections.

## 27. Create a Dynamic Array and Find the Largest Element

Question: Write a C program to dynamically allocate memory for an array and find the largest element.

Concept: Dynamic arrays and pointer-based comparison.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *ptr;

    int n, i, largest;

    printf("Enter number of elements: ");
    scanf("%d", &n);

    if(n <= 0) {
        printf("Invalid size!\n");
        return 1;
    }

    ptr = (int *)malloc(n * sizeof(int));

    if(ptr == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Enter elements:\n");

    for(i = 0; i < n; i++) {
        scanf("%d", &ptr[i]);
    }

    largest = ptr[0];

    for(i = 1; i < n; i++) {

        if(ptr[i] > largest) {
            largest = ptr[i];
        }
    }

    printf("Largest element: %d\n", largest);

    free(ptr);

    return 0;
}
```

Expected Output:

```
Enter number of elements: 5

Enter elements:
10 50 20 80 30

Largest element: 80
```

Why is this important?

It teaches how dynamically allocated arrays can be processed like normal arrays.

Where is it used?

Data analysis, result processing, and large collections of records.

## 28. Swap Two Numbers Using Pointers and Dynamic Memory Allocation

Question: Write a C program to dynamically allocate memory for two integers and swap their values using pointers.

Concept: Dynamic memory allocation and pointer dereferencing.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *a, *b;

    int temp;

    a = (int *)malloc(sizeof(int));

    b = (int *)malloc(sizeof(int));

    if(a == NULL || b == NULL) {

        printf("Memory allocation failed!\n");

        free(a);
        free(b);

        return 1;
    }

    printf("Enter two numbers: ");

    scanf("%d %d", a, b);

    printf("\nBefore swapping:\n");

    printf("a = %d\n", *a);
    printf("b = %d\n", *b);

    temp = *a;

    *a = *b;

    *b = temp;

    printf("\nAfter swapping:\n");

    printf("a = %d\n", *a);
    printf("b = %d\n", *b);

    free(a);
    free(b);

    return 0;
}
```

Expected Output:

```
Enter two numbers: 10 20

Before swapping:
a = 10
b = 20

After swapping:
a = 20
b = 10
```

Why is this important?

It combines pointers, memory allocation, and swapping.

Where is it used?

Dynamic data processing and memory-based applications.

## 29. Store Student Marks Using Dynamic Memory Allocation

Question: Write a C program to dynamically allocate memory for student marks. Read the marks of N students and calculate their total and average.

Concept: Dynamic memory allocation and array processing.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

int main() {

    int *marks;

    int n, i, total = 0;

    float average;

    printf("Enter number of students: ");
    scanf("%d", &n);

    if(n <= 0) {
        printf("Invalid number of students!\n");
        return 1;
    }

    marks = (int *)malloc(n * sizeof(int));

    if(marks == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    printf("Enter marks of students:\n");

    for(i = 0; i < n; i++) {

        scanf("%d", &marks[i]);

        total = total + marks[i];
    }

    average = (float)total / n;

    printf("\nTotal Marks: %d\n", total);

    printf("Average Marks: %.2f\n", average);

    free(marks);

    return 0;
}
```

Expected Output:

```
Enter number of students: 5

Enter marks of students:
80 90 85 75 70

Total Marks: 400
Average Marks: 80.00
```

Why is this important?

It demonstrates how pointers and dynamic memory allocation solve a practical problem where the number of students is not known in advance.

Where is it used?

College examination systems and student performance applications.

## 30. Mini Project – Dynamic Student Record Manager

Question: Develop a menu-driven C program that dynamically allocates memory for student records and supports these operations:

1. Add student records.
2. Display all student records.
3. Calculate the average marks.
4. Search for a student by roll number.
5. Exit.

Concept: Structures, pointers, dynamic memory allocation, `realloc()`, functions, and searching.

C Program:

```
#include <stdio.h>
#include <stdlib.h>

struct Student {

    int roll;

    char name[30];

    float marks;
};

int main() {

    struct Student *s = NULL;

    struct Student *temp;

    int count = 0;

    int choice, i, searchRoll;

    float total, average;

    do {

        printf("\n===== STUDENT RECORD MANAGER =====\n");

        printf("1. Add Student\n");
        printf("2. Display Students\n");
        printf("3. Calculate Average\n");
        printf("4. Search Student\n");
        printf("5. Exit\n");

        printf("Enter your choice: ");

        scanf("%d", &choice);

        switch(choice) {

            case 1:

                temp = (struct Student *)realloc(
                    s, (count + 1) * sizeof(struct Student)
                );

                if(temp == NULL) {

                    printf("Memory allocation failed!\n");

                    break;
                }

                s = temp;

                printf("\nEnter student name: ");

                scanf("%29s", s[count].name);

                printf("Enter roll number: ");

                scanf("%d", &s[count].roll);

                printf("Enter marks: ");

                scanf("%f", &s[count].marks);

                count++;

                printf("\nStudent added successfully!\n");

                break;

            case 2:

                if(count == 0) {

                    printf("\nNo student records available.\n");

                    break;
                }

                for(i = 0; i < count; i++) {

                    printf("\nName: %s\n", s[i].name);

                    printf("Roll: %d\n", s[i].roll);

                    printf("Marks: %.2f\n", s[i].marks);
                }

                break;

            case 3:

                if(count == 0) {

                    printf("\nNo student records available.\n");

                    break;
                }

                total = 0;

                for(i = 0; i < count; i++) {

                    total = total + s[i].marks;
                }

                average = total / count;

                printf("\nTotal Marks: %.2f\n", total);

                printf("Average Marks: %.2f\n", average);

                break;

            case 4:

                printf("\nEnter roll number to search: ");

                scanf("%d", &searchRoll);

                for(i = 0; i < count; i++) {

                    if(s[i].roll == searchRoll) {

                        printf("\nStudent Found!\n");

                        printf("Name: %s\n", s[i].name);

                        printf("Roll: %d\n", s[i].roll);

                        printf("Marks: %.2f\n", s[i].marks);

                        break;
                    }
                }

                if(i == count) {

                    printf("\nStudent not found!\n");
                }

                break;

            case 5:

                printf("\nExiting Program...\n");

                break;

            default:

                printf("\nInvalid choice!\n");
        }

    } while(choice != 5);

    free(s);

    return 0;
}
```

Expected Output (sample):

```
===== STUDENT RECORD MANAGER =====
1. Add Student
2. Display Students
3. Calculate Average
4. Search Student
5. Exit

Enter your choice: 1

Enter student name: Ravi
Enter roll number: 101
Enter marks: 85

Student added successfully!

Enter your choice: 1

Enter student name: Kiran
Enter roll number: 102
Enter marks: 95

Student added successfully!

Enter your choice: 2

Name: Ravi
Roll: 101
Marks: 85.00

Name: Kiran
Roll: 102
Marks: 95.00

Enter your choice: 3

Total Marks: 180.00
Average Marks: 90.00
```

Why is this important?

This project combines the most important pointer concepts into one application. The program can increase its allocated memory as new student records are added.

Where is it used?

Student management systems, college portals, and applications that manage dynamically growing records.

# Complete Pointer Programming Practice – 30 Programs

| Batch   | Programs | Main concepts                                |
| ------- | -------- | -------------------------------------------- |
| Batch 1 | 1–10     | Pointer basics, arrays, functions            |
| Batch 2 | 11–20    | Pointer arithmetic, strings, double pointers |
| Batch 3 | 21–30    | Dynamic memory allocation and mini project   |

## Important Dynamic Memory Functions

| Function    | Purpose                                                              |
| ----------- | -------------------------------------------------------------------- |
| `malloc()`  | Allocates a block of memory                                          |
| `calloc()`  | Allocates memory for multiple elements and initializes bytes to zero |
| `realloc()` | Resizes an allocated memory block                                    |
| `free()`    | Releases dynamically allocated memory                                |


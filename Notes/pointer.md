# Pointers in C Programming – Complete Teaching Notes

Pointers are one of the most important concepts in C programming. They are also a foundation for understanding dynamic memory allocation, linked lists, trees, and data structures.

Since students have already learned variables, arrays, functions, structures, and unions, we can now connect these concepts with pointers.

# 1. What is a Pointer?

A pointer is a special variable that stores the memory address of another variable.

Normally, a variable stores a value. A pointer stores the address where that value is located in memory.

### Real-world example

Imagine your college has a library.

- A book contains information.
- A book's location tells you where to find that book.
- Similarly, a variable stores a value.
- A pointer stores the memory address of that variable.

<img width="969" height="616" alt="image" src="https://github.com/user-attachments/assets/ad8dc7e8-946c-4cc5-9937-13e80f68408c" />


Simple example:

```
int a = 10;
```

Here:

- `a` is a variable.
- `10` is the value stored in the variable.
- The variable is stored at some memory address.

A pointer can store that memory address.

# 2. Why Do We Need Pointers?

You might ask students:

"If we can already store values using variables, why do we need pointers?"

Pointers are useful for:

1. Accessing memory addresses directly.
2. Modifying original variables through functions.
3. Efficiently processing arrays and strings.
4. Dynamic memory allocation.
5. Creating linked lists, trees, and graphs.
6. Working with structures and other complex data types.
7. Implementing call-by-reference behavior using addresses.

Real-world applications:

- Operating systems
- Database management systems
- Embedded systems
- Memory management
- Game development
- Data structures and algorithms

# 3. Understanding Memory Addresses

Every variable occupies some memory location.

Let's consider:

```
#include <stdio.h>

int main() {

    int a = 10;

    printf("Value of a: %d\n", a);
    printf("Address of a: %p\n", (void *)&a);

    return 0;
}
```

Sample output:

```
Value of a: 10
Address of a: 0061FF1C
```

The address shown is only an example. Actual addresses differ between executions and systems.

### Important operators

There are two important operators when learning pointers.

| Operator | Name                 | Purpose                                 |
| -------- | -------------------- | --------------------------------------- |
| `&`      | Address-of operator  | Returns the address of a variable       |
| `*`      | Dereference operator | Accesses the value stored at an address |

Example:

```
int a = 10;

printf("%d", a);
printf("%p", (void *)&a);
```

- `a` gives the value.
- `&a` gives the address.

# 4. Pointer Declaration

Syntax:

```
data_type *pointer_name;
```

Examples:

```
int *ptr;
float *fptr;
char *cptr;
```

Explanation:

- `int *ptr` declares a pointer intended to point to an integer.
- `float *fptr` declares a pointer intended to point to a float.
- `char *cptr` declares a pointer intended to point to a character.

Important: The pointer's data type determines the type of object it is intended to point to.

# 5. First Pointer Program

Question: Write a C program to declare an integer variable and a pointer. Store the address of the variable in the pointer and display the value and address.

C Program:

```
#include <stdio.h>

int main() {

    int a = 10;

    int *ptr;

    ptr = &a;

    printf("Value of a: %d\n", a);

    printf("Address of a: %p\n", (void *)&a);

    printf("Value stored in ptr: %p\n", (void *)ptr);

    printf("Value accessed using ptr: %d\n", *ptr);

    return 0;
}
```

Expected output (sample):

```
Value of a: 10
Address of a: 0061FF1C
Value stored in ptr: 0061FF1C
Value accessed using ptr: 10
```

### Explanation step by step

```
int a = 10;
```

Creates an integer variable.

```
int *ptr;
```

Declares an integer pointer.

```
ptr = &a;
```

Stores the address of `a` in `ptr`.

```
*ptr
```

Accesses the value stored at the address held by `ptr`.

Important observation: `&a` and `ptr` contain the same address. `*ptr` gives the value `10`.

# 6. Understanding Pointer Memory Representation

Consider:

```
int a = 50;
int *ptr = &a;
```

Illustrative memory representation

Pointer variable

# ptr

Stores address of a

Integer variable

# a = 50

Stores the actual value

ptr points to a

Conceptual illustration; actual memory addresses are assigned by the system.


<img width="1518" height="456" alt="image" src="https://github.com/user-attachments/assets/92b64f36-4440-4369-bef4-34bba8888af2" />


# 7. Modifying a Variable Using a Pointer

One of the most important features of pointers is that we can modify the original variable using its address.

Question: Write a C program to modify a variable's value using a pointer.

C Program:

```
#include <stdio.h>

int main() {

    int a = 10;

    int *ptr = &a;

    printf("Before modification: %d\n", a);

    *ptr = 50;

    printf("After modification: %d\n", a);

    return 0;
}
```

Output:

```
Before modification: 10
After modification: 50
```

### Explanation

Initially:

```
int a = 10;
```

Pointer:

```
int *ptr = &a;
```

Modification:

```
*ptr = 50;
```

This changes the value stored at the address of `a`.

Therefore, the original variable `a` becomes `50`.

Where is this used?

Modifying data through functions, updating records, and processing data structures.

# 8. Difference Between `ptr` and `*ptr`

This is a very important concept.

Consider:

```
int a = 100;

int *ptr = &a;
```

| Expression | Meaning                                |
| ---------- | -------------------------------------- |
| `a`        | Value of variable                      |
| `&a`       | Address of variable                    |
| `ptr`      | Address stored in pointer              |
| `*ptr`     | Value available at that address        |
| `&ptr`     | Address of the pointer variable itself |

Example:

```
#include <stdio.h>

int main() {

    int a = 100;

    int *ptr = &a;

    printf("a = %d\n", a);
    printf("&a = %p\n", (void *)&a);
    printf("ptr = %p\n", (void *)ptr);
    printf("*ptr = %d\n", *ptr);
    printf("&ptr = %p\n", (void *)&ptr);

    return 0;
}
```

# 9. Pointer Arithmetic

Pointers support arithmetic operations.

We can perform:

- Increment (`ptr++`)
- Decrement (`ptr--`)
- Addition (`ptr + n`)
- Subtraction (`ptr - n`)
- Difference between two pointers into the same array.

### Important concept

When we increment an integer pointer, it moves to the next integer element, not necessarily just one byte.

For example, if an integer occupies 4 bytes:

- Address: 1000
- After `ptr++`: 1004
- After another `ptr++`: 1008

The exact addresses depend on the platform and are illustrative.

Program:

```
#include <stdio.h>

int main() {

    int a = 10;

    int *ptr = &a;

    printf("Address before increment: %p\n", (void *)ptr);

    ptr++;

    printf("Address after increment: %p\n", (void *)ptr);

    return 0;
}
```

Important: In this example, `ptr++` moves beyond the single variable `a`. Do not dereference that resulting pointer. Pointer arithmetic is safely useful within an array and one position past its end.

# 10. Pointers and Arrays

Arrays and pointers are closely related in C.

Consider:

```
int arr[5] = {10, 20, 30, 40, 50};
```

The array name `arr` converts to a pointer to its first element in most expressions.

```
arr
```

Represents the address of the first element in this context.

```
&arr[0]
```

Also represents the address of the first element.

Therefore:

```
*arr
```

Accesses the first element.

### Example program

```
#include <stdio.h>

int main() {

    int arr[5] = {10, 20, 30, 40, 50};

    int *ptr = arr;

    printf("First element: %d\n", *ptr);

    printf("Second element: %d\n", *(ptr + 1));

    printf("Third element: %d\n", *(ptr + 2));

    return 0;
}
```

Output:

```
First element: 10
Second element: 20
Third element: 30
```

### Important relationship

| Array expression | Pointer equivalent |
| ---------------- | ------------------ |
| `arr[0]`         | `*(arr + 0)`       |
| `arr[1]`         | `*(arr + 1)`       |
| `arr[2]`         | `*(arr + 2)`       |
| `arr[i]`         | `*(arr + i)`       |

# 11. Print Array Elements Using Pointers

Question: Write a C program to read five integer values into an array and display them using a pointer.

```
#include <stdio.h>

int main() {

    int arr[5];

    int *ptr = arr;

    int i;

    printf("Enter 5 numbers:\n");

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

Output:

```
Enter 5 numbers:
10 20 30 40 50

Array Elements:
10 20 30 40 50
```

# 12. Pointers and Functions

Pointers allow functions to modify original variables.

Normally, C passes function arguments by value, meaning the function receives a copy.

But if we pass an address, the function can access and modify the original variable through a pointer.

### Example: Swap Two Numbers Using Pointers

Question: Write a C program to swap two numbers using a function and pointers.

```
#include <stdio.h>

void swap(int *a, int *b) {

    int temp;

    temp = *a;

    *a = *b;

    *b = temp;
}

int main() {

    int x = 10;
    int y = 20;

    printf("Before swapping:\n");

    printf("x = %d\n", x);
    printf("y = %d\n", y);

    swap(&x, &y);

    printf("\nAfter swapping:\n");

    printf("x = %d\n", x);
    printf("y = %d\n", y);

    return 0;
}
```

Output:

```
Before swapping:
x = 10
y = 20

After swapping:
x = 20
y = 10
```

### Explanation

```
swap(&x, &y);
```

We send the addresses of `x` and `y`.

```
void swap(int *a, int *b)
```

The function receives those addresses.

```
temp = *a;
*a = *b;
*b = temp;
```

These statements swap the values stored at those addresses.

Where is this used?

Sorting algorithms, modifying arrays through functions, and updating original records.

# 13. Pointer to Pointer

A pointer can also store the address of another pointer. This is called a pointer to pointer.

Syntax:

```
int **ptr;
```

Example:

```
#include <stdio.h>

int main() {

    int a = 100;

    int *p = &a;

    int **pp = &p;

    printf("Value of a: %d\n", a);

    printf("Using pointer: %d\n", *p);

    printf("Using pointer to pointer: %d\n", **pp);

    return 0;
}
```

Output:

```
Value of a: 100
Using pointer: 100
Using pointer to pointer: 100
```

### Understand the relationship

`pp` – Pointer to pointer

Stores address of p

`p` – Pointer

Stores address of a

`a` – Normal variable

# 100

Stores the actual integer value

- `p` points to `a`.
- `pp` points to `p`.
- `*p` gives `100`.
- `**pp` also gives `100`.

# 14. NULL Pointer

A NULL pointer is a pointer that does not point to a valid object.

Example:

```
#include <stdio.h>

int main() {

    int *ptr = NULL;

    if(ptr == NULL) {

        printf("Pointer is NULL\n");
    }

    return 0;
}
```

Output:

```
Pointer is NULL
```

Why do we use NULL?

- To initialize a pointer that does not yet point to an object.
- To represent the absence of a valid object.
- To check whether a pointer has been assigned a valid address.

Never dereference a NULL pointer:

```
*ptr = 10;  // Invalid when ptr is NULL
```

# 15. Void Pointer

A void pointer is a generic pointer that can hold the address of an object of any data type.

Syntax:

```
void *ptr;
```

Example:

```
#include <stdio.h>

int main() {

    int a = 100;

    float b = 25.5;

    void *ptr;

    ptr = &a;

    printf("Integer: %d\n", *(int *)ptr);

    ptr = &b;

    printf("Float: %.2f\n", *(float *)ptr);

    return 0;
}
```

Output:

```
Integer: 100
Float: 25.50
```

Explanation:

- `void *ptr` can hold an object address without specifying its type.
- Before dereferencing, we convert it to the correct pointer type.
- A void pointer cannot be directly dereferenced in standard C.

# 16. Pointer to Structure

We already studied structures. Now we can connect structures with pointers.

Consider:

```
struct Student {
    int roll;
    float marks;
};
```

A pointer can store the address of a structure variable.

Example:

```
#include <stdio.h>

struct Student {
    int roll;
    float marks;
};

int main() {

    struct Student s = {101, 90.5};

    struct Student *ptr = &s;

    printf("Roll Number: %d\n", ptr->roll);

    printf("Marks: %.2f\n", ptr->marks);

    return 0;
}
```

Output:

```
Roll Number: 101
Marks: 90.50
```

Remember:

```
(*ptr).roll
```

and

```
ptr->roll
```

Both access the same structure member.

# 17. Common Pointer Mistakes

| Mistake                                          | Problem                          | Correct approach                             |
| ------------------------------------------------ | -------------------------------- | -------------------------------------------- |
| Uninitialized pointer                            | May point anywhere               | Initialize it with a valid address or `NULL` |
| Dereferencing NULL                               | Undefined behavior               | Check before dereferencing                   |
| Wrong pointer type                               | Incorrect interpretation of data | Use the matching pointer type                |
| Using an address after object lifetime ends      | Dangling pointer                 | Ensure the object remains alive              |
| Accessing outside array bounds                   | Undefined behavior               | Stay within valid array elements             |
| Forgetting `&` in `scanf` for ordinary variables | Invalid argument                 | Pass the variable's address                  |

Important safety rule: Never dereference an uninitialized, NULL, dangling, or otherwise invalid pointer.

# 18. Important Viva Questions

1. What is a pointer?
2. Why do we use pointers in C?
3. What is the address-of operator?
4. What is the dereference operator?
5. How do you declare an integer pointer?
6. What is the difference between `ptr` and `*ptr`?
7. What is a NULL pointer?
8. What is a void pointer?
9. What is a pointer to pointer?
10. What is pointer arithmetic?
11. What is the relationship between arrays and pointers?
12. Can a pointer modify an original variable?
13. What is a dangling pointer?
14. What is a wild pointer?
15. What is the difference between an array and a pointer?

# 19. Quick Knowledge Test

Pointers MCQ Test

0/7 answered

1\. What does the & operator return?

Value of variable

Address of variable

Size of variable

Pointer value



2\. What does \*ptr return when ptr is valid?

Address of ptr

Value at the pointed location

Size of pointer

Variable name



3\. Which declaration creates an integer pointer?

int ptr;

pointer int ptr;

int \*ptr;

int &ptr;



4\. What is the output of this code: int a=20; int \*p=&a; printf("%d",\*p);

Address of a

0

20

Compilation error



5\. Which pointer represents no valid object?

NULL pointer

Void pointer

Integer pointer

Double pointer



6\. What does \*\*pp mean for a valid int pointer-to-pointer?

Address of pp

Value pointed to by the pointer pointed to by pp

Size of pp

Invalid syntax



7\. What happens when an integer pointer is incremented within an array?

Moves by one byte always

Moves to the next integer element

Becomes NULL

Moves backwards



Submit test

# 20. Recommended Teaching Sequence

For your first-year B.Tech students, teach pointers in this order:

| Class | Topics                                                                    |
| ----- | ------------------------------------------------------------------------- |
| 1     | Memory addresses, `&`, `*`, pointer declaration                           |
| 2     | Pointer initialization and dereferencing                                  |
| 3     | Modifying values through pointers                                         |
| 4     | Pointer arithmetic                                                        |
| 5     | Pointers and arrays                                                       |
| 6     | Pointers and functions, swapping                                          |
| 7     | Pointer to pointer                                                        |
| 8     | NULL and void pointers                                                    |
| 9     | Pointers to structures                                                    |
| 10    | Dynamic memory allocation using `malloc`, `calloc`, `realloc`, and `free` |

My recommendation: Do not rush into pointer arithmetic or double pointers on the first day. Make sure students can explain these three expressions confidently:

```
a       // Value
&a      // Address
*ptr    // Value at the address stored in ptr
```

Once they understand these, the remaining pointer concepts become much easier.

The next step in this topic is 30 hands-on Pointer Programs in C, divided into three batches of 10, following the same format as the structures practice.

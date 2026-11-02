# 2.3 ARRAYS

Array is a linear data structure that groups elements of similar types and stores them at contiguous memory locations. The concept of arrays can be easily related with real-life scenarios. For example, percentage marks of 50 students, salary amounts of 100 employees and names of books present in a library are all examples of arrays.

Each element in an array is assigned an index number called array subscript. It is used to identify the location of element in the array. In C language, the index number of the base element (first element) of an array starts with 0. Therefore, the location of the last element of an array containing n elements is always n-1. An array is referred using the array name defined at the time of array declaration. Each individual array element is referred using array name and index number.

Let us consider an array A containing four elements. Figure 2.7 shows the logical representation of array A:

Array A

\|  |  |  |  | |---|---|---|---| | Index | 0 | 1 | 2 | 3 |

Fig. 2.7 Logical representation of array

Some of the typical operations performed on arrays include:

1. Insertion Inserts an element into the array.
2. Deletion Deletes an element from the array.
3. Traversal Accesses each element of the array.
4. Sort Rearranges the array elements in a specific order, such as ascending or descending.
5. Search Searches a key value in the array.

Note

For more information on array operations, refer to Chapter 4.

C supports the following types of arrays:

1. Single-dimensional arrays Represent elements of the array in a single column. The array A shown in Figure 2.7 is an instance of single-dimensional array.
2. Multi-dimensional arrays Represent elements of an array in multiple columns and rows. A multi-dimensional array is also referred as array of arrays. Such arrays are commonly used to realize the mathematical concept of matrices.

Before an array can be used in a program, it needs to be first declared and initialized. You can initialize an array either at the time of its declaration or initialize it later in the program with the help of assignment operator.

The subsequent sections explain the declaration and initialization of single and multi-dimensional arrays along with related syntax and examples.

## 2.3.1 Single-Dimensional Array

### Array Declaration

Syntax

```
<data-type> <array_name>[size];
```

Example

```
int A[10];
```

### Array Initialization

Syntax

```
<data-type> <array_name>[size] = {element1, element2, ...., elementn};
<array_name>[index_number] = <element>;
```

Example

```
int A[3]={2,4,8};
A[0]=2;
```

### Array size (in bytes)

The size of a single-dimensional array can be calculated by using the following formula:

```
array size = length of array * size of data type
```

Example

Consider the following array:

```
int A[4] = {10, 20, 30, 40};
```

Here, size of array A = 4 \* 2 = 8 bytes.

### Array Representation

Figure 2.8 shows the logical representation of single-dimensional array.

| A[i]           | A[0] | A[1] | A[2] | A[3] |
| -------------- | ---- | ---- | ---- | ---- |
|                | 10   | 20   | 30   | 40   |
| Memory address | b    | b+2  | b+4  | b+6  |

Fig. 2.8 Logical representation of single-dimensional array

Example 2.7 Using single-dimensional array, write a program to find the average of 10 numbers.

Program 2.7 To find average of 10 numbers

```
#include <stdio.h>
#include <conio.h>

void main()
{
    int a[10], sum, i;
    float ave;
    clrscr();

    printf("Enter ten integers: ");
    for(i=0;i<=9;i++)
    scanf("%d",&a[i]);

    sum=0;

    for(i=0;i<=9;i++)
    sum=sum+a[i];

    ave=1.0*sum/10;

    /*Displaying the results*/
    printf("\nAverage = %.2f",ave);
    getch();
}
```

Output

```
Enter ten integers:
1
2
3
4
5
6
7
8
9
10

Average = 5.50
```

Program analysis

| Key Statement      | Purpose                                                  |
| ------------------ | -------------------------------------------------------- |
| int a[10], sum, i; | Declares a 10-element array a along with other variables |
| scanf(“%d”,&a[i]); | Reads an array element value                             |

## 2.3.2 Multi-Dimensional Array

### Array Declaration

Syntax

```
<data-type> <array_name>[row-subscript][column-subscript];
```

Example

```
int A[2][2];
```

### Array Initialization

Syntax

```
<array_name> [row-index_number][column-index_number] = <element>;
<data-type> <array_name>[row-subscript][column-subscript] =
{element1, element2, ...., elementn};
```

Example

```
A[1][0]=3;
int A[2][2] = {1,2,3,4};
```

The above declaration statement initializes array A in the following manner:

```
A[0][0]=1
A[0][1]=2
A[1][0]=3
A[1][1]=4 */
```

### Array size (in bytes)

The size of a multi-dimensional array can be calculated by using the following formula:

```
array size = row-size * column-size * size of data type
```

Example Consider the following array:

```
int A[2][2] = {10, 20, 30, 40};
```

Here, size of array A = 2 \* 2 \* 2 = 8 bytes.

### Array Representation

Figure 2.9 shows the logical representation of multi-dimensional array.

| A[i][j]        | A[0][0] | A[0][1] | A[1][0] | A[1][1] |
| -------------- | ------- | ------- | ------- | ------- |
|                | 10      | 20      | 30      | 40      |
| Memory address | b       | b+2     | b+4     | b+6     |

Fig. 2.9 Logical representation of multi-dimensional array

Example 2.8 Using multi-dimensional array, write a program to represent a 2 × 2 matrix.

Program 2.8 2 × 2 matrix

```
#include <stdio.h>
#include <conio.h>

void main()
{
    int i,j,M[2][2];
    clrscr();

    printf("Enter the elements of the 2 × 2 matrix:\n");
    for(i=0; i<2;i++)
        for(j=0; j<2;j++)
        {
            printf("\M[%d] [%d] = ", i, j);
            scanf("%d",& M[i][j]);
        }

    printf("The matrix represented by the 2 × 2 2D array is:\n");
    for(i=0; i<2; i++)
    {
        printf("\n\t\t ");
        for(j=0; j<2; j++)
            printf("%d ", M[i][j]);
    }

    getch();
}
```

Output

```
Enter the elements of the 2 × 2 matrix:
M[0][0] = 1
M[0][1] = 2
M[1][0] = 3
M[1][1] = 4
The matrix represented by the 2 × 2 2D array is:

            1    2
            3    4
```

Program analysis

| Key Statement          | Purpose                                                       |
| ---------------------- | ------------------------------------------------------------- |
| int i,j,M[2][2];       | Declares a two-dimensional array M along with other variables |
| scanf(“%d”,&M[i][j]);  | Reads an element value for a two-dimensional array            |
| printf(“%d ”,M[i][j]); | Displays an element value of a two-dimensional array          |


# 4.3 REPRESENTATION OF ONE-DIMENSIONAL ARRAY IN MEMORY

The elements of a one-dimensional array are stored at consecutive locations in memory. Each of the locations is accessed with the help of array index identifier to retrieve the corresponding element.

Consider the following integer array:

```
arr[5] = {2, 6, 7, 3, 8}
```

Here, arr is a five-element integer array. Figure 4.1 shows the representation of array arr in memory.

Fig. 4.1 – Array representation in memory

| Array Index     | arr[0] | arr[1] | arr[2] | arr[3] | arr[4] |
| --------------- | ------ | ------ | ------ | ------ | ------ |
| Value           | 2      | 6      | 7      | 3      | 8      |
| Memory Location | 6000   | 6002   | 6004   | 6006   | 6008   |

As shown in Fig. 4.1, each array element is stored at consecutive memory locations, i.e., 6000, 6002, 6004, and so on. The location of the first element, i.e., 6000 is also referred to as the base address of the array.

If we know the base address of an array, then we can find the location of its individual elements by using a simple formula, which is:

```
Address of A[k] = B + W * k
```

Here,

- A[ ] is the array.
- B is the base address, i.e., the address of the first element.
- W is the word size or the size of an array element.
- k is the index identifier.

For instance, the address of the third element of array arr stored at index location 2 would be:

```
Address of arr[2] = 6000 + 2 * 2
                  = 6000 + 4
                  = 6004
```

Note: The word size of a data type is decided by the programming language being used and the hardware specifications.

# 4.4 ARRAY TRAVERSAL

While working with arrays, it is often required to access the array elements; that is, reading values from the array. This is achieved with the help of array traversal. It involves visiting the array elements and storing or retrieving values from it. Some of the typical situations where array traversal may be required are:

- Printing array elements.
- Searching an element in the array.
- Sorting an array, and so on.

Check Point

1. What is a base address?

   Ans. It is the memory address of the first element of an array.
2. How are array elements stored in memory?

   Ans. The elements of an array are stored at consecutive locations in memory.

Mind Jog

What is 'array index out of bound'?

It is a runtime error that is encountered when a program tries to reference an address location outside of the defined array limits.

## Algorithm

Example 4.1 Write an algorithm to sequentially traverse an array.

```
traverse(arr[], size)

Step 1: Start
Step 2: Set i = 0
Step 3: Repeat Steps 4–5 while i < size
Step 4: Access arr[i]
Step 5: Set i = i + 1
Step 6: Stop
```

## Program

Example 4.2 Write a C program to traverse each element of an array and print its value on the console.

Program 4.1 performs array traversal and prints the array elements as output. It uses the algorithm depicted in Example 4.1.

Program 4.1 – C program to traverse each element of an array and print its value

```
#include <stdio.h>
#include <conio.h>

void traverse(int*, int); /*Function prototype for array traversal*/

void main()
{
    int arr[5] = {2, 6, 7, 3, 8};
    int N = 5;
    clrscr();

    printf("Press any key to perform array traversal and display its elements:\n\n");
    getch();

    traverse(arr, N); /*Calling traverse function*/

    getch();
}

void traverse(int *array, int size)
{
    int i;
    for(i=0; i<size; i++)
        printf("arr[%d] = %d\n", i, array[i]); /*Accessing array element and printing it*/
}
```

Important observations:

1. `int arr[5] = {2, 6, 7, 3, 8};` initializes the array at the time of declaration. This is referred to as compile-time initialization.
2. `void traverse(int*, int);` declares the function prototype.
3. `traverse(arr, N);` calls the traversal function.
4. `int *array` receives the base address of the array.
5. `for(i=0; i<size; i++)` accesses every element sequentially.
6. `array[i]` retrieves the value at the specified index.



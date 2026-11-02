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


## Output

```
Press any key to perform array traversal and display its elements:

arr[0] = 2

arr[1] = 6

arr[2] = 7

arr[3] = 3

arr[4] = 8
```

## Program analysis

| Key Statement               | Purpose                                                                              |
| --------------------------- | ------------------------------------------------------------------------------------ |
| `void traverse(int*, int);` | Declares the prototype for the `traverse()` function for traversing an array         |
| `traverse(arr,N);`          | Calls the `traverse()` function for traversing the array `arr` containing N elements |
| `for(i=0;i<size;i++)`       | Uses the for loop to access the array elements with each iteration                   |

Tip: While traversing an array, the index identifier should be updated carefully so that array out of bound situation does not arise. In this situation, the program tries to access a location outside of the reserved memory block, which is an illegal operation.

# 4.5 INSERTION AND DELETION

Insertion is the task of adding an element into an existing array while deletion is the task of removing an element from the array. The point of insertion or deletion that is the position where an element is to be inserted or deleted holds vital importance, as we shall see in the subsequent sections.

## 4.5.1 Insertion

If an element is to be inserted at the end of the array, then it can be simply achieved by storing the new element one position to the right of the last element. However, the array must have vacant positions at the end for this to be feasible. Alternatively, if an element is required to be inserted at the middle, then this will require all the subsequent elements to be moved one place to the right. Figure 4.2 depicts the insertion of an element into an array.

Check Point

1. What is array traversal?

   Ans. It is the task of visiting the array elements and storing or retrieving values from it.
2. What is the need for array traversal?

   Ans. It is required in almost all array related operations, such as sorting, searching, printing, etc.

[Array Data Structure - Types, Applications, Implementation](https://images.openai.com/static-rsc-4/uVcuSiR0nvx2ZSMR08MGs5pNjO4ysMtb1N2yQnytuUCdtUKEuRDS5xvlCO4i1ivgwy0lHygJHcWTz2CMuv40PWooF0k4GeG8hoHwoA5rFsiDv6P-pW6Vivtxu8HUfuuwvoAv2w4nVD65819zNscV89facnZgVEmg_Hc-QOPx7f4?purpose=inline)

[masaischool.com](https://www.masaischool.com/blog/array-data-structure-explained-with-examples/?utm_source=chatgpt.com)

Fig. 4.2 – Array insertion

## Algorithm

Example 4.3 Write an algorithm to perform array insertion.

The following algorithm inserts an element P at index location k in the array A[N], where k= k\
Step 4: Set A[i+1] = A[i]\
Step 5: Set i = i - 1\
Step 6: Set A[k] = P\
Step 7: Set N = N + 1\
Step 8: Stop

````

## Program

**Example 4.4** Write a C program to perform array insertion.

Program 4.2 performs array insertion and prints the updated array elements as output. It uses the algorithm depicted in Example 4.3.

**Program 4.2 – Array insertion**

```c
#include <stdio.h>
#include <conio.h>

void main()
{
    int array[10] = {-1, 3, 5, 22, 77};

    int i, k, N, P;
    clrscr();

    N = 5;

    printf("The contents of the array are:\n");
    for(i=0;i<N;i++)
        printf("array[%d] = %d\n",i,array[i]); /*Printing array elements*/

    printf("\nEnter the element to be inserted:\n");
    scanf("%d",&P);

    printf("\nEnter the index location where %d is to be inserted:\n", P);
    scanf("%d",&k);

    for(i=N;i>=k;i--)
        array[i+1]=array[i];

    array[k] = P;
    N = N + 1;

    printf("\nThe contents of the array after array insertion are:\n");
    for(i=0;i<N;i++)
        printf("array[%d] = %d\n",i,array[i]); /*Printing array elements after array insertion*/

    getch();
}
````

## Output

```
The contents of the array are:
array[0] = -1
array[1] = 3
array[2] = 5
array[3] = 22
array[4] = 77

Enter the element to be inserted:
19

Enter the index location where 19 is to be inserted:
1

The contents of the array after array insertion are:
array[0] = -1
array[1] = 19
array[2] = 3
array[3] = 5
array[4] = 22
array[5] = 77
```

Important explanation of insertion:

When inserting an element at a particular index:

1. Start from the last existing element.
2. Move each element one position to the right.
3. Continue until the required index is reached.
4. Insert the new element at that index.
5. Increase the array's logical size by 1.


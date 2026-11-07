# C Programming: Arrays — Programs 1–10

## Program 1: Read and Display Array Elements

Question: Write a C program to read 5 integers into an array and display all the elements.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Array elements are:\n");

    for (int i = 0; i < 5; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
```

Expected Output:

```
Array elements are:
10 20 30 40 50
```

Why this is important: Introduces array declaration, indexing, input, and traversal using loops.

Where it is used: Storing and displaying student marks, product prices, employee IDs, and other collections of data.

## Program 2: Print Array Elements in Reverse Order

Question: Write a C program to read 5 integers and display them in reverse order.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Reverse order:\n");

    for (int i = 4; i >= 0; i--)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
```

Expected Output:

```
Reverse order:
50 40 30 20 10
```

Why this is important: Teaches reverse traversal and decrementing loop counters.

Where it is used: Displaying recent records first, processing data backward, and solving reversal problems.

## Program 3: Calculate the Sum of Array Elements

Question: Write a C program to calculate the sum of 5 integers stored in an array.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int sum = 0;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
        sum = sum + arr[i];
    }

    printf("Sum = %d", sum);

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
```

Expected Output:

```
Sum = 150
```

Why this is important: Demonstrates the accumulator pattern while traversing an array.

Where it is used: Calculating total marks, monthly expenses, sales revenue, and inventory quantities.

## Program 4: Find the Average of Array Elements

Question: Write a C program to read 5 integers and calculate their average.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int sum = 0;
    float average;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
        sum = sum + arr[i];
    }

    average = (float)sum / 5;

    printf("Average = %.2f", average);

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
70 80 90 60 100
```

Expected Output:

```
Average = 80.00
```

Why this is important: Combines arrays, loops, accumulation, and floating-point division.

Where it is used: Calculating average marks, average temperatures, average ratings, and business performance metrics.

## Program 5: Find the Largest Element in an Array

Question: Write a C program to find the largest number among 5 array elements.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    int largest = arr[0];

    for (int i = 1; i < 5; i++)
    {
        if (arr[i] > largest)
        {
            largest = arr[i];
        }
    }

    printf("Largest = %d", largest);

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
25 78 42 91 36
```

Expected Output:

```
Largest = 91
```

Why this is important: Teaches comparison-based searching and updating a maximum value.

Where it is used: Finding the highest marks, maximum salary, highest score, and most expensive product.

## Program 6: Find the Smallest Element in an Array

Question: Write a C program to find the smallest number among 5 array elements.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    int smallest = arr[0];

    for (int i = 1; i < 5; i++)
    {
        if (arr[i] < smallest)
        {
            smallest = arr[i];
        }
    }

    printf("Smallest = %d", smallest);

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
25 78 42 12 36
```

Expected Output:

```
Smallest = 12
```

Why this is important: Teaches minimum-value searching and comparison.

Where it is used: Finding the lowest price, minimum marks, shortest duration, and smallest measurement.

## Program 7: Count Even and Odd Elements

Question: Write a C program to count how many even and odd numbers are present in an array of 5 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int even = 0, odd = 0;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);

        if (arr[i] % 2 == 0)
        {
            even++;
        }
        else
        {
            odd++;
        }
    }

    printf("Even count = %d\n", even);
    printf("Odd count = %d", odd);

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 15 22 33 40
```

Expected Output:

```
Even count = 3
Odd count = 2
```

Why this is important: Combines array traversal, the modulus operator, conditional statements, and counters.

Where it is used: Classifying numerical data, analyzing records, and counting items that satisfy a condition.

## Program 8: Count Positive, Negative, and Zero Elements

Question: Write a C program to count the positive numbers, negative numbers, and zeros in an array of 6 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];
    int positive = 0, negative = 0, zero = 0;

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);

        if (arr[i] > 0)
        {
            positive++;
        }
        else if (arr[i] < 0)
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

Expected Input:

```
Enter 6 numbers:
10 -5 0 20 -8 0
```

Expected Output:

```
Positive = 2
Negative = 2
Zero = 2
```

Why this is important: Demonstrates how to classify array elements using multiple conditions.

Where it is used: Processing financial values, analyzing sensor readings, and categorizing numerical datasets.

## Program 9: Search for an Element in an Array

Question: Write a C program to search for a given number in an array of 5 integers. Display whether the number is found.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int key, found = 0;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Enter number to search: ");
    scanf("%d", &key);

    for (int i = 0; i < 5; i++)
    {
        if (arr[i] == key)
        {
            found = 1;
            break;
        }
    }

    if (found == 1)
    {
        printf("Element found");
    }
    else
    {
        printf("Element not found");
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
Enter number to search: 30
```

Expected Output:

```
Element found
```

Why this is important: Introduces linear search, one of the fundamental searching algorithms.

Where it is used: Searching for an ID, checking whether a value exists, and finding records in small collections.

## Program 10: Count Occurrences of a Given Element

Question: Write a C program to count how many times a given number appears in an array of 8 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[8];
    int key, count = 0;

    printf("Enter 8 numbers:\n");

    for (int i = 0; i < 8; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Enter number to count: ");
    scanf("%d", &key);

    for (int i = 0; i < 8; i++)
    {
        if (arr[i] == key)
        {
            count++;
        }
    }

    printf("Occurrences = %d", count);

    return 0;
}
```

Expected Input:

```
Enter 8 numbers:
10 20 10 30 10 40 20 10
Enter number to count: 10
```

Expected Output:

```
Occurrences = 4
```

Why this is important: Teaches frequency counting, which is different from searching because every matching element must be counted.

Where it is used: Counting repeated values, analyzing survey responses, finding product frequencies, and processing duplicate records.

## Key concepts covered in Programs 1–10

| Concept                | Programs |
| ---------------------- | -------- |
| Array input and output | 1        |
| Reverse traversal      | 2        |
| Sum and average        | 3, 4     |
| Largest and smallest   | 5, 6     |
| Conditional counting   | 7, 8     |
| Linear search          | 9        |
| Frequency counting     | 10       |

Important array rule: For an array declared as `int arr[5];`, the valid indices are `0` through `4`. Always ensure that the loop does not access an index outside the array bounds.

# C Programming: Arrays — Programs 11–20

## Program 11: Copy Elements from One Array to Another

Question: Write a C program to copy all elements of one array into another array.

Code:

```
#include <stdio.h>

int main()
{
    int a[5], b[5];

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &a[i]);
    }

    for (int i = 0; i < 5; i++)
    {
        b[i] = a[i];
    }

    printf("Copied array:\n");

    for (int i = 0; i < 5; i++)
    {
        printf("%d ", b[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
```

Expected Output:

```
Copied array:
10 20 30 40 50
```

Why this is important: Demonstrates copying elements using indices and loops.

Where it is used: Creating backup data, duplicating lists, and preparing data for further processing.

## Program 12: Count Elements Greater Than 50

Question: Write a C program to count how many elements in an array of 6 integers are greater than 50.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];
    int count = 0;

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 6; i++)
    {
        if (arr[i] > 50)
        {
            count++;
        }
    }

    printf("Count = %d", count);

    return 0;
}
```

Expected Input:

```
Enter 6 numbers:
25 60 75 40 90 30
```

Expected Output:

```
Count = 3
```

Why this is important: Teaches conditional counting and filtering.

Where it is used: Counting passing marks, high-value transactions, and records meeting a threshold.

## Program 13: Print Only Even Elements

Question: Write a C program to display only the even numbers present in an array of 6 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Even numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        if (arr[i] % 2 == 0)
        {
            printf("%d ", arr[i]);
        }
    }

    return 0;
}
```

Expected Input:

```
Enter 6 numbers:
11 20 35 42 50 63
```

Expected Output:

```
Even numbers:
20 42 50
```

Why this is important: Combines array traversal with a condition to select specific elements.

Where it is used: Filtering numerical data and extracting records that satisfy a rule.

## Program 14: Print Only Odd Elements

Question: Write a C program to display only the odd numbers present in an array of 6 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Odd numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        if (arr[i] % 2 != 0)
        {
            printf("%d ", arr[i]);
        }
    }

    return 0;
}
```

Expected Input:

```
Enter 6 numbers:
11 20 35 42 50 63
```

Expected Output:

```
Odd numbers:
11 35 63
```

Why this is important: Reinforces the modulus operator and conditional filtering.

Where it is used: Selecting odd-numbered positions, filtering data, and solving mathematical problems.

## Program 15: Find the Second Largest Distinct Element

Question: Write a C program to find the second largest distinct element in an array of 5 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int largest, second;
    int hasSecond = 0;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    largest = arr[0];

    for (int i = 1; i < 5; i++)
    {
        if (arr[i] > largest)
        {
            largest = arr[i];
        }
    }

    for (int i = 0; i < 5; i++)
    {
        if (arr[i] < largest)
        {
            if (!hasSecond || arr[i] > second)
            {
                second = arr[i];
                hasSecond = 1;
            }
        }
    }

    if (hasSecond)
    {
        printf("Second largest = %d", second);
    }
    else
    {
        printf("No second largest distinct element");
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 40 30 40 20
```

Expected Output:

```
Second largest = 30
```

Why this is important: Teaches multiple passes through an array, comparisons, and handling duplicate values.

Where it is used: Ranking scores, identifying runner-up values, and analyzing top-performing records.

## Program 16: Find the Position of an Element

Question: Write a C program to find the first position of a given number in an array of 5 integers. Display the position starting from 1.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int key, position = -1;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Enter number to search: ");
    scanf("%d", &key);

    for (int i = 0; i < 5; i++)
    {
        if (arr[i] == key)
        {
            position = i + 1;
            break;
        }
    }

    if (position != -1)
    {
        printf("Position = %d", position);
    }
    else
    {
        printf("Element not found");
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
Enter number to search: 40
```

Expected Output:

```
Position = 4
```

Why this is important: Explains the difference between an array's zero-based index and a human-readable position.

Where it is used: Locating records, finding product positions, and searching lists.

## Program 17: Replace All Occurrences of a Number

Question: Write a C program to replace every occurrence of a given number with another number in an array of 6 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];
    int oldValue, newValue;
    int count = 0;

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Enter number to replace: ");
    scanf("%d", &oldValue);

    printf("Enter replacement number: ");
    scanf("%d", &newValue);

    for (int i = 0; i < 6; i++)
    {
        if (arr[i] == oldValue)
        {
            arr[i] = newValue;
            count++;
        }
    }

    printf("Updated array:\n");

    for (int i = 0; i < 6; i++)
    {
        printf("%d ", arr[i]);
    }

    printf("\nReplacements = %d", count);

    return 0;
}
```

Expected Input:

```
Enter 6 numbers:
10 20 10 30 10 40
Enter number to replace: 10
Enter replacement number: 99
```

Expected Output:

```
Updated array:
99 20 99 30 99 40
Replacements = 3
```

Why this is important: Demonstrates updating array elements based on a condition.

Where it is used: Updating values in datasets, correcting records, and replacing codes in lists.

## Program 18: Calculate the Sum of Even Elements

Question: Write a C program to calculate the sum of all even elements in an array of 6 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];
    int sum = 0;

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 6; i++)
    {
        if (arr[i] % 2 == 0)
        {
            sum += arr[i];
        }
    }

    printf("Sum of even elements = %d", sum);

    return 0;
}
```

Expected Input:

```
Enter 6 numbers:
10 15 20 25 30 35
```

Expected Output:

```
Sum of even elements = 60
```

Why this is important: Combines filtering with the accumulator pattern.

Where it is used: Calculating totals for selected categories of data.

## Program 19: Calculate the Sum of Positive Elements

Question: Write a C program to calculate the sum of all positive elements in an array of 6 integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];
    int sum = 0;

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 6; i++)
    {
        if (arr[i] > 0)
        {
            sum += arr[i];
        }
    }

    printf("Sum of positive elements = %d", sum);

    return 0;
}
```

Expected Input:

```
Enter 6 numbers:
10 -5 20 0 -8 15
```

Expected Output:

```
Sum of positive elements = 45
```

Why this is important: Teaches how to calculate a total for elements that satisfy a condition.

Where it is used: Summing positive financial values, valid measurements, and selected records.

## Program 20: Check Whether Two Arrays Are Equal

Question: Write a C program to read two arrays of 5 integers and check whether their elements are equal in the same order.

Code:

```
#include <stdio.h>

int main()
{
    int a[5], b[5];
    int equal = 1;

    printf("Enter first array:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &a[i]);
    }

    printf("Enter second array:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &b[i]);
    }

    for (int i = 0; i < 5; i++)
    {
        if (a[i] != b[i])
        {
            equal = 0;
            break;
        }
    }

    if (equal == 1)
    {
        printf("Arrays are equal");
    }
    else
    {
        printf("Arrays are not equal");
    }

    return 0;
}
```

Expected Input:

```
Enter first array:
10 20 30 40 50
Enter second array:
10 20 30 40 50
```

Expected Output:

```
Arrays are equal
```

Why this is important: Teaches element-by-element comparison and early termination using `break`.

Where it is used: Comparing datasets, checking copied data, validating results, and testing algorithms.

## Key concepts covered in Programs 11–20

| Concept                            | Programs |
| ---------------------------------- | -------- |
| Copying arrays                     | 11       |
| Conditional counting and filtering | 12–14    |
| Second largest distinct element    | 15       |
| Searching for a position           | 16       |
| Updating array values              | 17       |
| Conditional sums                   | 18–19    |
| Comparing arrays                   | 20       |

## Program 21: Reverse an Array In Place

Question: Write a C program to reverse the elements of an array without using another array.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5], temp;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 5 / 2; i++)
    {
        temp = arr[i];
        arr[i] = arr[4 - i];
        arr[4 - i] = temp;
    }

    printf("Reversed array:\n");

    for (int i = 0; i < 5; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
```

Expected Output:

```
Reversed array:
50 40 30 20 10
```

Why this is important: Teaches swapping and modifying an array without allocating a second array.

Where it is used: Reversing sequences, manipulating lists, and interview problems involving in-place operations.

## Program 22: Insert an Element at a Given Position

Question: Write a C program to insert a number at a specified position in an array of five elements. Assume the array has enough capacity for the new element.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6] = {10, 20, 30, 40, 50};
    int position, value;

    printf("Enter position (1-6): ");
    scanf("%d", &position);

    printf("Enter value: ");
    scanf("%d", &value);

    if (position < 1 || position > 6)
    {
        printf("Invalid position");
        return 0;
    }

    for (int i = 5; i >= position; i--)
    {
        arr[i] = arr[i - 1];
    }

    arr[position - 1] = value;

    printf("Updated array:\n");

    for (int i = 0; i < 6; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter position (1-6): 3
Enter value: 25
```

Expected Output:

```
Updated array:
10 20 25 30 40 50
```

Why this is important: Demonstrates shifting elements to make room for a new value.

Where it is used: Inserting records into ordered lists, maintaining rankings, and implementing array-based lists.

## Program 23: Delete an Element from a Given Position

Question: Write a C program to delete an element at a specified position from an array of five elements.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5] = {10, 20, 30, 40, 50};
    int position;
    int n = 5;

    printf("Enter position to delete (1-5): ");
    scanf("%d", &position);

    if (position < 1 || position > n)
    {
        printf("Invalid position");
        return 0;
    }

    for (int i = position - 1; i < n - 1; i++)
    {
        arr[i] = arr[i + 1];
    }

    n--;

    printf("Updated array:\n");

    for (int i = 0; i < n; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter position to delete (1-5): 3
```

Expected Output:

```
Updated array:
10 20 40 50
```

Why this is important: Teaches how to remove an element by shifting the remaining elements to the left.

Where it is used: Removing records, deleting list items, and implementing array-based data structures.

## Program 24: Sort an Array in Ascending Order

Question: Write a C program to sort five integers in ascending order using Bubble Sort.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5], temp;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 4; i++)
    {
        for (int j = 0; j < 4 - i; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    printf("Ascending order:\n");

    for (int i = 0; i < 5; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
50 20 40 10 30
```

Expected Output:

```
Ascending order:
10 20 30 40 50
```

Why this is important: Introduces sorting and nested loops, both essential topics in data structures and algorithms.

Where it is used: Ranking scores, ordering prices, organizing records, and preparing data for searching.

## Program 25: Sort an Array in Descending Order

Question: Write a C program to arrange five integers from largest to smallest using Bubble Sort.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5], temp;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 4; i++)
    {
        for (int j = 0; j < 4 - i; j++)
        {
            if (arr[j] < arr[j + 1])
            {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }

    printf("Descending order:\n");

    for (int i = 0; i < 5; i++)
    {
        printf("%d ", arr[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
50 20 40 10 30
```

Expected Output:

```
Descending order:
50 40 30 20 10
```

Why this is important: Shows how changing the comparison condition changes the sorting order.

Where it is used: Displaying highest scores first, ranking products, and arranging records by value.

## Program 26: Merge Two Arrays

Question: Write a C program to combine two arrays of three elements each into a single array.

Code:

```
#include <stdio.h>

int main()
{
    int a[3], b[3], c[6];

    printf("Enter 3 elements for first array:\n");

    for (int i = 0; i < 3; i++)
    {
        scanf("%d", &a[i]);
    }

    printf("Enter 3 elements for second array:\n");

    for (int i = 0; i < 3; i++)
    {
        scanf("%d", &b[i]);
    }

    for (int i = 0; i < 3; i++)
    {
        c[i] = a[i];
    }

    for (int i = 0; i < 3; i++)
    {
        c[i + 3] = b[i];
    }

    printf("Merged array:\n");

    for (int i = 0; i < 6; i++)
    {
        printf("%d ", c[i]);
    }

    return 0;
}
```

Expected Input:

```
Enter 3 elements for first array:
10 20 30
Enter 3 elements for second array:
40 50 60
```

Expected Output:

```
Merged array:
10 20 30 40 50 60
```

Why this is important: Teaches copying data from multiple arrays into one array.

Where it is used: Combining datasets, joining lists of records, and merging results from different sources.

## Program 27: Find the Second Smallest Distinct Element

Question: Write a C program to find the second smallest distinct element in an array of five integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int smallest, second;
    int hasSecond = 0;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    smallest = arr[0];

    for (int i = 1; i < 5; i++)
    {
        if (arr[i] < smallest)
        {
            smallest = arr[i];
        }
    }

    for (int i = 0; i < 5; i++)
    {
        if (arr[i] > smallest)
        {
            if (!hasSecond || arr[i] < second)
            {
                second = arr[i];
                hasSecond = 1;
            }
        }
    }

    if (hasSecond)
    {
        printf("Second smallest = %d", second);
    }
    else
    {
        printf("No second smallest distinct element");
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 40 20 10 30
```

Expected Output:

```
Second smallest = 20
```

Why this is important: Develops comparison logic and teaches how to handle duplicate values.

Where it is used: Finding runner-up values, rankings, and statistical analysis.

## Program 28: Count Duplicate Occurrences of Each Element

Question: Write a C program to count how many times each distinct element appears in an array of five integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int visited[5] = {0};

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 5; i++)
    {
        if (visited[i] == 1)
        {
            continue;
        }

        int count = 1;

        for (int j = i + 1; j < 5; j++)
        {
            if (arr[i] == arr[j])
            {
                count++;
                visited[j] = 1;
            }
        }

        printf("%d occurs %d time(s)\n", arr[i], count);
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 10 30 20
```

Expected Output:

```
10 occurs 2 time(s)
20 occurs 2 time(s)
30 occurs 1 time(s)
```

Why this is important: Introduces nested loops, frequency counting, and tracking already-processed elements.

Where it is used: Detecting duplicates, analyzing survey responses, and finding the frequency of values in datasets.

## Program 29: Perform Linear Search and Display All Matching Positions

Question: Write a C program to find every position where a given number occurs in an array of six integers.

Code:

```
#include <stdio.h>

int main()
{
    int arr[6];
    int key, found = 0;

    printf("Enter 6 numbers:\n");

    for (int i = 0; i < 6; i++)
    {
        scanf("%d", &arr[i]);
    }

    printf("Enter number to search: ");
    scanf("%d", &key);

    for (int i = 0; i < 6; i++)
    {
        if (arr[i] == key)
        {
            printf("Found at position %d\n", i + 1);
            found = 1;
        }
    }

    if (found == 0)
    {
        printf("Element not found");
    }

    return 0;
}
```

Expected Input:

```
Enter 6 numbers:
10 20 10 30 10 40
Enter number to search: 10
```

Expected Output:

```
Found at position 1
Found at position 3
Found at position 5
```

Why this is important: Demonstrates searching for all matches rather than stopping at the first match.

Where it is used: Finding repeated IDs, locating duplicate records, and searching datasets.

## Program 30: Check Whether an Array Is Sorted

Question: Write a C program to check whether the elements of an array of five integers are in ascending order.

Code:

```
#include <stdio.h>

int main()
{
    int arr[5];
    int sorted = 1;

    printf("Enter 5 numbers:\n");

    for (int i = 0; i < 5; i++)
    {
        scanf("%d", &arr[i]);
    }

    for (int i = 0; i < 4; i++)
    {
        if (arr[i] > arr[i + 1])
        {
            sorted = 0;
            break;
        }
    }

    if (sorted == 1)
    {
        printf("Array is sorted in ascending order");
    }
    else
    {
        printf("Array is not sorted in ascending order");
    }

    return 0;
}
```

Expected Input:

```
Enter 5 numbers:
10 20 30 40 50
```

Expected Output:

```
Array is sorted in ascending order
```

Why this is important: Teaches comparison of adjacent elements and how to validate an array's ordering.

Where it is used: Checking sorted data before binary search, validating ordered records, and testing sorting algorithms.

## Summary: Arrays Programs 21–30

| Program | Concept                            |
| ------- | ---------------------------------- |
| 21      | Reverse an array in place          |
| 22      | Insert an element                  |
| 23      | Delete an element                  |
| 24      | Bubble Sort — ascending            |
| 25      | Bubble Sort — descending           |
| 26      | Merge two arrays                   |
| 27      | Second smallest distinct element   |
| 28      | Frequency of each distinct element |
| 29      | Find all matching positions        |
| 30      | Check whether an array is sorted   |

These 30 programs cover array traversal, searching, updating, insertion, deletion, sorting, merging, and frequency counting—important foundations for linked lists, stacks, queues, and other data structures.

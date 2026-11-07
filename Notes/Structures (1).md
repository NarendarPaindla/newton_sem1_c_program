# C Programming – Structures

<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/384ef1f8-04d0-44cf-9874-7ce302d0e969" />


## 1. What is a structure in C?

Definition: A structure is a user-defined data type in C that allows us to combine different types of data members under a single name.

### Real-time example: Student details

Imagine a college student record:

- Student name – Ravi
- Roll number – 101
- Age – 18
- Marks – 85.5

These details have different data types:

| Student detail | Data type    |
| -------------- | ------------ |
| Name           | `char` array |
| Roll number    | `int`        |
| Age            | `int`        |
| Marks          | `float`      |

How can we store all these related details together?

We can use a structure.

## 2. Why do we need structures?

Suppose we want to store details of three students.

Without structures:

```
#include <stdio.h>

int main()
{
    char name1[30] = "Ravi";
    int roll1 = 101;
    float marks1 = 85.5;

    char name2[30] = "Suresh";
    int roll2 = 102;
    float marks2 = 90.5;

    char name3[30] = "Priya";
    int roll3 = 103;
    float marks3 = 95.5;

    return 0;
}
```

As the number of students increases, managing separate variables becomes difficult.

With structures:

We can group all related information into one student record.

```
struct Student
{
    char name[30];
    int roll;
    float marks;
};
```

Now each student can be represented using a single structure variable.

## 3. Structure syntax

### General syntax

```
struct structure_name
{
    data_type member1;
    data_type member2;
    data_type member3;
};
```

Example:

```
struct Student
{
    char name[30];
    int roll;
    float marks;
};
```

Explanation:

| Component | Meaning                             |
| --------- | ----------------------------------- |
| `struct`  | Keyword used to declare a structure |
| `Student` | Structure name (tag)                |
| `name`    | Structure member                    |
| `roll`    | Structure member                    |
| `marks`   | Structure member                    |
| `;`       | Ends the structure declaration      |

Important: The structure declaration defines a type. It does not, by itself, create a student variable.

## 4. Declaring structure variables

After defining a structure, we can create variables using that structure.

```
struct Student
{
    char name[30];
    int roll;
    float marks;
};

int main()
{
    struct Student s1;
    struct Student s2;

    return 0;
}
```

Here:

- `Student` is the structure type.
- `s1` and `s2` are structure variables.
- Both variables have their own `name`, `roll` and `marks` members.

You can also declare variables immediately after the structure definition:

```
struct Student
{
    char name[30];
    int roll;
    float marks;
} s1, s2;
```

## 5. Accessing structure members using the dot operator (`.`)

The dot operator is used to access individual members of a structure variable.

Syntax:

```
structure_variable.member_name
```

Examples:

```
s1.roll = 101;
s1.marks = 85.5;
```

To access the name:

```
printf("%s", s1.name);
```
<img width="2048" height="1536" alt="image" src="https://github.com/user-attachments/assets/e5dceeb6-2a44-43b6-b90f-62d6eb3d3c39" />


## 6. First complete program – Read and display student details

Question: Write a C program to read and display a student's name, roll number and marks using a structure.

```
#include <stdio.h>

struct Student
{
    char name[30];
    int roll;
    float marks;
};

int main()
{
    struct Student s1;

    printf("Enter student name: ");
    scanf("%29s", s1.name);

    printf("Enter roll number: ");
    scanf("%d", &s1.roll);

    printf("Enter marks: ");
    scanf("%f", &s1.marks);

    printf("\nStudent Details\n");

    printf("Name = %s\n", s1.name);
    printf("Roll Number = %d\n", s1.roll);
    printf("Marks = %.2f\n", s1.marks);

    return 0;
}
```

Expected Output:

```
Enter student name: Ravi
Enter roll number: 101
Enter marks: 85.5

Student Details
Name = Ravi
Roll Number = 101
Marks = 85.50
```

Explain to students:

1. We created a structure named `Student`.
2. We declared a structure variable `s1`.
3. We accepted input into individual members.
4. We used the dot operator to access each member.
5. We displayed the complete student record.

## 7. Initializing structure variables

We can assign values to structure members at the time of declaring the variable.

```
#include <stdio.h>

struct Student
{
    char name[30];
    int roll;
    float marks;
};

int main()
{
    struct Student s1 = {"Ravi", 101, 85.5};

    printf("Name = %s\n", s1.name);
    printf("Roll = %d\n", s1.roll);
    printf("Marks = %.2f\n", s1.marks);

    return 0;
}
```

Output:

```
Name = Ravi
Roll = 101
Marks = 85.50
```

The values are assigned in the same order in which the members are declared.

## 8. Array of structures

Definition: An array of structures is a collection of structure variables of the same structure type.

### Real-time example

Imagine a college has 5 students. Each student has a name, roll number and marks.

Instead of declaring five separate structure variables, we can use an array of structures.

Syntax:

```
struct Student students[5];
```

<img width="1701" height="1551" alt="image" src="https://github.com/user-attachments/assets/075e3a6e-1c0f-4b93-8683-9fda6f85d3ed" />


### Program: Store and display details of five students

```
#include <stdio.h>

struct Student
{
    char name[30];
    int roll;
    float marks;
};

int main()
{
    struct Student s[5];
    int i;

    for (i = 0; i < 5; i++)
    {
        printf("\nEnter details of student %d\n", i + 1);

        printf("Enter name: ");
        scanf("%29s", s[i].name);

        printf("Enter roll number: ");
        scanf("%d", &s[i].roll);

        printf("Enter marks: ");
        scanf("%f", &s[i].marks);
    }

    printf("\n--- Student Records ---\n");

    for (i = 0; i < 5; i++)
    {
        printf("\nName = %s", s[i].name);
        printf("\nRoll = %d", s[i].roll);
        printf("\nMarks = %.2f\n", s[i].marks);
    }

    return 0;
}
```

Sample Output:

```
Enter details of student 1
Enter name: Ravi
Enter roll number: 101
Enter marks: 85

Enter details of student 2
Enter name: Priya
Enter roll number: 102
Enter marks: 90

--- Student Records ---

Name = Ravi
Roll = 101
Marks = 85.00

Name = Priya
Roll = 102
Marks = 90.00
```

Why is this important? It combines arrays and structures to manage multiple records.

Where is it used? College management systems, employee databases and library management systems.

## 9. Structure and functions

We can pass structure variables to functions just like ordinary variables.

There are two common approaches:

- Passing a structure variable by value.
- Passing the address of a structure variable using a pointer.

### Program: Pass a structure to a function

Question: Write a C program to read and display student details using separate functions.

```
#include <stdio.h>

struct Student
{
    char name[30];
    int roll;
    float marks;
};

void display(struct Student s)
{
    printf("\nStudent Details\n");
    printf("Name = %s\n", s.name);
    printf("Roll = %d\n", s.roll);
    printf("Marks = %.2f\n", s.marks);
}

int main()
{
    struct Student s1;

    printf("Enter name: ");
    scanf("%29s", s1.name);

    printf("Enter roll number: ");
    scanf("%d", &s1.roll);

    printf("Enter marks: ");
    scanf("%f", &s1.marks);

    display(s1);

    return 0;
}
```

Output:

```
Enter name: Ravi
Enter roll number: 101
Enter marks: 88

Student Details
Name = Ravi
Roll = 101
Marks = 88.00
```

Important explanation:

`display(s1)` passes a copy of the structure to the function. Changes made to that copy do not modify the original structure variable.

## 10. Pointer to a structure

Definition: A structure pointer is a pointer variable that stores the address of a structure variable.

Consider:

```
struct Student s1;
struct Student *ptr;

ptr = &s1;
```

Here:

- `s1` is a structure variable.
- `ptr` is a pointer to a structure.
- `&s1` gives the address of the structure variable.

### Accessing members using a structure pointer

There are two ways:

Using the dot operator with dereferencing:

```
(*ptr).roll
```

Using the arrow operator:

```
ptr->roll
```

Both expressions access the same member.

<img width="1200" height="800" alt="image" src="https://github.com/user-attachments/assets/55efadcf-fe42-4e0b-85bf-ae2cb1e64ea7" />


### Program: Access structure members using a pointer

```
#include <stdio.h>

struct Student
{
    char name[30];
    int roll;
    float marks;
};

int main()
{
    struct Student s1;
    struct Student *ptr;

    ptr = &s1;

    printf("Enter name: ");
    scanf("%29s", ptr->name);

    printf("Enter roll number: ");
    scanf("%d", &ptr->roll);

    printf("Enter marks: ");
    scanf("%f", &ptr->marks);

    printf("\nStudent Details\n");

    printf("Name = %s\n", ptr->name);
    printf("Roll = %d\n", ptr->roll);
    printf("Marks = %.2f\n", ptr->marks);

    return 0;
}
```

Output:

```
Enter name: Ravi
Enter roll number: 101
Enter marks: 90

Student Details
Name = Ravi
Roll = 101
Marks = 90.00
```

Why is this important? It connects structures with pointers and introduces the arrow operator.

Where is it used? Linked lists, trees, dynamic memory management and database record handling.

## 11. Nested structures

Definition: A structure declared as a member of another structure is called a nested structure.

### Real-time example

A student has:

- Name
- Roll number
- Date of birth

The date of birth itself contains:

- Day
- Month
- Year

We can create one structure inside another structure.

### Program: Store student details with date of birth

```
#include <stdio.h>

struct Date
{
    int day;
    int month;
    int year;
};

struct Student
{
    char name[30];
    int roll;
    struct Date dob;
};

int main()
{
    struct Student s1;

    printf("Enter student name: ");
    scanf("%29s", s1.name);

    printf("Enter roll number: ");
    scanf("%d", &s1.roll);

    printf("Enter date of birth (DD MM YYYY): ");
    scanf("%d %d %d",
          &s1.dob.day,
          &s1.dob.month,
          &s1.dob.year);

    printf("\nStudent Details\n");

    printf("Name = %s\n", s1.name);
    printf("Roll = %d\n", s1.roll);

    printf("Date of Birth = %02d-%02d-%04d",
           s1.dob.day,
           s1.dob.month,
           s1.dob.year);

    return 0;
}
```

Output:

```
Enter student name: Ravi
Enter roll number: 101
Enter date of birth (DD MM YYYY): 15 8 2007

Student Details
Name = Ravi
Roll = 101
Date of Birth = 15-08-2007
```

Why is this important? Students understand how complex records can be divided into smaller related structures.

Where is it used? Employee records, banking applications, address management and student databases.

## 12. `typedef` with structures

Definition: The `typedef` keyword creates an alternative name (alias) for an existing data type.

Normally, we declare a structure variable like this:

```
struct Student s1;
```

Using `typedef`, we can simplify it:

```
typedef struct
{
    char name[30];
    int roll;
    float marks;
} Student;
```

Now we can declare a variable like this:

```
Student s1;
```

### Complete program

```
#include <stdio.h>

typedef struct
{
    char name[30];
    int roll;
    float marks;
} Student;

int main()
{
    Student s1 = {"Ravi", 101, 85.5};

    printf("Name = %s\n", s1.name);
    printf("Roll = %d\n", s1.roll);
    printf("Marks = %.2f\n", s1.marks);

    return 0;
}
```

Output:

```
Name = Ravi
Roll = 101
Marks = 85.50
```

Why is this important? It makes structure declarations shorter and easier to read.

## 13. Difference between array and structure

This is an important examination question.

| Array                                        | Structure                                         |
| -------------------------------------------- | ------------------------------------------------- |
| Stores multiple values of the same data type | Groups members that can have different data types |
| Elements are accessed using indexes          | Members are accessed using member names           |
| Example: `int marks[5]`                      | Example: `struct Student`                         |
| Array elements are accessed using `arr[0]`   | Structure members are accessed using `s1.roll`    |
| Used for collections of similar values       | Used for related records                          |

Simple example:

An array can store five subject marks:

```
int marks[5] = {80, 90, 75, 85, 95};
```

A structure can store one student's complete details:

```
struct Student
{
    char name[30];
    int roll;
    float marks;
};
```

## 14. Difference between structure and union

Both structures and unions are user-defined data types, but their memory allocation is different.

[Sturctures In C by Logicmojo](https://images.openai.com/static-rsc-4/xOd4UwT7CCsg3u_0U9fi-giw8MiQ51ssnzyVsQis6oRWWeuMbhaSCO9ODEue_oJ3xJTEcKfWDp4iEzx2_8OgriS3I3fTltj-54G10x2EcGvYyMWW2gvqVofL8UI6DaErrsFUPuXij1Z712Z8JZ3zny5tSqg5Ha4U0jgQLTlIrVI?purpose=inline)

Structure

Each member has its own storage within the structure.

[Back to the basics - struct vs union :) | Piyush Itankar](https://images.openai.com/static-rsc-4/LH7ORKmurMPgK1xS9cXJH07-7fZhh726A_ePvReoqnC3Y-7WcAnfhXDYsWoeCyoDCztzhHn4vfjr72lQiuFr5IWrhlnvk12F-qwnjBpNgRy_h7A-zb3OVehrs6bixbXlMA4ak92niIlRYnGOj1uk372yJRbzyAZLAoGjy4N9jOY?purpose=inline)

Union

All members share the same memory region.

| Structure                                                  | Union                                                               |
| ---------------------------------------------------------- | ------------------------------------------------------------------- |
| Uses `struct` keyword                                      | Uses `union` keyword                                                |
| Each member has separate storage                           | Members share storage                                               |
| Members can hold values simultaneously                     | Only one member's stored value should be relied upon at a time      |
| Size is at least enough for all members, including padding | Size is at least enough for its largest member, including alignment |

### Example of structure

```
struct Data
{
    int a;
    float b;
    char c;
};
```

### Example of union

```
union Data
{
    int a;
    float b;
    char c;
};
```

Important: Do not assume that the size of a structure is always the sum of its member sizes. Compilers may add padding for alignment.

# 15. Common mistakes students should avoid

1. Forgetting the semicolon after the structure definition.
2. Using `.` incorrectly while accessing members.
3. Using `&` with a character array name in `scanf()` unnecessarily.
4. Forgetting to write `struct` when declaring a variable if no `typedef` alias exists.
5. Confusing structure variables with structure members.
6. Accessing a structure pointer using `.` instead of `->`.
7. Assuming that assigning one structure to another copies only one member. In fact, compatible structure assignments copy all members.
8. Confusing structures with arrays.

# 16. Viva questions

1. What is a structure in C?
2. Why do we use structures?
3. What is the purpose of the `struct` keyword?
4. What is a structure member?
5. How do we declare a structure variable?
6. What is the dot operator?
7. What is an array of structures?
8. Can a structure contain different data types?
9. Can we pass a structure to a function?
10. What is a pointer to a structure?
11. What is the arrow operator?
12. What is a nested structure?
13. What is the purpose of `typedef`?
14. What is the difference between an array and a structure?
15. What is the difference between a structure and a union?
16. Can one structure be a member of another structure?
17. Can a structure contain an array?
18. Can a structure contain a pointer?

# 17. Recommended practical teaching sequence

| Class | Topic                        | Practical activity                 |
| ----- | ---------------------------- | ---------------------------------- |
| 1     | Introduction and declaration | Create a student structure         |
| 2     | Accessing members            | Read and display student details   |
| 3     | Structure initialization     | Initialize employee details        |
| 4     | Array of structures          | Store five student records         |
| 5     | Structures with functions    | Pass student details to a function |
| 6     | Structure pointers           | Access members using `->`          |
| 7     | Nested structures            | Student details with date of birth |
| 8     | `typedef` and union          | Compare structure and union        |

My recommendation: Spend more time on array of structures and structure pointers. These concepts are especially useful when students later implement student management systems, linked lists and other data structures.

The next practice stage can be 30 hands-on C programs on structures, divided into three batches of 10, with complete code, sample input/output, why each program is important and where it is used.

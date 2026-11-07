# Structures in C – 30 Hands-on Programs

## Batch 1: Programs 1–10

These programs start with basic structure declaration and gradually introduce arrays of structures, calculations, searching, updating records, and functions.

## 1. Display Student Details Using Structure

Question: Write a C program to declare a structure named `Student` with name, roll number, and marks. Initialize the values and display the student details.

Concept: Structure declaration and initialization.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s1 = {"Ravi", 101, 85.5};

    printf("Student Details\n");
    printf("Name: %s\n", s1.name);
    printf("Roll Number: %d\n", s1.roll);
    printf("Marks: %.2f\n", s1.marks);

    return 0;
}
```

Expected Output:

```
Student Details
Name: Ravi
Roll Number: 101
Marks: 85.50
```

Why is this important?

It introduces how a structure stores different types of information together.

Where is it used?

Student management systems, employee databases, and college admission systems.

## 2. Read and Display Student Details

Question: Write a C program to read a student's name, roll number, and marks from the user and display them using a structure.

Concept: Reading and accessing structure members using the dot (`.`) operator.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s1;

    printf("Enter student name: ");
    scanf("%29s", s1.name);

    printf("Enter roll number: ");
    scanf("%d", &s1.roll);

    printf("Enter marks: ");
    scanf("%f", &s1.marks);

    printf("\nStudent Details\n");

    printf("Name: %s\n", s1.name);
    printf("Roll Number: %d\n", s1.roll);
    printf("Marks: %.2f\n", s1.marks);

    return 0;
}
```

Expected Output:

```
Enter student name: Kiran
Enter roll number: 102
Enter marks: 92.5

Student Details
Name: Kiran
Roll Number: 102
Marks: 92.50
```

Why is this important?

Students learn how to accept user input directly into structure members.

Where is it used?

Student registration forms and employee information systems.

## 3. Store and Display Details of 5 Students

Question: Write a C program to store the details of five students using an array of structures and display all their details.

Concept: Array of structures.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s[5];

    int i;

    for(i = 0; i < 5; i++) {

        printf("\nEnter details of student %d\n", i + 1);

        printf("Enter name: ");
        scanf("%29s", s[i].name);

        printf("Enter roll number: ");
        scanf("%d", &s[i].roll);

        printf("Enter marks: ");
        scanf("%f", &s[i].marks);
    }

    printf("\nAll Student Details\n");

    for(i = 0; i < 5; i++) {

        printf("\nStudent %d\n", i + 1);

        printf("Name: %s\n", s[i].name);
        printf("Roll Number: %d\n", s[i].roll);
        printf("Marks: %.2f\n", s[i].marks);
    }

    return 0;
}
```

Expected Output (sample):

```
Enter details of student 1
Enter name: Ravi
Enter roll number: 101
Enter marks: 85

Enter details of student 2
Enter name: Kiran
Enter roll number: 102
Enter marks: 90

...

All Student Details

Student 1
Name: Ravi
Roll Number: 101
Marks: 85.00

Student 2
Name: Kiran
Roll Number: 102
Marks: 90.00
```

Why is this important?

It demonstrates how to manage multiple records using one structure definition.

Where is it used?

College student databases, school management systems, and examination records.

## 4. Calculate Total and Average Marks of a Student

Question: Write a C program to store a student's name, roll number, and marks in three subjects using a structure. Calculate and display the total and average marks.

Concept: Structure members with calculations.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float m1, m2, m3;
};

int main() {

    struct Student s;

    float total, average;

    printf("Enter student name: ");
    scanf("%29s", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter marks in 3 subjects: ");
    scanf("%f %f %f", &s.m1, &s.m2, &s.m3);

    total = s.m1 + s.m2 + s.m3;

    average = total / 3;

    printf("\nStudent Details\n");

    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll);
    printf("Total Marks: %.2f\n", total);
    printf("Average Marks: %.2f\n", average);

    return 0;
}
```

Expected Output:

```
Enter student name: Ravi
Enter roll number: 101
Enter marks in 3 subjects: 80 90 85

Student Details
Name: Ravi
Roll Number: 101
Total Marks: 255.00
Average Marks: 85.00
```

Why is this important?

It combines structure members with arithmetic operations.

Where is it used?

Student result processing and academic performance tracking.

## 5. Find the Student Who Scored the Highest Marks

Question: Write a C program to read the details of five students and display the student who obtained the highest marks.

Concept: Array of structures and comparison.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s[5];

    int i, highest = 0;

    for(i = 0; i < 5; i++) {

        printf("\nEnter student %d details\n", i + 1);

        printf("Enter name: ");
        scanf("%29s", s[i].name);

        printf("Enter roll number: ");
        scanf("%d", &s[i].roll);

        printf("Enter marks: ");
        scanf("%f", &s[i].marks);
    }

    for(i = 1; i < 5; i++) {

        if(s[i].marks > s[highest].marks) {
            highest = i;
        }
    }

    printf("\nTopper Details\n");

    printf("Name: %s\n", s[highest].name);
    printf("Roll Number: %d\n", s[highest].roll);
    printf("Marks: %.2f\n", s[highest].marks);

    return 0;
}
```

Expected Output (sample):

```
Enter student 1 details
Enter name: Ravi
Enter roll number: 101
Enter marks: 80

Enter student 2 details
Enter name: Kiran
Enter roll number: 102
Enter marks: 95

...

Topper Details
Name: Kiran
Roll Number: 102
Marks: 95.00
```

Why is this important?

It teaches how to compare structure members across multiple records.

Where is it used?

College topper lists, merit lists, and examination result systems.

## 6. Search for a Student Using Roll Number

Question: Write a C program to store five student records and search for a student using their roll number.

Concept: Searching in an array of structures.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s[5];

    int i, searchRoll, found = 0;

    for(i = 0; i < 5; i++) {

        printf("\nEnter student %d details\n", i + 1);

        printf("Enter name: ");
        scanf("%29s", s[i].name);

        printf("Enter roll number: ");
        scanf("%d", &s[i].roll);

        printf("Enter marks: ");
        scanf("%f", &s[i].marks);
    }

    printf("\nEnter roll number to search: ");
    scanf("%d", &searchRoll);

    for(i = 0; i < 5; i++) {

        if(s[i].roll == searchRoll) {

            printf("\nStudent Found!\n");

            printf("Name: %s\n", s[i].name);
            printf("Roll Number: %d\n", s[i].roll);
            printf("Marks: %.2f\n", s[i].marks);

            found = 1;
            break;
        }
    }

    if(found == 0) {
        printf("Student not found.\n");
    }

    return 0;
}
```

Expected Output (sample):

```
Enter roll number to search: 102

Student Found!
Name: Kiran
Roll Number: 102
Marks: 95.00
```

Why is this important?

It demonstrates how to retrieve a particular record from a collection of records.

Where is it used?

Searching student records using hall ticket numbers or employee records using employee IDs.

## 7. Update Student Marks

Question: Write a C program to read a student's details and update their marks with a new value.

Concept: Modifying structure members.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s;

    printf("Enter student name: ");
    scanf("%29s", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter current marks: ");
    scanf("%f", &s.marks);

    printf("\nBefore Updating\n");

    printf("Name: %s\n", s.name);
    printf("Marks: %.2f\n", s.marks);

    printf("\nEnter new marks: ");
    scanf("%f", &s.marks);

    printf("\nAfter Updating\n");

    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll);
    printf("Updated Marks: %.2f\n", s.marks);

    return 0;
}
```

Expected Output:

```
Enter student name: Ravi
Enter roll number: 101
Enter current marks: 75

Before Updating
Name: Ravi
Marks: 75.00

Enter new marks: 90

After Updating
Name: Ravi
Roll Number: 101
Updated Marks: 90.00
```

Why is this important?

It explains that structure members can be modified after assigning values.

Where is it used?

Updating examination marks, employee details, and customer information.

## 8. Employee Salary Calculation Using Structure

Question: Write a C program to store employee ID, employee name, and monthly salary using a structure. Calculate and display the annual salary.

Concept: Structure with salary calculations.

C Program:

```
#include <stdio.h>

struct Employee {
    int id;
    char name[30];
    float salary;
};

int main() {

    struct Employee e;

    float annualSalary;

    printf("Enter employee ID: ");
    scanf("%d", &e.id);

    printf("Enter employee name: ");
    scanf("%29s", e.name);

    printf("Enter monthly salary: ");
    scanf("%f", &e.salary);

    annualSalary = e.salary * 12;

    printf("\nEmployee Details\n");

    printf("Employee ID: %d\n", e.id);
    printf("Employee Name: %s\n", e.name);
    printf("Monthly Salary: %.2f\n", e.salary);
    printf("Annual Salary: %.2f\n", annualSalary);

    return 0;
}
```

Expected Output:

```
Enter employee ID: 501
Enter employee name: Rahul
Enter monthly salary: 30000

Employee Details
Employee ID: 501
Employee Name: Rahul
Monthly Salary: 30000.00
Annual Salary: 360000.00
```

Why is this important?

It demonstrates how structures can represent real-world entities.

Where is it used?

Payroll management systems and employee databases.

## 9. Store Student Date of Birth Using Nested Structure

Question: Write a C program to store a student's name, roll number, and date of birth using nested structures.

Concept: Nested structures – one structure used as a member inside another structure.

C Program:

```
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

struct Student {
    char name[30];
    int roll;
    struct Date dob;
};

int main() {

    struct Student s;

    printf("Enter student name: ");
    scanf("%29s", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter date of birth (DD MM YYYY): ");
    scanf("%d %d %d",
          &s.dob.day,
          &s.dob.month,
          &s.dob.year);

    printf("\nStudent Details\n");

    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll);

    printf("Date of Birth: %02d-%02d-%04d\n",
           s.dob.day,
           s.dob.month,
           s.dob.year);

    return 0;
}
```

Expected Output:

```
Enter student name: Ravi
Enter roll number: 101
Enter date of birth (DD MM YYYY): 15 08 2005

Student Details
Name: Ravi
Roll Number: 101
Date of Birth: 15-08-2005
```

Why is this important?

It teaches how complex information can be organized using nested structures.

Where is it used?

Student registration systems, employee profiles, and banking applications.

## 10. Pass a Structure to a Function

Question: Write a C program to read student details and pass the structure to a function to display the details.

Concept: Passing structures as function arguments.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

void display(struct Student s) {

    printf("\nStudent Details\n");

    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll);
    printf("Marks: %.2f\n", s.marks);
}

int main() {

    struct Student s1;

    printf("Enter student name: ");
    scanf("%29s", s1.name);

    printf("Enter roll number: ");
    scanf("%d", &s1.roll);

    printf("Enter marks: ");
    scanf("%f", &s1.marks);

    display(s1);

    return 0;
}
```

Expected Output:

```
Enter student name: Kiran
Enter roll number: 102
Enter marks: 88.5

Student Details
Name: Kiran
Roll Number: 102
Marks: 88.50
```

Why is this important?

It demonstrates how structures can be passed to functions, making programs modular and reusable.

Where is it used?

Large applications where different functions process student, employee, or customer records.

# Structures in C – Batch 2: Programs 11–20

In this batch, we will move beyond basic structure operations and learn structure pointers, `typedef`, sorting records, and practical applications.

## 11. Access Structure Members Using a Pointer

Question: Write a C program to read student details and display them using a pointer to a structure.

Concept: Pointer to structure and arrow (`->`) operator.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s;
    struct Student *ptr;

    ptr = &s;

    printf("Enter student name: ");
    scanf("%29s", ptr->name);

    printf("Enter roll number: ");
    scanf("%d", &ptr->roll);

    printf("Enter marks: ");
    scanf("%f", &ptr->marks);

    printf("\nStudent Details\n");

    printf("Name: %s\n", ptr->name);
    printf("Roll Number: %d\n", ptr->roll);
    printf("Marks: %.2f\n", ptr->marks);

    return 0;
}
```

Expected Output:

```
Enter student name: Ravi
Enter roll number: 101
Enter marks: 85.5

Student Details
Name: Ravi
Roll Number: 101
Marks: 85.50
```

Why is this important?

It teaches how pointers access structure members without directly using the structure variable.

Where is it used?

Dynamic data structures, linked lists, and memory-efficient record processing.

## 12. Use typedef with Structure

Question: Write a C program using `typedef` to create an alias for a structure and display employee details.

Concept: `typedef` with structures.

C Program:

```
#include <stdio.h>

typedef struct Employee {
    int id;
    char name[30];
    float salary;
} Employee;

int main() {

    Employee e;

    printf("Enter employee ID: ");
    scanf("%d", &e.id);

    printf("Enter employee name: ");
    scanf("%29s", e.name);

    printf("Enter salary: ");
    scanf("%f", &e.salary);

    printf("\nEmployee Details\n");

    printf("ID: %d\n", e.id);
    printf("Name: %s\n", e.name);
    printf("Salary: %.2f\n", e.salary);

    return 0;
}
```

Expected Output:

```
Enter employee ID: 501
Enter employee name: Rahul
Enter salary: 35000

Employee Details
ID: 501
Name: Rahul
Salary: 35000.00
```

Why is this important?

Without `typedef`, we write:

```
struct Employee e;
```

With `typedef`, we can simply write:

```
Employee e;
```

Where is it used?

Large C projects where structures are used frequently.

## 13. Sort Student Records Based on Marks

Question: Write a C program to read the details of five students and sort them in descending order based on their marks.

Concept: Array of structures and sorting.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s[5], temp;

    int i, j;

    for(i = 0; i < 5; i++) {

        printf("\nEnter student %d details\n", i + 1);

        printf("Enter name: ");
        scanf("%29s", s[i].name);

        printf("Enter roll number: ");
        scanf("%d", &s[i].roll);

        printf("Enter marks: ");
        scanf("%f", &s[i].marks);
    }

    for(i = 0; i < 4; i++) {

        for(j = 0; j < 4 - i; j++) {

            if(s[j].marks < s[j + 1].marks) {

                temp = s[j];
                s[j] = s[j + 1];
                s[j + 1] = temp;
            }
        }
    }

    printf("\nStudents Sorted by Marks\n");

    for(i = 0; i < 5; i++) {

        printf("\nName: %s\n", s[i].name);
        printf("Roll Number: %d\n", s[i].roll);
        printf("Marks: %.2f\n", s[i].marks);
    }

    return 0;
}
```

Expected Output (sample):

```
Students Sorted by Marks

Name: Kiran
Roll Number: 102
Marks: 95.00

Name: Ravi
Roll Number: 101
Marks: 90.00

Name: Suresh
Roll Number: 103
Marks: 85.00

...
```

Why is this important?

Students learn how to sort complete records rather than sorting only individual numbers.

Where is it used?

Merit lists, student rankings, employee performance rankings, and result processing.

## 14. Calculate Total and Average Marks of Multiple Students

Question: Write a C program to read five students' names and marks in three subjects. Calculate and display the total and average marks of each student.

Concept: Array of structures with multiple data members.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float m1, m2, m3;
    float total, average;
};

int main() {

    struct Student s[5];

    int i;

    for(i = 0; i < 5; i++) {

        printf("\nEnter student %d details\n", i + 1);

        printf("Enter name: ");
        scanf("%29s", s[i].name);

        printf("Enter roll number: ");
        scanf("%d", &s[i].roll);

        printf("Enter marks in 3 subjects: ");
        scanf("%f %f %f",
              &s[i].m1,
              &s[i].m2,
              &s[i].m3);

        s[i].total = s[i].m1 + s[i].m2 + s[i].m3;

        s[i].average = s[i].total / 3;
    }

    printf("\nStudent Results\n");

    for(i = 0; i < 5; i++) {

        printf("\nName: %s\n", s[i].name);
        printf("Roll Number: %d\n", s[i].roll);
        printf("Total: %.2f\n", s[i].total);
        printf("Average: %.2f\n", s[i].average);
    }

    return 0;
}
```

Expected Output (sample):

```
Student Results

Name: Ravi
Roll Number: 101
Total: 255.00
Average: 85.00

Name: Kiran
Roll Number: 102
Total: 270.00
Average: 90.00

...
```

Why is this important?

It shows how to store both original information and calculated results inside a structure.

Where is it used?

Automated examination and academic result management systems.

## 15. Count Students Who Passed and Failed

Question: Write a C program to read the details of five students and count how many students passed and failed. Consider 40 marks as the minimum passing mark.

Concept: Array of structures and conditional statements.

C Program:

```
#include <stdio.h>

struct Student {
    char name[30];
    int roll;
    float marks;
};

int main() {

    struct Student s[5];

    int i, pass = 0, fail = 0;

    for(i = 0; i < 5; i++) {

        printf("\nEnter student %d details\n", i + 1);

        printf("Enter name: ");
        scanf("%29s", s[i].name);

        printf("Enter roll number: ");
        scanf("%d", &s[i].roll);

        printf("Enter marks: ");
        scanf("%f", &s[i].marks);

        if(s[i].marks >= 40) {
            pass++;
        }
        else {
            fail++;
        }
    }

    printf("\nResult Summary\n");

    printf("Number of Passed Students: %d\n", pass);
    printf("Number of Failed Students: %d\n", fail);

    return 0;
}
```

Expected Output (sample):

```
Result Summary
Number of Passed Students: 4
Number of Failed Students: 1
```

Why is this important?

It combines structures with decision-making statements.

Where is it used?

College examination systems and student performance reports.

## 16. Store and Display Book Details

Question: Write a C program to store the book ID, book name, author name, and price using a structure. Read and display the details of three books.

Concept: Real-world application of an array of structures.

C Program:

```
#include <stdio.h>

struct Book {
    int id;
    char name[50];
    char author[50];
    float price;
};

int main() {

    struct Book b[3];

    int i;

    for(i = 0; i < 3; i++) {

        printf("\nEnter Book %d Details\n", i + 1);

        printf("Enter Book ID: ");
        scanf("%d", &b[i].id);

        printf("Enter Book Name: ");
        scanf("%49s", b[i].name);

        printf("Enter Author Name: ");
        scanf("%49s", b[i].author);

        printf("Enter Price: ");
        scanf("%f", &b[i].price);
    }

    printf("\nBook Details\n");

    for(i = 0; i < 3; i++) {

        printf("\nBook ID: %d\n", b[i].id);
        printf("Book Name: %s\n", b[i].name);
        printf("Author: %s\n", b[i].author);
        printf("Price: %.2f\n", b[i].price);
    }

    return 0;
}
```

Expected Output (sample):

```
Book Details

Book ID: 1
Book Name: CProgramming
Author: Dennis
Price: 450.00

Book ID: 2
Book Name: Java
Author: James
Price: 550.00
```

Why is this important?

It demonstrates how structures model real-world objects with multiple properties.

Where is it used?

Library management systems and bookstore applications.

## 17. Calculate Bank Account Balance Using Structure

Question: Write a C program to store account number, customer name, and balance using a structure. Accept a deposit amount and update the account balance.

Concept: Updating structure members using arithmetic operations.

C Program:

```
#include <stdio.h>

struct BankAccount {
    int accountNumber;
    char name[30];
    float balance;
};

int main() {

    struct BankAccount account;

    float deposit;

    printf("Enter account number: ");
    scanf("%d", &account.accountNumber);

    printf("Enter customer name: ");
    scanf("%29s", account.name);

    printf("Enter current balance: ");
    scanf("%f", &account.balance);

    printf("Enter deposit amount: ");
    scanf("%f", &deposit);

    if(deposit > 0) {

        account.balance = account.balance + deposit;

        printf("\nDeposit Successful!\n");
    }
    else {

        printf("\nInvalid deposit amount!\n");
    }

    printf("\nAccount Details\n");

    printf("Account Number: %d\n", account.accountNumber);
    printf("Customer Name: %s\n", account.name);
    printf("Updated Balance: %.2f\n", account.balance);

    return 0;
}
```

Expected Output:

```
Enter account number: 1001
Enter customer name: Rahul
Enter current balance: 10000
Enter deposit amount: 5000

Deposit Successful!

Account Details
Account Number: 1001
Customer Name: Rahul
Updated Balance: 15000.00
```

Why is this important?

It teaches how structures can store and update financial information.

Where is it used?

Banking applications, account management systems, and digital wallets.

## 18. Calculate Electricity Bill Using Structure

Question: Write a C program to store customer ID, customer name, and electricity units consumed using a structure. Calculate the electricity bill at ₹5 per unit.

Concept: Structure members with billing calculations.

C Program:

```
#include <stdio.h>

struct Customer {
    int id;
    char name[30];
    float units;
    float bill;
};

int main() {

    struct Customer c;

    printf("Enter customer ID: ");
    scanf("%d", &c.id);

    printf("Enter customer name: ");
    scanf("%29s", c.name);

    printf("Enter units consumed: ");
    scanf("%f", &c.units);

    if(c.units >= 0) {

        c.bill = c.units * 5;

        printf("\nElectricity Bill\n");

        printf("Customer ID: %d\n", c.id);
        printf("Customer Name: %s\n", c.name);
        printf("Units Consumed: %.2f\n", c.units);
        printf("Total Bill: Rs. %.2f\n", c.bill);
    }
    else {

        printf("Invalid units!\n");
    }

    return 0;
}
```

Expected Output:

```
Enter customer ID: 201
Enter customer name: Ravi
Enter units consumed: 150

Electricity Bill
Customer ID: 201
Customer Name: Ravi
Units Consumed: 150.00
Total Bill: Rs. 750.00
```

Why is this important?

It combines structures, conditions, and mathematical calculations.

Where is it used?

Electricity billing and utility management systems.

## 19. Compare Two Dates Using Structures

Question: Write a C program to read two dates using a structure and check whether both dates are equal.

Concept: Comparing structure members.

C Program:

```
#include <stdio.h>

struct Date {
    int day;
    int month;
    int year;
};

int main() {

    struct Date d1, d2;

    printf("Enter first date (DD MM YYYY): ");
    scanf("%d %d %d",
          &d1.day, &d1.month, &d1.year);

    printf("Enter second date (DD MM YYYY): ");
    scanf("%d %d %d",
          &d2.day, &d2.month, &d2.year);

    if(d1.day == d2.day &&
       d1.month == d2.month &&
       d1.year == d2.year) {

        printf("\nBoth dates are equal.\n");
    }
    else {

        printf("\nDates are different.\n");
    }

    return 0;
}
```

Expected Output:

```
Enter first date (DD MM YYYY): 15 08 2026
Enter second date (DD MM YYYY): 15 08 2026

Both dates are equal.
```

Why is this important?

It teaches that structure variables cannot generally be compared directly using `==`. Their individual members must be compared.

Where is it used?

Date validation, appointment scheduling, and booking applications.

## 20. Swap Two Structure Variables

Question: Write a C program to read two employee records and swap their complete details using a temporary structure variable.

Concept: Assigning one structure variable to another.

C Program:

```
#include <stdio.h>

struct Employee {
    int id;
    char name[30];
    float salary;
};

int main() {

    struct Employee e1, e2, temp;

    printf("Enter first employee details\n");

    printf("Enter ID: ");
    scanf("%d", &e1.id);

    printf("Enter name: ");
    scanf("%29s", e1.name);

    printf("Enter salary: ");
    scanf("%f", &e1.salary);

    printf("\nEnter second employee details\n");

    printf("Enter ID: ");
    scanf("%d", &e2.id);

    printf("Enter name: ");
    scanf("%29s", e2.name);

    printf("Enter salary: ");
    scanf("%f", &e2.salary);

    temp = e1;
    e1 = e2;
    e2 = temp;

    printf("\nAfter Swapping\n");

    printf("\nFirst Employee\n");
    printf("ID: %d\n", e1.id);
    printf("Name: %s\n", e1.name);
    printf("Salary: %.2f\n", e1.salary);

    printf("\nSecond Employee\n");
    printf("ID: %d\n", e2.id);
    printf("Name: %s\n", e2.name);
    printf("Salary: %.2f\n", e2.salary);

    return 0;
}
```

Expected Output (sample):

```
Enter first employee details
Enter ID: 101
Enter name: Ravi
Enter salary: 25000

Enter second employee details
Enter ID: 102
Enter name: Kiran
Enter salary: 35000

After Swapping

First Employee
ID: 102
Name: Kiran
Salary: 35000.00

Second Employee
ID: 101
Name: Ravi
Salary: 25000.00
```

Why is this important?

Unlike swapping individual variables, structure assignment allows us to swap all members together.

Where is it used?

Sorting records, rearranging employee information, and managing collections of records.

# Structures in C – Batch 3: Programs 21–30

This is the final batch of our 30 hands-on programs on Structures in C. These programs focus on structure pointers, functions, nested structures, arrays of records, and a mini project.

## 21. Find the Highest Salary Among Employees

Question: Write a C program to read the details of five employees and find the employee who receives the highest salary.

Concept: Array of structures and searching for the maximum value.

C Program:

```
#include <stdio.h>

struct Employee {
    int id;
    char name[30];
    float salary;
};

int main() {

    struct Employee e[5];

    int i, highest = 0;

    for(i = 0; i < 5; i++) {

        printf("\nEnter employee %d details\n", i + 1);

        printf("Enter ID: ");
        scanf("%d", &e[i].id);

        printf("Enter name: ");
        scanf("%29s", e[i].name);

        printf("Enter salary: ");
        scanf("%f", &e[i].salary);
    }

    for(i = 1; i < 5; i++) {

        if(e[i].salary > e[highest].salary) {
            highest = i;
        }
    }

    printf("\nHighest Paid Employee\n");

    printf("ID: %d\n", e[highest].id);
    printf("Name: %s\n", e[highest].name);
    printf("Salary: %.2f\n", e[highest].salary);

    return 0;
}
```

Expected Output (sample):

```
Highest Paid Employee

ID: 103
Name: Suresh
Salary: 75000.00
```

Why is this important?

It teaches how to identify a particular record based on a structure member.

Where is it used?

Payroll systems and employee performance analysis.

## 22. Pass a Structure Pointer to a Function

Question: Write a C program to read employee details and pass the address of the structure to a function to display the details.

Concept: Structure pointer as a function argument.

C Program:

```
#include <stdio.h>

struct Employee {
    int id;
    char name[30];
    float salary;
};

void display(struct Employee *ptr) {

    printf("\nEmployee Details\n");

    printf("ID: %d\n", ptr->id);
    printf("Name: %s\n", ptr->name);
    printf("Salary: %.2f\n", ptr->salary);
}

int main() {

    struct Employee e;

    printf("Enter employee ID: ");
    scanf("%d", &e.id);

    printf("Enter employee name: ");
    scanf("%29s", e.name);

    printf("Enter salary: ");
    scanf("%f", &e.salary);

    display(&e);

    return 0;
}
```

Expected Output:

```
Enter employee ID: 101
Enter employee name: Ravi
Enter salary: 40000

Employee Details
ID: 101
Name: Ravi
Salary: 40000.00
```

Why is this important?

Passing a structure pointer avoids copying the entire structure into the function. It also allows the function to modify the original structure.

Where is it used?

Large applications where functions process employee, student, and customer records.

## 23. Modify Structure Data Using a Pointer Function

Question: Write a C program to read student details and update the student's marks using a function that receives a structure pointer.

Concept: Modifying original structure members through pointers.

C Program:

```
#include <stdio.h>

struct Student {
    int roll;
    char name[30];
    float marks;
};

void updateMarks(struct Student *ptr) {

    printf("\nEnter updated marks: ");
    scanf("%f", &ptr->marks);

}

int main() {

    struct Student s;

    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter name: ");
    scanf("%29s", s.name);

    printf("Enter current marks: ");
    scanf("%f", &s.marks);

    printf("\nBefore Updating: %.2f\n", s.marks);

    updateMarks(&s);

    printf("\nAfter Updating\n");

    printf("Roll Number: %d\n", s.roll);
    printf("Name: %s\n", s.name);
    printf("Updated Marks: %.2f\n", s.marks);

    return 0;
}
```

Expected Output:

```
Enter roll number: 101
Enter name: Ravi
Enter current marks: 75

Before Updating: 75.00

Enter updated marks: 95

After Updating
Roll Number: 101
Name: Ravi
Updated Marks: 95.00
```

Why is this important?

It demonstrates how a function can directly modify the original structure using its address.

Where is it used?

Updating student results, employee records, and customer information.

## 24. Store and Display Product Details Using Structures

Question: Write a C program to store the ID, name, price, and quantity of five products. Calculate and display the total value of each product.

Concept: Array of structures with calculated members.

C Program:

```
#include <stdio.h>

struct Product {
    int id;
    char name[30];
    float price;
    int quantity;
    float total;
};

int main() {

    struct Product p[5];

    int i;

    for(i = 0; i < 5; i++) {

        printf("\nEnter product %d details\n", i + 1);

        printf("Enter product ID: ");
        scanf("%d", &p[i].id);

        printf("Enter product name: ");
        scanf("%29s", p[i].name);

        printf("Enter price: ");
        scanf("%f", &p[i].price);

        printf("Enter quantity: ");
        scanf("%d", &p[i].quantity);

        p[i].total = p[i].price * p[i].quantity;
    }

    printf("\nProduct Details\n");

    for(i = 0; i < 5; i++) {

        printf("\nProduct ID: %d\n", p[i].id);
        printf("Name: %s\n", p[i].name);
        printf("Price: %.2f\n", p[i].price);
        printf("Quantity: %d\n", p[i].quantity);
        printf("Total Value: %.2f\n", p[i].total);
    }

    return 0;
}
```

Expected Output (sample):

```
Product Details

Product ID: 101
Name: Laptop
Price: 50000.00
Quantity: 2
Total Value: 100000.00
```

Why is this important?

It demonstrates how multiple related properties can be grouped and processed together.

Where is it used?

Inventory management, shopping applications, and billing systems.

## 25. Calculate the Total Bill of Multiple Products

Question: Write a C program to read the details of three products and calculate the grand total bill.

Concept: Array of structures and aggregate calculations.

C Program:

```
#include <stdio.h>

struct Product {
    char name[30];
    float price;
    int quantity;
    float amount;
};

int main() {

    struct Product p[3];

    int i;
    float grandTotal = 0;

    for(i = 0; i < 3; i++) {

        printf("\nEnter product %d details\n", i + 1);

        printf("Enter product name: ");
        scanf("%29s", p[i].name);

        printf("Enter price: ");
        scanf("%f", &p[i].price);

        printf("Enter quantity: ");
        scanf("%d", &p[i].quantity);

        p[i].amount = p[i].price * p[i].quantity;

        grandTotal = grandTotal + p[i].amount;
    }

    printf("\nShopping Bill\n");

    for(i = 0; i < 3; i++) {

        printf("\nProduct: %s\n", p[i].name);
        printf("Amount: %.2f\n", p[i].amount);
    }

    printf("\nGrand Total: Rs. %.2f\n", grandTotal);

    return 0;
}
```

Expected Output (sample):

```
Shopping Bill

Product: Laptop
Amount: 50000.00

Product: Mouse
Amount: 500.00

Product: Keyboard
Amount: 1000.00

Grand Total: Rs. 51500.00
```

Why is this important?

It teaches how to process multiple records and calculate a combined result.

Where is it used?

Supermarket billing, e-commerce applications, and shopping carts.

## 26. Search for a Book Using Book ID

Question: Write a C program to store five book records and search for a book using its ID.

Concept: Linear search using an array of structures.

C Program:

```
#include <stdio.h>

struct Book {
    int id;
    char name[30];
    float price;
};

int main() {

    struct Book b[5];

    int i, searchId, found = 0;

    for(i = 0; i < 5; i++) {

        printf("\nEnter book %d details\n", i + 1);

        printf("Enter book ID: ");
        scanf("%d", &b[i].id);

        printf("Enter book name: ");
        scanf("%29s", b[i].name);

        printf("Enter price: ");
        scanf("%f", &b[i].price);
    }

    printf("\nEnter book ID to search: ");
    scanf("%d", &searchId);

    for(i = 0; i < 5; i++) {

        if(b[i].id == searchId) {

            printf("\nBook Found!\n");

            printf("ID: %d\n", b[i].id);
            printf("Name: %s\n", b[i].name);
            printf("Price: %.2f\n", b[i].price);

            found = 1;
            break;
        }
    }

    if(found == 0) {
        printf("\nBook Not Found!\n");
    }

    return 0;
}
```

Expected Output (sample):

```
Enter book ID to search: 103

Book Found!
ID: 103
Name: Python
Price: 600.00
```

Why is this important?

It reinforces searching through structured records.

Where is it used?

Library management and online bookstore applications.

## 27. Store Student Address Using Nested Structures

Question: Write a C program to store a student's name, roll number, and address. The address should contain city, state, and PIN code using a nested structure.

Concept: Nested structures.

C Program:

```
#include <stdio.h>

struct Address {
    char city[30];
    char state[30];
    int pincode;
};

struct Student {
    char name[30];
    int roll;
    struct Address address;
};

int main() {

    struct Student s;

    printf("Enter student name: ");
    scanf("%29s", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.roll);

    printf("Enter city: ");
    scanf("%29s", s.address.city);

    printf("Enter state: ");
    scanf("%29s", s.address.state);

    printf("Enter PIN code: ");
    scanf("%d", &s.address.pincode);

    printf("\nStudent Details\n");

    printf("Name: %s\n", s.name);
    printf("Roll Number: %d\n", s.roll);

    printf("\nAddress Details\n");

    printf("City: %s\n", s.address.city);
    printf("State: %s\n", s.address.state);
    printf("PIN Code: %d\n", s.address.pincode);

    return 0;
}
```

Expected Output:

```
Enter student name: Ravi
Enter roll number: 101
Enter city: Hyderabad
Enter state: Telangana
Enter PIN code: 500001

Student Details
Name: Ravi
Roll Number: 101

Address Details
City: Hyderabad
State: Telangana
PIN Code: 500001
```

Why is this important?

It demonstrates how one structure can contain another structure as a member.

Where is it used?

Student registration, customer profiles, and employee management applications.

## 28. Create a Menu-Driven Student Management Program

Question: Write a menu-driven C program to perform the following operations using structures:

1. Add student details.
2. Display all students.
3. Exit.

Concept: Array of structures, functions, loops, and switch statements.

C Program:

```
#include <stdio.h>

struct Student {
    int roll;
    char name[30];
    float marks;
};

int main() {

    struct Student s[50];

    int choice;
    int count = 0;
    int i;

    do {

        printf("\n===== STUDENT MANAGEMENT =====\n");

        printf("1. Add Student\n");
        printf("2. Display Students\n");
        printf("3. Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {

            case 1:

                if(count < 50) {

                    printf("\nEnter student name: ");
                    scanf("%29s", s[count].name);

                    printf("Enter roll number: ");
                    scanf("%d", &s[count].roll);

                    printf("Enter marks: ");
                    scanf("%f", &s[count].marks);

                    count++;

                    printf("\nStudent Added Successfully!\n");
                }
                else {

                    printf("\nStudent limit reached!\n");
                }

                break;

            case 2:

                if(count == 0) {

                    printf("\nNo student records available.\n");
                }
                else {

                    printf("\nStudent Records\n");

                    for(i = 0; i < count; i++) {

                        printf("\nName: %s\n", s[i].name);
                        printf("Roll: %d\n", s[i].roll);
                        printf("Marks: %.2f\n", s[i].marks);
                    }
                }

                break;

            case 3:

                printf("\nExiting Program...\n");
                break;

            default:

                printf("\nInvalid Choice!\n");
        }

    } while(choice != 3);

    return 0;
}
```

Expected Output (sample):

```
===== STUDENT MANAGEMENT =====
1. Add Student
2. Display Students
3. Exit

Enter your choice: 1

Enter student name: Ravi
Enter roll number: 101
Enter marks: 85

Student Added Successfully!

===== STUDENT MANAGEMENT =====
1. Add Student
2. Display Students
3. Exit

Enter your choice: 2

Student Records

Name: Ravi
Roll: 101
Marks: 85.00
```

Why is this important?

It combines multiple concepts into one practical application.

Where is it used?

College student management systems.

## 29. Create a Menu-Driven Employee Management Program

Question: Write a C program to manage employee records with the following operations:

1. Add employee.
2. Display all employees.
3. Search employee by ID.
4. Exit.

Concept: Structures, arrays, searching, and menu-driven programming.

C Program:

```
#include <stdio.h>

struct Employee {
    int id;
    char name[30];
    float salary;
};

int main() {

    struct Employee e[50];

    int choice;
    int count = 0;
    int i, searchId, found;

    do {

        printf("\n===== EMPLOYEE MANAGEMENT =====\n");

        printf("1. Add Employee\n");
        printf("2. Display Employees\n");
        printf("3. Search Employee\n");
        printf("4. Exit\n");

        printf("Enter choice: ");
        scanf("%d", &choice);

        switch(choice) {

            case 1:

                if(count < 50) {

                    printf("\nEnter employee ID: ");
                    scanf("%d", &e[count].id);

                    printf("Enter employee name: ");
                    scanf("%29s", e[count].name);

                    printf("Enter salary: ");
                    scanf("%f", &e[count].salary);

                    count++;

                    printf("\nEmployee Added Successfully!\n");
                }
                else {

                    printf("\nEmployee limit reached!\n");
                }

                break;

            case 2:

                for(i = 0; i < count; i++) {

                    printf("\nID: %d\n", e[i].id);
                    printf("Name: %s\n", e[i].name);
                    printf("Salary: %.2f\n", e[i].salary);
                }

                if(count == 0) {
                    printf("\nNo employee records available.\n");
                }

                break;

            case 3:

                printf("\nEnter employee ID to search: ");
                scanf("%d", &searchId);

                found = 0;

                for(i = 0; i < count; i++) {

                    if(e[i].id == searchId) {

                        printf("\nEmployee Found!\n");

                        printf("ID: %d\n", e[i].id);
                        printf("Name: %s\n", e[i].name);
                        printf("Salary: %.2f\n", e[i].salary);

                        found = 1;
                        break;
                    }
                }

                if(found == 0) {
                    printf("\nEmployee Not Found!\n");
                }

                break;

            case 4:

                printf("\nExiting Program...\n");
                break;

            default:

                printf("\nInvalid Choice!\n");
        }

    } while(choice != 4);

    return 0;
}
```

Expected Output (sample):

```
===== EMPLOYEE MANAGEMENT =====
1. Add Employee
2. Display Employees
3. Search Employee
4. Exit

Enter choice: 1

Enter employee ID: 101
Enter employee name: Rahul
Enter salary: 35000

Employee Added Successfully!

Enter choice: 3

Enter employee ID to search: 101

Employee Found!
ID: 101
Name: Rahul
Salary: 35000.00
```

Why is this important?

It gives students experience building a small record-management application.

Where is it used?

HR systems, payroll applications, and employee databases.

## 30. Mini Project – Student Result Management System

Question: Develop a student result management system using structures. The program should support:

1. Add student records.
2. Display all student records.
3. Calculate total and average marks.
4. Display pass/fail status.
5. Search student by roll number.
6. Exit.

Consider 40 marks as the minimum passing mark in each subject.

Concept: Structures, arrays, functions, searching, conditions, loops, and menu-driven programming.

C Program:

```
#include <stdio.h>

struct Student {
    int roll;
    char name[30];

    float m1, m2, m3;

    float total;
    float average;
};

void addStudent(struct Student s[], int *count) {

    if(*count >= 50) {

        printf("\nStudent limit reached!\n");
        return;
    }

    printf("\nEnter student name: ");
    scanf("%29s", s[*count].name);

    printf("Enter roll number: ");
    scanf("%d", &s[*count].roll);

    printf("Enter marks in three subjects: ");

    scanf("%f %f %f",
          &s[*count].m1,
          &s[*count].m2,
          &s[*count].m3);

    s[*count].total =
        s[*count].m1 +
        s[*count].m2 +
        s[*count].m3;

    s[*count].average = s[*count].total / 3;

    (*count)++;

    printf("\nStudent Added Successfully!\n");
}

void displayStudents(struct Student s[], int count) {

    int i;

    if(count == 0) {

        printf("\nNo records available!\n");
        return;
    }

    for(i = 0; i < count; i++) {

        printf("\nStudent Details\n");

        printf("Name: %s\n", s[i].name);
        printf("Roll: %d\n", s[i].roll);

        printf("Total: %.2f\n", s[i].total);
        printf("Average: %.2f\n", s[i].average);

        if(s[i].m1 >= 40 &&
           s[i].m2 >= 40 &&
           s[i].m3 >= 40) {

            printf("Result: PASS\n");
        }
        else {

            printf("Result: FAIL\n");
        }
    }
}

void searchStudent(struct Student s[], int count) {

    int roll, i, found = 0;

    printf("\nEnter roll number to search: ");
    scanf("%d", &roll);

    for(i = 0; i < count; i++) {

        if(s[i].roll == roll) {

            printf("\nStudent Found!\n");

            printf("Name: %s\n", s[i].name);
            printf("Roll: %d\n", s[i].roll);

            printf("Total: %.2f\n", s[i].total);
            printf("Average: %.2f\n", s[i].average);

            if(s[i].m1 >= 40 &&
               s[i].m2 >= 40 &&
               s[i].m3 >= 40) {

                printf("Result: PASS\n");
            }
            else {

                printf("Result: FAIL\n");
            }

            found = 1;
            break;
        }
    }

    if(found == 0) {

        printf("\nStudent Not Found!\n");
    }
}

int main() {

    struct Student s[50];

    int choice;
    int count = 0;

    do {

        printf("\n===== STUDENT RESULT MANAGEMENT =====\n");

        printf("1. Add Student\n");
        printf("2. Display All Students\n");
        printf("3. Search Student\n");
        printf("4. Exit\n");

        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {

            case 1:
                addStudent(s, &count);
                break;

            case 2:
                displayStudents(s, count);
                break;

            case 3:
                searchStudent(s, count);
                break;

            case 4:
                printf("\nThank You!\n");
                break;

            default:
                printf("\nInvalid Choice!\n");
        }

    } while(choice != 4);

    return 0;
}
```

Expected Output (sample):

```
===== STUDENT RESULT MANAGEMENT =====
1. Add Student
2. Display All Students
3. Search Student
4. Exit

Enter your choice: 1

Enter student name: Ravi
Enter roll number: 101
Enter marks in three subjects: 85 90 80

Student Added Successfully!

Enter your choice: 2

Student Details
Name: Ravi
Roll: 101
Total: 255.00
Average: 85.00
Result: PASS

Enter your choice: 3

Enter roll number to search: 101

Student Found!
Name: Ravi
Roll: 101
Total: 255.00
Average: 85.00
Result: PASS
```

Why is this important?

This mini project demonstrates how structures work together with functions, arrays, pointers, and conditions in a real application.

Where is it used?

College examination portals and student academic management systems.


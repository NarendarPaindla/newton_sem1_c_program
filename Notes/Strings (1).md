# C Programming – Complete Strings Notes and Practical Programs

Strings are one of the most important topics in C programming. They are used whenever we need to store, process, compare, search, or manipulate text.

Examples include student names, email addresses, passwords, mobile application messages, employee details, and product names.

This module starts from the basics and progresses to string functions, character processing, arrays of strings, and practical programming problems.

# 1. Introduction to Strings

## What is a string?

A string in C is a sequence of characters terminated by a special character called the null character (`'\0'`).

For example:

```
char name[] = "Narendar";
```

This stores the characters:

```
N  a  r  e  n  d  a  r  \0
```

The last character `'\0'` indicates the end of the string.

Important: C does not have a separate built-in `string` data type. Strings are represented using character arrays.

## Real-world example

Suppose you are developing a student registration application.

You need to store:

- Student name
- College name
- Email address
- City
- Department

These are all text values, so strings are used.

Student registration data

Student name

Narendar

College

Newton College

City

Guntur

Department

CSE

# 2. Why Do We Need Strings?

Consider the following declaration:

```
char first = 'N';
```

This stores only one character.

But what if we want to store an entire name such as `Narendar`?

We use a character array:

```
char name[20] = "Narendar";
```

This can store up to 19 ordinary characters plus the terminating null character.

Where strings are used:

1. Student management systems.
2. Login and registration applications.
3. Email and username validation.
4. Banking applications.
5. Text editors.
6. Search engines.
7. Chat applications.
8. File processing.

# 3. Difference Between Character and String

This is an important concept.

| Character            | String                     |
| -------------------- | -------------------------- |
| Stores one character | Stores multiple characters |
| Uses single quotes   | Uses double quotes         |
| Uses `char`          | Uses `char` array          |
| Example: `'A'`       | Example: `"Apple"`         |

Example:

```
char ch = 'A';

char name[] = "Apple";
```

Remember:

- `'A'` is a character.
- `"A"` is a string containing one visible character and a null terminator.

# 4. Understanding the Null Character (`'\0'`)

The null character is one of the most important concepts in C strings.

Consider:

```
char name[] = "CAT";
```

Internally, the array contains:

String memory representation

# C

Index 0

# A

Index 1

# T

Index 2

# \0

Index 3

The null character marks the end of the string. It is not the same as the character `'0'`.

Total array size = 4 bytes, assuming one byte per `char`.

Why is `'\0'` necessary?

Suppose C stores:

```
char name[] = "CAT";
```

When we print the string using:

```
printf("%s", name);
```

C continues reading characters until it encounters `'\0'`.

Without a proper null terminator, string operations may read beyond the array, causing undefined behavior.

# 5. Declaration and Initialization of Strings

## 5.1 Declaration

```
char name[20];
```

Creates a character array with space for 20 characters, including the null terminator when used as a C string.

## 5.2 Initialization Using a String Literal

```
char name[20] = "Narendar";
```

## 5.3 Initialization Without Specifying Size

```
char name[] = "Hello";
```

The compiler automatically allocates enough space for all characters plus `'\0'`.

Here, the size is 6.

## 5.4 Character-by-Character Initialization

```
char name[5] = {'C', 'O', 'D', 'E', '\0'};
```

## 5.5 Empty String Initialization

```
char name[20] = "";
```

This creates an empty string whose first character is `'\0'`.

# 6. Reading and Displaying Strings

There are different ways to read strings in C.

## 6.1 Using `scanf()`

```
#include <stdio.h>

int main() {
    char name[30];

    printf("Enter your name: ");
    scanf("%29s", name);

    printf("Your name is %s", name);

    return 0;
}
```

Expected Input

```
Enter your name: Narendar
```

Expected Output

```
Your name is Narendar
```

Important points:

- `%s` is used to read a string.
- We do not use `&` before the array name in this `scanf()` call.
- `%29s` limits the input to 29 characters, leaving space for `'\0'`.
- `scanf("%s")` stops reading at whitespace.

For example, if the input is `Narendar Reddy`, only `Narendar` is read.

## 6.2 Using `fgets()`

To read a full name containing spaces, use `fgets()`.

```
#include <stdio.h>

int main() {
    char name[50];

    printf("Enter your full name: ");
    fgets(name, sizeof(name), stdin);

    printf("Your name is: %s", name);

    return 0;
}
```

Expected Input

```
Enter your full name: Narendar Reddy
```

Expected Output

```
Your name is: Narendar Reddy
```

Important points:

- `fgets()` can read spaces.
- It limits how many characters are read.
- It may retain the newline character `'\n'` when there is room.
- It automatically adds `'\0'` when successful.

## 6.3 Difference Between `scanf()` and `fgets()`

| Feature              | `scanf("%s", ...)`    | `fgets()`             |
| -------------------- | --------------------- | --------------------- |
| Reads one word       | Yes                   | Yes                   |
| Reads spaces         | No                    | Yes                   |
| Reads full name      | No                    | Yes                   |
| Can limit input size | Yes, with field width | Yes, with buffer size |
| Reads newline        | Stops at whitespace   | May retain newline    |

Trainer tip: Prefer `fgets()` when reading names, addresses, sentences, and other text containing spaces.

# 7. Removing the Newline from `fgets()`

When we use `fgets()`, it may store the Enter key as `'\n'` inside the string.

Example:

```
char name[50];

fgets(name, sizeof(name), stdin);
```

If the user enters `Ravi` and presses Enter, the array may contain:

```
R a v i \n \0
```

We can remove the newline using `strcspn()` from `string.h`.

```
#include <stdio.h>
#include <string.h>

int main() {
    char name[50];

    printf("Enter your name: ");
    fgets(name, sizeof(name), stdin);

    name[strcspn(name, "\n")] = '\0';

    printf("Name: %s", name);

    return 0;
}
```

Expected Input

```
Enter your name: Ravi Kumar
```

Expected Output

```
Name: Ravi Kumar
```

# 8. Displaying Strings Character by Character

A string is a character array, so we can access each character using its index.

Question: Write a C program to display every character of a string on a separate line.

```
#include <stdio.h>

int main() {
    char name[] = "HELLO";
    int i = 0;

    while (name[i] != '\0') {
        printf("%c\n", name[i]);
        i++;
    }

    return 0;
}
```

Expected Output

```
H
E
L
L
O
```

Important logic:

```
while (name[i] != '\0')
```

The loop continues until it reaches the null character.

Why this is important: Helps students understand how strings are stored and processed internally.

Where it is used: Character processing, text analysis, and string manipulation.

# 9. String Length

String length means the number of visible characters in a string, excluding the null character.

Example:

```
char name[] = "APPLE";
```

Length = 5.

Array size = 6, because it also contains `'\0'`.

## Using `strlen()`

The `strlen()` function is available in `string.h`.

Syntax:

```
strlen(string_name);
```

Program:

```
#include <stdio.h>
#include <string.h>

int main() {
    char name[] = "APPLE";

    printf("Length = %zu", strlen(name));

    return 0;
}
```

Expected Output

```
Length = 5
```

## Difference Between `strlen()` and `sizeof()`

This is an important viva question.

```
char name[] = "APPLE";

printf("%zu\n", strlen(name));
printf("%zu\n", sizeof(name));
```

Expected Output

```
5
6
```

| Function/operator | Meaning                              |
| ----------------- | ------------------------------------ |
| `strlen()`        | Counts characters before `'\0'`      |
| `sizeof()`        | Gives the size of the array in bytes |

# 10. Important String Handling Functions

C provides several built-in string handling functions through the `string.h` header file.

First, understand these six important functions.

## 10.1 `strlen()` – Find String Length

Purpose: Returns the number of characters in a string, excluding `'\0'`.

```
#include <stdio.h>
#include <string.h>

int main() {
    char name[] = "Newton";

    printf("Length = %zu", strlen(name));

    return 0;
}
```

Output

```
Length = 6
```

## 10.2 `strcpy()` – Copy One String into Another

Purpose: Copies the source string, including its terminating null character, into the destination.

Syntax:

```
strcpy(destination, source);
```

```
#include <stdio.h>
#include <string.h>

int main() {
    char source[] = "Hello";
    char destination[20];

    strcpy(destination, source);

    printf("Copied string: %s", destination);

    return 0;
}
```

Output

```
Copied string: Hello
```

Important: The destination must have enough space to hold the copied string, including `'\0'`.

## 10.3 `strcat()` – Join Two Strings

Purpose: Appends the source string to the end of the destination string.

Syntax:

```
strcat(destination, source);
```

```
#include <stdio.h>
#include <string.h>

int main() {
    char first[30] = "Hello ";
    char second[] = "World";

    strcat(first, second);

    printf("%s", first);

    return 0;
}
```

Output

```
Hello World
```

Important: The destination must have sufficient capacity for both strings and the null terminator.

## 10.4 `strcmp()` – Compare Two Strings

Purpose: Compares two strings lexicographically.

Syntax:

```
strcmp(string1, string2);
```

Return value:

| Result   | Meaning                          |
| -------- | -------------------------------- |
| 0        | Both strings are equal           |
| Negative | First string comes before second |
| Positive | First string comes after second  |

Example:

```
#include <stdio.h>
#include <string.h>

int main() {
    char a[] = "Apple";
    char b[] = "Apple";

    if (strcmp(a, b) == 0) {
        printf("Strings are equal");
    } else {
        printf("Strings are not equal");
    }

    return 0;
}
```

Output

```
Strings are equal
```

Important: Do not compare strings using `==` when you want to compare their contents.

Incorrect:

```
if (a == b)
```

Correct:

```
if (strcmp(a, b) == 0)
```

## 10.5 `strchr()` – Find a Character in a String

Purpose: Finds the first occurrence of a specified character.

```
#include <stdio.h>
#include <string.h>

int main() {
    char name[] = "PROGRAMMING";

    char *result = strchr(name, 'G');

    if (result != NULL) {
        printf("Character found");
    } else {
        printf("Character not found");
    }

    return 0;
}
```

Output

```
Character found
```

## 10.6 `strstr()` – Find a Substring

Purpose: Searches for a smaller string inside another string.

```
#include <stdio.h>
#include <string.h>

int main() {
    char sentence[] = "I love C programming";

    if (strstr(sentence, "C") != NULL) {
        printf("Substring found");
    } else {
        printf("Substring not found");
    }

    return 0;
}
```

Output

```
Substring found
```

# 11. Important Character Handling Functions

The `ctype.h` header provides functions to classify and convert characters.

| Function    | Purpose                                         |
| ----------- | ----------------------------------------------- |
| `isalpha()` | Checks whether a character is an alphabet       |
| `isdigit()` | Checks whether a character is a digit           |
| `isalnum()` | Checks whether a character is a letter or digit |
| `isspace()` | Checks whether a character is whitespace        |
| `islower()` | Checks whether a character is lowercase         |
| `isupper()` | Checks whether a character is uppercase         |
| `toupper()` | Converts a lowercase character to uppercase     |
| `tolower()` | Converts an uppercase character to lowercase    |

Example:

```
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'a';

    printf("Uppercase = %c\n", toupper((unsigned char)ch));

    printf("Is alphabet = %d\n", isalpha((unsigned char)ch));

    return 0;
}
```

Expected Output

```
Uppercase = A
Is alphabet = 1
```

Note: Character classification functions return zero when the condition is false and a nonzero value when it is true.

# 12. Difference Between `strcpy()`, `strcat()`, and `strcmp()`

| Function   | Operation        | Example                        |
| ---------- | ---------------- | ------------------------------ |
| `strcpy()` | Copies a string  | `"Hello"` into another array   |
| `strcat()` | Joins strings    | `"Hello" + " World"`           |
| `strcmp()` | Compares strings | Checks whether two names match |

# 13. String Operations Without Built-in Functions

Students should understand how these functions work internally, rather than depending only on library functions.

## 13.1 Find String Length Without `strlen()`

```
#include <stdio.h>

int main() {
    char str[100];
    int i = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0' && str[i] != '\n') {
        i++;
    }

    printf("Length = %d", i);

    return 0;
}
```

Expected Input

```
Enter a string: Hello World
```

Expected Output

```
Length = 11
```

## 13.2 Copy a String Without `strcpy()`

```
#include <stdio.h>

int main() {
    char source[] = "Newton";
    char destination[50];
    int i = 0;

    while (source[i] != '\0') {
        destination[i] = source[i];
        i++;
    }

    destination[i] = '\0';

    printf("Copied string: %s", destination);

    return 0;
}
```

Expected Output

```
Copied string: Newton
```

## 13.3 Join Two Strings Without `strcat()`

```
#include <stdio.h>

int main() {
    char first[50] = "Hello ";
    char second[] = "Students";
    int i = 0, j = 0;

    while (first[i] != '\0') {
        i++;
    }

    while (second[j] != '\0') {
        first[i] = second[j];
        i++;
        j++;
    }

    first[i] = '\0';

    printf("%s", first);

    return 0;
}
```

Expected Output

```
Hello Students
```

## 13.4 Compare Two Strings Without `strcmp()`

```
#include <stdio.h>

int main() {
    char a[] = "HELLO";
    char b[] = "HELLO";
    int i = 0;

    while (a[i] == b[i] && a[i] != '\0') {
        i++;
    }

    if (a[i] == b[i]) {
        printf("Strings are equal");
    } else {
        printf("Strings are not equal");
    }

    return 0;
}
```

Expected Output

```
Strings are equal
```

# 14. Important String Programs

These programs cover the main logic-building problems that students should practise.

## Program 1: Find the Length of a String

Question: Write a C program to find the length of a string without using `strlen()`.

```
#include <stdio.h>

int main() {
    char str[100];
    int i = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0' && str[i] != '\n') {
        i++;
    }

    printf("Length = %d", i);

    return 0;
}
```

Expected Input

```
Enter a string: Programming
```

Expected Output

```
Length = 11
```

Why this is important: Teaches how strings are traversed using a loop.

Where it is used: Input validation, text processing, and form validation.

## Program 2: Count Vowels and Consonants

Question: Write a C program to count vowels and consonants in a string.

```
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100];
    int i = 0, vowels = 0, consonants = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0') {
        char ch = (char)tolower((unsigned char)str[i]);

        if (ch >= 'a' && ch <= 'z') {
            if (ch == 'a' || ch == 'e' || ch == 'i' ||
                ch == 'o' || ch == 'u') {
                vowels++;
            } else {
                consonants++;
            }
        }

        i++;
    }

    printf("Vowels = %d\n", vowels);
    printf("Consonants = %d", consonants);

    return 0;
}
```

Expected Input

```
Enter a string: Hello World
```

Expected Output

```
Vowels = 3
Consonants = 7
```

Why this is important: Combines string traversal, character conversion, and conditional statements.

Where it is used: Text analysis and basic language-processing applications.

## Program 3: Count the Number of Words

Question: Write a C program to count the number of words in a sentence.

```
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[200];
    int i = 0, count = 0, inWord = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0') {
        if (!isspace((unsigned char)str[i])) {
            if (inWord == 0) {
                count++;
                inWord = 1;
            }
        } else {
            inWord = 0;
        }

        i++;
    }

    printf("Word count = %d", count);

    return 0;
}
```

Expected Input

```
Enter a sentence: C programming is easy
```

Expected Output

```
Word count = 4
```

Why this is important: Demonstrates how to identify word boundaries using whitespace.

Where it is used: Word counters, document editors, and text analysis tools.

## Program 4: Reverse a String

Question: Write a C program to reverse a string without using built-in reverse functions.

```
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], temp;
    int i, j;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    str[strcspn(str, "\n")] = '\0';

    i = 0;
    j = (int)strlen(str) - 1;

    while (i < j) {
        temp = str[i];
        str[i] = str[j];
        str[j] = temp;

        i++;
        j--;
    }

    printf("Reversed string: %s", str);

    return 0;
}
```

Expected Input

```
Enter a string: HELLO
```

Expected Output

```
Reversed string: OLLEH
```

Why this is important: Teaches swapping and working with opposite indexes.

Where it is used: Text manipulation, palindrome checking, and string algorithms.

## Program 5: Check Whether a String Is a Palindrome

Question: Write a C program to check whether a string is a palindrome, ignoring letter case.

Example: `madam` reads the same forward and backward.

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[100];
    int i, j, palindrome = 1;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    str[strcspn(str, "\n")] = '\0';

    i = 0;
    j = (int)strlen(str) - 1;

    while (i < j) {
        if (tolower((unsigned char)str[i]) !=
            tolower((unsigned char)str[j])) {
            palindrome = 0;
            break;
        }

        i++;
        j--;
    }

    if (palindrome) {
        printf("Palindrome string");
    } else {
        printf("Not a palindrome string");
    }

    return 0;
}
```

Expected Input

```
Enter a string: Madam
```

Expected Output

```
Palindrome string
```

Why this is important: Combines string comparison, reverse traversal, and case conversion.

Where it is used: Text-processing exercises and palindrome-based applications.

## Program 6: Convert Lowercase to Uppercase

Question: Write a C program to convert all lowercase letters in a string to uppercase.

```
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100];
    int i = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0') {
        str[i] = (char)toupper((unsigned char)str[i]);
        i++;
    }

    printf("Uppercase: %s", str);

    return 0;
}
```

Expected Input

```
Enter a string: Hello World
```

Expected Output

```
Uppercase: HELLO WORLD
```

Why this is important: Demonstrates character conversion inside a string traversal.

Where it is used: Search normalization, formatting, and case-insensitive processing.

## Program 7: Convert Uppercase to Lowercase

Question: Write a C program to convert all uppercase letters in a string to lowercase.

```
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100];
    int i = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0') {
        str[i] = (char)tolower((unsigned char)str[i]);
        i++;
    }

    printf("Lowercase: %s", str);

    return 0;
}
```

Expected Input

```
Enter a string: HELLO WORLD
```

Expected Output

```
Lowercase: hello world
```

Why this is important: Helps students understand how to transform text character by character.

Where it is used: Username handling, search systems, and text normalization.

## Program 8: Count Digits, Alphabets, and Special Characters

Question: Write a C program to count alphabets, digits, and special characters in a string.

```
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100];
    int i = 0, alphabets = 0, digits = 0, special = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0' && str[i] != '\n') {
        unsigned char ch = (unsigned char)str[i];

        if (isalpha(ch)) {
            alphabets++;
        } else if (isdigit(ch)) {
            digits++;
        } else if (!isspace(ch)) {
            special++;
        }

        i++;
    }

    printf("Alphabets = %d\n", alphabets);
    printf("Digits = %d\n", digits);
    printf("Special characters = %d", special);

    return 0;
}
```

Expected Input

```
Enter a string: Hello123@
```

Expected Output

```
Alphabets = 5
Digits = 3
Special characters = 1
```

Why this is important: Teaches character classification and conditional counting.

Where it is used: Password validation, form validation, and text analysis.

## Program 9: Count Occurrences of a Character

Question: Write a C program to count how many times a given character occurs in a string.

```
#include <stdio.h>

int main() {
    char str[100], ch;
    int i = 0, count = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    printf("Enter a character: ");
    scanf(" %c", &ch);

    while (str[i] != '\0') {
        if (str[i] == ch) {
            count++;
        }
        i++;
    }

    printf("Occurrences = %d", count);

    return 0;
}
```

Expected Input

```
Enter a string: programming
Enter a character: m
```

Expected Output

```
Occurrences = 2
```

Why this is important: Demonstrates character searching and frequency counting.

Where it is used: Text search, word analysis, and character frequency calculations.

## Program 10: Remove Spaces from a String

Question: Write a C program to remove all spaces from a string.

```
#include <stdio.h>

int main() {
    char str[100];
    int i = 0, j = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0') {
        if (str[i] != ' ' && str[i] != '\n') {
            str[j] = str[i];
            j++;
        }
        i++;
    }

    str[j] = '\0';

    printf("After removing spaces: %s", str);

    return 0;
}
```

Expected Input

```
Enter a sentence: Hello World C
```

Expected Output

```
After removing spaces: HelloWorldC
```

Why this is important: Teaches in-place string modification and maintaining separate read and write indexes.

Where it is used: Text cleaning, data preprocessing, and input normalization.

## Program 11: Count Uppercase and Lowercase Letters

Question: Write a C program to count uppercase and lowercase letters in a string.

```
#include <stdio.h>
#include <ctype.h>

int main() {
    char str[100];
    int i = 0, upper = 0, lower = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0') {
        unsigned char ch = (unsigned char)str[i];

        if (isupper(ch)) {
            upper++;
        } else if (islower(ch)) {
            lower++;
        }

        i++;
    }

    printf("Uppercase = %d\n", upper);
    printf("Lowercase = %d", lower);

    return 0;
}
```

Expected Input

```
Enter a string: Hello WORLD
```

Expected Output

```
Uppercase = 5
Lowercase = 4
```

Why this is important: Teaches character classification using `ctype.h`.

Where it is used: Password analysis, text analytics, and formatting applications.

## Program 12: Compare Two Strings Without `strcmp()`

Question: Write a C program to compare two strings and determine whether they are equal.

```
#include <stdio.h>

int main() {
    char a[100], b[100];
    int i = 0, equal = 1;

    printf("Enter first string: ");
    fgets(a, sizeof(a), stdin);

    printf("Enter second string: ");
    fgets(b, sizeof(b), stdin);

    while (a[i] != '\0' && a[i] != '\n' &&
           b[i] != '\0' && b[i] != '\n') {

        if (a[i] != b[i]) {
            equal = 0;
            break;
        }

        i++;
    }

    if (a[i] != b[i]) {
        equal = 0;
    }

    if (equal) {
        printf("Strings are equal");
    } else {
        printf("Strings are not equal");
    }

    return 0;
}
```

Expected Input

```
Enter first string: Hello
Enter second string: Hello
```

Expected Output

```
Strings are equal
```

Why this is important: Explains how string comparison works character by character.

Where it is used: Login verification, username comparison, and searching records.

## Program 13: Find the Frequency of Each Character

Question: Write a C program to count the frequency of every character in a string, considering uppercase and lowercase letters as different characters.

```
#include <stdio.h>

int main() {
    char str[100];
    int freq[256] = {0};

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    for (int i = 0; str[i] != '\0' && str[i] != '\n'; i++) {
        unsigned char ch = (unsigned char)str[i];
        freq[ch]++;
    }

    printf("Character frequencies:\n");

    for (int i = 0; i < 256; i++) {
        if (freq[i] > 0) {
            printf("%c = %d\n", i, freq[i]);
        }
    }

    return 0;
}
```

Expected Input

```
Enter a string: apple
```

Expected Output

```
Character frequencies:
a = 1
e = 1
l = 1
p = 2
```

Why this is important: Introduces frequency arrays and character-to-index mapping.

Where it is used: Text analytics, word-frequency tools, and basic data compression concepts.

## Program 14: Find the First Occurrence of a Character

Question: Write a C program to find the position of the first occurrence of a character in a string. Use zero-based indexing.

```
#include <stdio.h>

int main() {
    char str[100], ch;
    int i = 0, position = -1;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    printf("Enter character to search: ");
    scanf(" %c", &ch);

    while (str[i] != '\0' && str[i] != '\n') {
        if (str[i] == ch) {
            position = i;
            break;
        }
        i++;
    }

    if (position != -1) {
        printf("Found at index %d", position);
    } else {
        printf("Character not found");
    }

    return 0;
}
```

Expected Input

```
Enter a string: programming
Enter character to search: g
```

Expected Output

```
Found at index 3
```

Why this is important: Demonstrates linear searching in a string and stopping at the first match.

Where it is used: Finding characters, searching text, and locating delimiters.

## Program 15: Replace a Character in a String

Question: Write a C program to replace every occurrence of a given character with another character.

```
#include <stdio.h>

int main() {
    char str[100], oldChar, newChar;
    int i = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    printf("Enter character to replace: ");
    scanf(" %c", &oldChar);

    printf("Enter new character: ");
    scanf(" %c", &newChar);

    while (str[i] != '\0') {
        if (str[i] == oldChar) {
            str[i] = newChar;
        }
        i++;
    }

    printf("Updated string: %s", str);

    return 0;
}
```

Expected Input

```
Enter a string: banana
Enter character to replace: a
Enter new character: o
```

Expected Output

```
Updated string: bonono
```

Why this is important: Teaches updating string elements using indexes.

Where it is used: Text editing, find-and-replace features, and data cleaning.

## Program 16: Count the Number of Spaces

Question: Write a C program to count the number of spaces in a sentence.

```
#include <stdio.h>

int main() {
    char str[100];
    int count = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] == ' ') {
            count++;
        }
    }

    printf("Number of spaces = %d", count);

    return 0;
}
```

Expected Input

```
Enter a sentence: C programming is easy
```

Expected Output

```
Number of spaces = 3
```

Why this is important: Helps understand whitespace and string traversal.

Where it is used: Text formatting, word processing, and sentence analysis.

## Program 17: Reverse Each Word in a Sentence

Question: Write a C program to reverse every word individually while maintaining the original word order.

For example, `Hello World` becomes `olleH dlroW`.

```
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], temp;
    int start = 0, end, i;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    str[strcspn(str, "\n")] = '\0';

    i = 0;

    while (str[i] != '\0') {
        if (str[i] == ' ') {
            end = i - 1;

            while (start < end) {
                temp = str[start];
                str[start] = str[end];
                str[end] = temp;

                start++;
                end--;
            }

            start = i + 1;
        }

        i++;
    }

    end = i - 1;

    while (start < end) {
        temp = str[start];
        str[start] = str[end];
        str[end] = temp;

        start++;
        end--;
    }

    printf("Result: %s", str);

    return 0;
}
```

Expected Input

```
Enter a sentence: Hello World
```

Expected Output

```
Result: olleH dlroW
```

Why this is important: Combines string traversal, word boundaries, and multiple index operations.

Where it is used: Text manipulation and word-processing algorithms.

## Program 18: Check Whether Two Strings Are Anagrams

Question: Write a C program to check whether two lowercase words are anagrams. Anagrams contain exactly the same letters with the same frequencies, but possibly in a different order.

Example: `listen` and `silent`.

```
#include <stdio.h>
#include <string.h>

int main() {
    char a[100], b[100];
    int freq[26] = {0};
    int anagram = 1;

    printf("Enter first lowercase word: ");
    scanf("%99s", a);

    printf("Enter second lowercase word: ");
    scanf("%99s", b);

    if (strlen(a) != strlen(b)) {
        anagram = 0;
    } else {
        for (int i = 0; a[i] != '\0'; i++) {
            if (a[i] < 'a' || a[i] > 'z' ||
                b[i] < 'a' || b[i] > 'z') {
                anagram = 0;
                break;
            }

            freq[a[i] - 'a']++;
            freq[b[i] - 'a']--;
        }

        for (int i = 0; i < 26; i++) {
            if (freq[i] != 0) {
                anagram = 0;
                break;
            }
        }
    }

    if (anagram) {
        printf("Anagram strings");
    } else {
        printf("Not anagram strings");
    }

    return 0;
}
```

Expected Input

```
Enter first lowercase word: listen
Enter second lowercase word: silent
```

Expected Output

```
Anagram strings
```

Why this is important: Introduces character-frequency comparison and array-based string algorithms.

Where it is used: Word games, spelling tools, and text-processing challenges.

## Program 19: Remove Duplicate Characters from a String

Question: Write a C program to remove repeated characters, keeping only their first occurrence.

```
#include <stdio.h>

int main() {
    char str[100];
    int i = 0, j, k;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    while (str[i] != '\0' && str[i] != '\n') {
        j = i + 1;

        while (str[j] != '\0' && str[j] != '\n') {
            if (str[i] == str[j]) {
                k = j;

                while (str[k] != '\0') {
                    str[k] = str[k + 1];
                    k++;
                }
            } else {
                j++;
            }
        }

        i++;
    }

    printf("After removing duplicates: %s", str);

    return 0;
}
```

Expected Input

```
Enter a string: programming
```

Expected Output

```
After removing duplicates: progamin
```

Why this is important: Teaches nested loops and deletion by shifting characters.

Where it is used: Removing duplicate text entries and cleaning data.

## Program 20: Validate a Simple Password

Question: Write a C program to check whether a password contains at least 8 characters, one uppercase letter, one lowercase letter, and one digit.

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char password[100];
    int upper = 0, lower = 0, digit = 0;

    printf("Enter password: ");
    scanf("%99s", password);

    for (int i = 0; password[i] != '\0'; i++) {
        unsigned char ch = (unsigned char)password[i];

        if (isupper(ch)) {
            upper = 1;
        } else if (islower(ch)) {
            lower = 1;
        } else if (isdigit(ch)) {
            digit = 1;
        }
    }

    if (strlen(password) >= 8 && upper && lower && digit) {
        printf("Valid password");
    } else {
        printf("Invalid password");
    }

    return 0;
}
```

Expected Input

```
Enter password: Newton123
```

Expected Output

```
Valid password
```

Why this is important: Combines string length, character classification, and multiple conditions.

Where it is used: Registration forms, password policy checks, and input validation. This is a basic rule checker, not a complete password-security system.

# 15. Array of Strings

So far, we have stored one string in one character array.

But what if we want to store the names of five students?

We can use a two-dimensional character array.

Declaration:

```
char names[5][30];
```

This means:

- 5 strings.
- Each string can hold up to 29 characters plus `'\0'`.

## Example: Store and Display Five Student Names

```
#include <stdio.h>

int main() {
    char names[5][30];

    printf("Enter 5 student names:\n");

    for (int i = 0; i < 5; i++) {
        fgets(names[i], sizeof(names[i]), stdin);
    }

    printf("\nStudent names:\n");

    for (int i = 0; i < 5; i++) {
        printf("%s", names[i]);
    }

    return 0;
}
```

Expected Input

```
Ravi
Sita
Kiran
Arun
Priya
```

Expected Output

```
Student names:
Ravi
Sita
Kiran
Arun
Priya
```

## Visual Representation

names[5][30]

0

Ravi

1

Sita

2

Kiran

3

Arun

4

Priya

Each row represents one independent string with capacity for 30 characters.

## Important Operations on an Array of Strings

- Read multiple names.
- Display all names.
- Search for a particular name.
- Sort names alphabetically.
- Find the longest name.
- Count names starting with a particular letter.

# 16. Sorting Strings Alphabetically

Question: Write a C program to sort five names alphabetically using `strcmp()` and `strcpy()`.

```
#include <stdio.h>
#include <string.h>

int main() {
    char names[5][30] = {
        "Ravi", "Arun", "Kiran", "Sita", "Balu"
    };

    char temp[30];

    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < 4 - i; j++) {
            if (strcmp(names[j], names[j + 1]) > 0) {
                strcpy(temp, names[j]);
                strcpy(names[j], names[j + 1]);
                strcpy(names[j + 1], temp);
            }
        }
    }

    printf("Sorted names:\n");

    for (int i = 0; i < 5; i++) {
        printf("%s\n", names[i]);
    }

    return 0;
}
```

Expected Output

```
Sorted names:
Arun
Balu
Kiran
Ravi
Sita
```

Why this is important: Combines two-dimensional character arrays, string comparison, swapping, and Bubble Sort.

Where it is used: Sorting student names, employee records, and contact lists.

# 17. Difference Between a String and an Array of Strings

| Feature     | Single string    | Array of strings     |
| ----------- | ---------------- | -------------------- |
| Declaration | `char name[30];` | `char names[5][30];` |
| Stores      | One string       | Multiple strings     |
| Indexing    | `name[i]`        | `names[i][j]`        |
| Example     | `"Narendar"`     | `"Ravi", "Sita"`     |

# 18. String Literal vs Character Array

Consider:

```
char name[] = "Newton";
```

This creates a modifiable character array initialized with the characters of the string.

You can modify it:

```
name[0] = 'M';
```

Now the string becomes `Mewton`.

But consider:

```
char *name = "Newton";
```

Here, `name` points to a string literal. Attempting to modify the literal through the pointer causes undefined behavior.

Remember: A character array initialized with a string literal can be modified; a string literal itself must not be modified.

# 19. Common Mistakes in Strings

| Mistake                | Incorrect                                               | Correct                                |
| ---------------------- | ------------------------------------------------------- | -------------------------------------- |
| Missing header         | Using `strlen()` without header                         | Include `string.h`                     |
| Wrong declaration      | `string name;`                                          | `char name[30];`                       |
| Wrong quotes           | `char ch = "A";`                                        | `char ch = 'A';`                       |
| Wrong string quotes    | `char name = 'Hello';`                                  | `char name[] = "Hello";`               |
| Incorrect comparison   | `a == b`                                                | `strcmp(a,b) == 0`                     |
| Missing null character | Character array without `'\0'` when treated as a string | Add a terminating `'\0'`               |
| Unsafe input           | `gets(name)`                                            | `fgets(name, sizeof(name), stdin)`     |
| Unsafe copying         | Copying into a small destination                        | Ensure sufficient destination capacity |

Important safety rules:

1. Never use `gets()`. It is unsafe and was removed from the C standard.
2. Always ensure enough space for the null character.
3. Use a width limit with `%s`, such as `%29s` for a 30-character array.
4. Use `fgets()` for sentences containing spaces.
5. Do not use `strcpy()` or `strcat()` without checking destination capacity.
6. Remember that `strlen()` does not count `'\0'`.
7. Do not compare string contents using `==`.

# 20. Important Viva Questions on Strings

| No. | Question                                                         | Answer                                                                 |
| --- | ---------------------------------------------------------------- | ---------------------------------------------------------------------- |
| 1   | What is a string in C?                                           | A character sequence terminated by `'\0'`.                             |
| 2   | Does C have a string data type?                                  | No. Strings are represented using character arrays.                    |
| 3   | What is the null character?                                      | `'\0'`, which marks the end of a string.                               |
| 4   | Which header contains string functions?                          | `string.h`                                                             |
| 5   | Which function finds string length?                              | `strlen()`                                                             |
| 6   | Which function copies strings?                                   | `strcpy()`                                                             |
| 7   | Which function joins strings?                                    | `strcat()`                                                             |
| 8   | Which function compares strings?                                 | `strcmp()`                                                             |
| 9   | Does `strlen()` count the null character?                        | No.                                                                    |
| 10  | What is the difference between `scanf()` and `fgets()`?          | `scanf("%s")` stops at whitespace; `fgets()` can read spaces.          |
| 11  | What does `strcmp()` return when strings are equal?              | Zero.                                                                  |
| 12  | Can we modify a character array?                                 | Yes, provided it is not a string literal itself.                       |
| 13  | What is the size of `"HELLO"` as an initialized character array? | 6 bytes.                                                               |
| 14  | What is an array of strings?                                     | A collection of strings, commonly represented by a 2D character array. |
| 15  | What does `strchr()` do?                                         | Finds the first occurrence of a character.                             |
| 16  | What does `strstr()` do?                                         | Finds a substring inside another string.                               |
| 17  | Which header contains `toupper()`?                               | `ctype.h`                                                              |
| 18  | What does `'\n'` represent?                                      | Newline character.                                                     |
| 19  | What does `'\0'` represent?                                      | Null character.                                                        |
| 20  | Can a string contain spaces?                                     | Yes. Use an appropriate input method such as `fgets()`.                |

# 21. String Practice Assignments

These 30 questions can be used as lab assignments or coding practice.

## Level 1 – Basic String Programs

1. Read and display a string.
2. Find the length without using `strlen()`.
3. Count vowels and consonants.
4. Count uppercase and lowercase characters.
5. Count digits and special characters.
6. Count the number of words.
7. Reverse a string.
8. Check whether a string is a palindrome.
9. Convert lowercase letters into uppercase.
10. Convert uppercase letters into lowercase.

## Level 2 – Intermediate String Programs

11. Copy one string into another without `strcpy()`.
12. Join two strings without `strcat()`.
13. Compare two strings without `strcmp()`.
14. Count the occurrences of a given character.
15. Find the first occurrence of a character.
16. Replace a character in a string.
17. Remove all spaces from a sentence.
18. Remove duplicate characters.
19. Find the frequency of each character.
20. Check whether two strings are anagrams.

## Level 3 – Advanced String Programs

21. Reverse each word in a sentence.
22. Reverse the order of words in a sentence.
23. Find the longest word in a sentence.
24. Find the shortest word in a sentence.
25. Sort characters alphabetically.
26. Sort an array of student names.
27. Search for a name in an array of strings.
28. Count the number of occurrences of a word in a sentence.
29. Check whether a string is a valid basic password.
30. Remove a particular word from a sentence.

# 22. Interactive Knowledge Check

Test your understanding of C strings.

C Strings Quiz

0/7 answered

1\. What marks the end of a C string?

\n

\0

\t

EOF

2\. Which header file contains strlen()?

stdio.h

stdlib.h

string.h

ctype.h

3\. What is strlen("APPLE")?

4

5

6

7

4\. Which function compares two strings?

strcpy()

strcat()

strcmp()

strlen()

5\. Which function can read a full name containing spaces?

scanf("%s")

fgets()

strlen()

strchr()

6\. What is the size of char s[] = "CAT"?

3

4

5

2

7\. Which function converts a lowercase character to uppercase?

tolower()

isalpha()

toupper()

isdigit()

Submit answers

# 23. Recommended Teaching Sequence

1. String fundamentals

   Character vs string, null character, declaration, initialization.

   Covered
2. String input and output

   `scanf()`, `fgets()`, `printf()`, and `puts()`.

   Covered
3. String library functions

   `strlen()`, `strcpy()`, `strcat()`, `strcmp()`, `strchr()`, `strstr()`.

   Covered
4. Character processing

   `ctype.h`, vowels, consonants, digits, and special characters.

   Covered
5. String manipulation

   Reversing, copying, joining, comparing, and replacing.

   Covered
6. Arrays of strings

   Multiple names, searching, and sorting.

   Covered
7. Advanced string problems

   Anagrams, word processing, password validation, and frequency counting.

   Covered

Important connection to the next topic – Pointers:

A string's array name is closely related to pointers. For example:

```
char name[] = "Newton";

printf("%c\n", name[0]);
printf("%c\n", *(name + 0));
```

Both print:

```
N
```

This connection will help students understand pointers, character pointers, pointer arithmetic, and dynamic memory allocation.

My recommendation: Before moving to pointers, make sure students can independently write these five programs:

1. Find string length without `strlen()`.
2. Reverse a string.
3. Check palindrome.
4. Count vowels and consonants.
5. Compare two strings without `strcmp()`.

These five problems provide a strong foundation in string processing.




# C Programming – Strings (Complete Teaching Notes for 1st-Year B.Tech Students)



Beginner Level

Concepts + Real-Time Examples + Programs



Subject: Programming for Problem Solving using C\
Topic: Strings in C Programming

## 1. Introduction – What is a String?

Let's start the class with a simple question.

Trainer asks students:

Imagine you are developing a college admission application. You need to store the following information about a student:

- Roll Number: 101
- Age: 18
- Marks: 95.5
- Name: Narendar

Now, think about this:

- Can we store the roll number using an integer? Yes.
- Can we store age using an integer? Yes.
- Can we store marks using a float? Yes.
- But how do we store the student's name?

We cannot store a complete name in a single `char` variable because `char` stores only one character.

For example:

```
char name = 'N';
```

This stores only one character: `N`.

But what if we want to store `Narendar`?

This is where Strings come into the picture.

### Definition of String

A string in C is a sequence of characters terminated by a special character called the null character (`'\0'`).

In simple words:

A string is a collection of characters used to represent text such as names, addresses, passwords, messages, and email IDs.

Examples:

```
Narendar
Hello
Hyderabad
Computer Science
12345
```

Remember: C does not have a separate built-in string data type like Python or Java. Strings are represented using character arrays.

## 2. Understanding Characters and Strings

Before learning strings, students must understand the difference between a character and a string.

| Character            | String                     |
| -------------------- | -------------------------- |
| Stores one character | Stores multiple characters |
| Uses single quotes   | Uses double quotes         |
| Uses `char`          | Uses `char` array          |
| Example: `'A'`       | Example: `"Apple"`         |

Example:

```
char ch = 'A';

char name[] = "Apple";
```

Explain this real-time example:

Think about a mobile contact list.

- `'R'` represents one letter.
- `"Ramesh"` represents a complete contact name.

## 3. How are Strings Stored in C?

This is one of the most important concepts.

Consider:

```
char name[] = "RAM";
```

Ask students:

How many characters are there in RAM?

Answer: 3.

But how many memory locations are required?

Answer: 4.

Why?

Because C automatically adds a special character called the null character (`'\0'`) at the end of the string.

Memory representation of `"RAM"`

# R

Index 0

# A

Index 1

# M

Index 2

# \0

Index 3

Four consecutive character-array locations

Total memory = 4 bytes (assuming 1 byte per char)

### What is Null Character (`'\0'`)?

Definition: The null character is a special character with ASCII value 0 that indicates the end of a string in C.

Important points:

- It is represented as `'\0'`.
- It is automatically added when a string is initialized using a string literal.
- It tells the compiler/library functions where the string ends.
- It is not the same as the character `'0'`.

Example:

```
char name[] = {'R', 'A', 'M', '\0'};
```

This is also a valid way of creating a string.

Ask students:

What happens if we remove `'\0'`?

Answer: The character array is no longer a properly terminated C string. String functions may continue reading beyond the array, causing undefined behavior.

## 4. Declaration and Initialization of Strings

There are multiple ways to declare and initialize strings.

### Method 1: Using a String Literal

```
char name[] = "Narendar";
```

Here:

- `char` – data type.
- `name` – array name.
- – array size is automatically determined.
- `"Narendar"` – string value.

The compiler allocates 9 characters, including `'\0'`.

### Method 2: Specifying Array Size

```
char name[20] = "Narendar";
```

Here, 20 character locations are allocated, but only the first 9 are needed for the string and its terminator.

### Method 3: Character-by-Character Initialization

```
char name[] = {'R', 'A', 'M', '\0'};
```

### Method 4: Empty String

```
char name[20] = "";
```

This initializes the string as empty.

### Important Difference

```
char name[] = "Hello";   // Valid
char name[5] = "Hello";  // Not enough space for '\0'
char name[6] = "Hello";  // Valid
```

For a string containing `n` visible characters, you need at least `n + 1` array elements.

## 5. How to Read and Display Strings in C

Now students know how to create a string. The next question is:

How do we take a name from the user and display it?

C provides different input/output methods for strings.

### A. Using `scanf()`

Syntax:

```
scanf("%s", name);
```

Example:

```
#include <stdio.h>

int main()
{
    char name[30];

    printf("Enter your name: ");
    scanf("%29s", name);

    printf("Your name is: %s", name);

    return 0;
}
```

Expected output:

```
Enter your name: Narendar
Your name is: Narendar
```

Explain:

- `%s` is the format specifier used to read a string.
- `name` is the character array.
- We use `%29s` to limit input to 29 characters, leaving one location for `'\0'`.

Important limitation of scanf():

What happens if the student enters:

```
Paindla Narendar Reddy
```

Output:

```
Paindla
```

Why?

Because `scanf("%s", name)` stops reading when it encounters whitespace (space, tab, or newline).

### B. Using `fgets()`

To read a complete name containing spaces, use `fgets()`.

Syntax:

```
fgets(string_name, size, stdin);
```

Example:

```
#include <stdio.h>

int main()
{
    char name[50];

    printf("Enter your full name: ");
    fgets(name, sizeof(name), stdin);

    printf("Your full name is: %s", name);

    return 0;
}
```

Expected output:

```
Enter your full name: Paindla Narendar Reddy
Your full name is: Paindla Narendar Reddy
```

Explain each argument:

| Argument       | Meaning                     |
| -------------- | --------------------------- |
| `name`         | Array where input is stored |
| `sizeof(name)` | Maximum buffer size         |
| `stdin`        | Standard input (keyboard)   |

Important: `fgets()` may also store the newline character `'\n'` if there is room in the array.

### C. Using `printf()`

Syntax:

```
printf("%s", name);
```

Example:

```
#include <stdio.h>

int main()
{
    char city[] = "Hyderabad";

    printf("City: %s", city);

    return 0;
}
```

### D. Using `puts()`

`puts()` displays a string and automatically moves the cursor to the next line.

Example:

```
#include <stdio.h>

int main()
{
    char message[] = "Welcome to C Programming";

    puts(message);

    return 0;
}
```

Expected output:

```
Welcome to C Programming
```

### Comparison of String Input/Output Functions

| Function             | Purpose                          |
| -------------------- | -------------------------------- |
| `scanf("%s", name)`  | Reads a word                     |
| `fgets()`            | Reads a line, including spaces   |
| `printf("%s", name)` | Displays a string                |
| `puts()`             | Displays a string with a newline |

## 6. String Length – `strlen()`

Now let's move to an interesting real-time example.

Scenario:

You are developing a registration page. The application requires users to enter a password containing at least 8 characters.

How can we count the number of characters in the password?

We use `strlen()`.

### Definition

`strlen()` is a predefined string-handling function used to calculate the number of characters in a string, excluding the null character (`'\0'`).

Header file:

```
#include <string.h>
```

Syntax:

```
strlen(string_name);
```

Example:

```
#include <stdio.h>
#include <string.h>

int main()
{
    char password[] = "hello123";

    printf("Password length: %zu", strlen(password));

    return 0;
}
```

Expected output:

```
Password length: 8
```

Remember:

- `strlen()` counts characters.
- It does not count `'\0'`.
- Its return type is `size_t`.

### Real-Time Applications

- Checking password length.
- Validating username length.
- Counting characters in a message.
- Checking input length in registration forms.

### Program 1: Find the Length of a String Without Using `strlen()`

Question: Write a C program to count the number of characters in a string without using the predefined `strlen()` function.

Logic:

1. Read a string.
2. Initialize `count = 0`.
3. Traverse each character until `'\0'`.
4. Increment the count.
5. Print the result.

```
#include <stdio.h>

int main()
{
    char str[100];
    int i = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    while (str[i] != '\0')
    {
        i++;
    }

    printf("Length of string = %d", i);

    return 0;
}
```

Expected output:

```
Enter a string: Computer
Length of string = 8
```

Trainer explanation: Here, we are manually counting every character until we reach the null character. This helps students understand how `strlen()` works internally.

## 7. Copying Strings – `strcpy()`

Real-time example:

Imagine you are developing a student management application.

You have one variable containing a student's name. Now you want to copy that name into another variable.

How can you do that?

We use `strcpy()`.

### Definition

`strcpy()` is a predefined string function used to copy the contents of one string into another string.

Header file:

```
#include <string.h>
```

Syntax:

```
strcpy(destination, source);
```

Example:

```
#include <stdio.h>
#include <string.h>

int main()
{
    char source[] = "Narendar";
    char destination[30];

    strcpy(destination, source);

    printf("Source: %s\n", source);
    printf("Destination: %s", destination);

    return 0;
}
```

Expected output:

```
Source: Narendar
Destination: Narendar
```

Explain:

- `source` contains the original string.
- `destination` receives the copied string.
- Destination must have enough space for all characters, including `'\0'`.

### Program 2: Copy a String Without Using `strcpy()`

```
#include <stdio.h>

int main()
{
    char source[100];
    char destination[100];
    int i = 0;

    printf("Enter a string: ");
    scanf("%99s", source);

    while (source[i] != '\0')
    {
        destination[i] = source[i];
        i++;
    }

    destination[i] = '\0';

    printf("Copied string: %s", destination);

    return 0;
}
```

Expected output:

```
Enter a string: Programming
Copied string: Programming
```

Important teaching point: Why do we write `destination[i] = '\0';` after the loop?

Because we must terminate the copied character array properly to make it a valid C string.

## 8. Joining Strings – `strcat()`

Real-time example:

Suppose you are creating a full-name generator.

First name:

```
Narendar
```

Last name:

```
Reddy
```

Required output:

```
NarendarReddy
```

How can we combine two strings?

We use `strcat()`.

### Definition

`strcat()` is a predefined string function used to append one string to the end of another string.

Syntax:

```
strcat(destination, source);
```

Example:

```
#include <stdio.h>
#include <string.h>

int main()
{
    char first[50] = "Narendar";
    char last[] = "Reddy";

    strcat(first, last);

    printf("Full name: %s", first);

    return 0;
}
```

Expected output:

```
Full name: NarendarReddy
```

If we want a space between the names:

```
char first[50] = "Narendar ";
char last[] = "Reddy";

strcat(first, last);
```

Output:

```
Narendar Reddy
```

Important: The destination array must have sufficient space for the original string, appended string, and terminating null character.

### Program 3: Concatenate Two Strings Without Using `strcat()`

```
#include <stdio.h>

int main()
{
    char str1[100], str2[50];
    int i = 0, j = 0;

    printf("Enter first string: ");
    scanf("%99s", str1);

    printf("Enter second string: ");
    scanf("%49s", str2);

    while (str1[i] != '\0')
    {
        i++;
    }

    while (str2[j] != '\0')
    {
        str1[i] = str2[j];
        i++;
        j++;
    }

    str1[i] = '\0';

    printf("Combined string: %s", str1);

    return 0;
}
```

Expected output:

```
Enter first string: Hello
Enter second string: World
Combined string: HelloWorld
```

## 9. Comparing Strings – `strcmp()`

Real-time example: Login System

Imagine you are developing a login application.

The registered username is:

```
admin
```

The user enters:

```
admin
```

The application must check whether both strings are equal.

Can we use this?

```
if (str1 == str2)
```

No! In C, this compares the array expressions after pointer conversion, not the string contents.

Instead, we use `strcmp()`.

### Definition

`strcmp()` is a predefined string function used to compare two strings lexicographically (based on character values).

Syntax:

```
strcmp(string1, string2);
```

Return values:

| Return value   | Meaning                 |
| -------------- | ----------------------- |
| `0`            | Both strings are equal  |
| Negative value | First string is smaller |
| Positive value | First string is greater |

Note: The exact nonzero value is not guaranteed to be `-1` or `1`.

Example:

```
#include <stdio.h>
#include <string.h>

int main()
{
    char username[30] = "admin";
    char input[30];

    printf("Enter username: ");
    scanf("%29s", input);

    if (strcmp(username, input) == 0)
    {
        printf("Login successful");
    }
    else
    {
        printf("Invalid username");
    }

    return 0;
}
```

Expected output 1:

```
Enter username: admin
Login successful
```

Expected output 2:

```
Enter username: student
Invalid username
```

Trainer explanation: `strcmp()` is case-sensitive. For example, `"Admin"` and `"admin"` are different strings.

### Program 4: Compare Two Strings Without Using `strcmp()`

```
#include <stdio.h>

int main()
{
    char str1[100], str2[100];
    int i = 0, flag = 1;

    printf("Enter first string: ");
    scanf("%99s", str1);

    printf("Enter second string: ");
    scanf("%99s", str2);

    while (str1[i] != '\0' || str2[i] != '\0')
    {
        if (str1[i] != str2[i])
        {
            flag = 0;
            break;
        }

        i++;
    }

    if (flag == 1)
        printf("Strings are equal");
    else
        printf("Strings are not equal");

    return 0;
}
```

Expected output:

```
Enter first string: Apple
Enter second string: Apple
Strings are equal
```

## 10. Important String Functions in C

Introduce these functions after students understand the four main functions.

All these functions are declared in:

```
#include <string.h>
```

| Function   | Purpose                               | Example             |
| ---------- | ------------------------------------- | ------------------- |
| `strlen()` | Finds string length                   | `strlen(str)`       |
| `strcpy()` | Copies a string                       | `strcpy(a,b)`       |
| `strcat()` | Joins strings                         | `strcat(a,b)`       |
| `strcmp()` | Compares strings                      | `strcmp(a,b)`       |
| `strchr()` | Finds first occurrence of a character | `strchr(str,'a')`   |
| `strstr()` | Finds a substring                     | `strstr(str,"cat")` |

A few more examples:

A. `strchr()` – Search for a Character

```
char str[] = "Programming";
char *result = strchr(str, 'g');
```

It returns a pointer to the first occurrence of `'g'`, or `NULL` if not found.

B. `strstr()` – Search for a Word or Substring

```
char str[] = "I love programming";
char *result = strstr(str, "program");
```

It finds the first occurrence of `"program"` inside the string.

## 11. Traversing a String Using a Loop

This is an important concept because students will use loops to solve most string problems.

Definition: String traversal means visiting each character of a string one by one until the null character (`'\0'`) is reached.

Example:

```
#include <stdio.h>

int main()
{
    char str[] = "HELLO";
    int i;

    for (i = 0; str[i] != '\0'; i++)
    {
        printf("%c\n", str[i]);
    }

    return 0;
}
```

Expected output:

```
H
E
L
L
O
```

Explain the condition:

```
str[i] != '\0'
```

This means continue the loop until the end of the string is reached.

### Real-time applications

- Processing each letter in a username.
- Counting vowels in a message.
- Checking whether a password contains special characters.
- Searching for a particular character.
- Reversing a word.

## 12. Important String Programs for Beginners

Now students should start implementing string operations using loops and conditions.

### Program 5: Count Vowels and Consonants

Question: Write a C program to count the number of vowels and consonants in a given string.

Real-time application: Text analysis and language-processing applications.

```
#include <stdio.h>

int main()
{
    char str[100];
    int i, vowels = 0, consonants = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        char ch = str[i];

        if (ch >= 'A' && ch <= 'Z')
            ch = ch + 32;

        if (ch >= 'a' && ch <= 'z')
        {
            if (ch == 'a' || ch == 'e' || ch == 'i' ||
                ch == 'o' || ch == 'u')
                vowels++;
            else
                consonants++;
        }
    }

    printf("Vowels = %d\n", vowels);
    printf("Consonants = %d", consonants);

    return 0;
}
```

Expected output:

```
Enter a string: Education
Vowels = 5
Consonants = 4
```

### Program 6: Reverse a String

Question: Write a C program to reverse a string without using predefined string functions.

Real-time application: Palindrome checking and text-processing operations.

```
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100], temp;
    int i, j;

    printf("Enter a string: ");
    scanf("%99s", str);

    j = strlen(str) - 1;

    for (i = 0; i < j; i++, j--)
    {
        temp = str[i];
        str[i] = str[j];
        str[j] = temp;
    }

    printf("Reversed string: %s", str);

    return 0;
}
```

Expected output:

```
Enter a string: HELLO
Reversed string: OLLEH
```

Explain the swapping process:

Initially:

```
H E L L O
```

Swap first and last:

```
O E L L H
```

Swap second and fourth:

```
O L L E H
```

Result:

```
OLLEH
```

### Program 7: Check Whether a String Is a Palindrome

Question: Write a C program to check whether a given string is a palindrome.

Definition: A palindrome is a word that reads the same from left to right and right to left.

Examples:

- MADAM
- LEVEL
- MALAYALAM
- RADAR

Real-time application: Word-processing and text-validation problems.

```
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100];
    int i, j, flag = 1;

    printf("Enter a string: ");
    scanf("%99s", str);

    j = strlen(str) - 1;

    for (i = 0; i < j; i++, j--)
    {
        if (str[i] != str[j])
        {
            flag = 0;
            break;
        }
    }

    if (flag == 1)
        printf("Palindrome");
    else
        printf("Not a palindrome");

    return 0;
}
```

Expected output:

```
Enter a string: MADAM
Palindrome
```

### Program 8: Count Digits, Alphabets and Special Characters

Question: Write a C program to count alphabets, digits and special characters in a string.

Real-time application: Password validation.

```
#include <stdio.h>

int main()
{
    char str[100];
    int i, alphabets = 0, digits = 0, special = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        if ((str[i] >= 'A' && str[i] <= 'Z') ||
            (str[i] >= 'a' && str[i] <= 'z'))
            alphabets++;

        else if (str[i] >= '0' && str[i] <= '9')
            digits++;

        else
            special++;
    }

    printf("Alphabets = %d\n", alphabets);
    printf("Digits = %d\n", digits);
    printf("Special characters = %d", special);

    return 0;
}
```

Expected output:

```
Enter a string: Hello@123
Alphabets = 5
Digits = 3
Special characters = 1
```

### Program 9: Convert Lowercase to Uppercase

Question: Write a C program to convert lowercase letters into uppercase letters.

Real-time application: Search systems that normalize text before comparison.

```
#include <stdio.h>

int main()
{
    char str[100];
    int i;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] >= 'a' && str[i] <= 'z')
        {
            str[i] = str[i] - 32;
        }
    }

    printf("Uppercase string: %s", str);

    return 0;
}
```

Expected output:

```
Enter a string: hello
Uppercase string: HELLO
```

Explain the ASCII concept:

- `a` has ASCII value 97.
- `A` has ASCII value 65.
- Difference = 32.

Therefore, subtracting 32 converts a lowercase English letter to uppercase in the ASCII character set.

### Program 10: Count the Number of Words in a Sentence

Question: Write a C program to count the number of words in a sentence.

Real-time application: Word counters in document editors.

```
#include <stdio.h>

int main()
{
    char str[200];
    int i, words = 0, inWord = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] != ' ' && str[i] != '\n' && str[i] != '\t')
        {
            if (inWord == 0)
            {
                words++;
                inWord = 1;
            }
        }
        else
        {
            inWord = 0;
        }
    }

    printf("Number of words = %d", words);

    return 0;
}
```

Expected output:

```
Enter a sentence: I love C programming
Number of words = 4
```

## 13. Difference Between Character Array and String

This is an important conceptual question for examinations.

| Character Array                             | String                                                   |
| ------------------------------------------- | -------------------------------------------------------- |
| Array of characters                         | Character array terminated by `'\0'`                     |
| May not contain null character              | Must contain null terminator                             |
| Can store individual characters             | Represents text                                          |
| Cannot always be used with string functions | Can be used with string functions if properly terminated |

Example:

```
char a[3] = {'A', 'B', 'C'};
```

This is a character array, but it is not a properly null-terminated string.

```
char b[4] = {'A', 'B', 'C', '\0'};
```

This is a valid C string.

## 14. Common Mistakes Students Should Avoid

| Mistake                                            | Correct approach                                               |
| -------------------------------------------------- | -------------------------------------------------------------- |
| Using single quotes for a string                   | Use double quotes                                              |
| Forgetting `'\0'`                                  | Ensure proper termination                                      |
| Using `==` to compare string contents              | Use `strcmp()`                                                 |
| Using `scanf("%s")` for full names                 | Use `fgets()`                                                  |
| Providing insufficient array size                  | Allocate enough memory                                         |
| Forgetting `#include `                             | Include `<string.h>` for string functions                      |
| Using `strcpy()` without checking destination size | Ensure sufficient destination capacity                         |
| Using `gets()`                                     | Never use it; it is unsafe and removed from modern C standards |

### Important difference: `'0'` vs `'\0'`

| `'0'`             | `'\0'`            |
| ----------------- | ----------------- |
| Character zero    | Null character    |
| ASCII value 48    | ASCII value 0     |
| Visible character | String terminator |

## 15. Real-Time Applications of Strings

Explain to students where strings are actually used in software development.

[User Login Screen Page Interface Concept Illustration Vector](https://images.openai.com/static-rsc-4/AIwCpfm_dKP_DNipyG2NtVmKgqHvcp6VLkkD5pr8binBEyD8eRbHXJKKuVpYlMmwGaMtD2lslTCudTCBhfpzgfRFZB_PrRK9i8noQHPxtzn4Oz241g5QhbHtmXUHw98ZIiAjrgqrKqoU6KbczltJlRil8nDVDqoIDn3TxLZ2RBU_Fp6QCGcmWOKL6jyndaET?purpose=inline)

1\. Login Applications

Store and compare usernames and passwords.

Functions: `strcmp()`, `strlen()`

[School Management website and Student Portal UI Kit by \~ EpicPxls](https://images.openai.com/static-rsc-4/kykYpbayg-1TJ_gc_6__3Fnt6yZHqX7ZRROaavO0_7GUvz0lCelZsFcY9iA8eQ_7Wx3J3yQpLurMLcCZv18c9J3jX-DXTlFvCDkU_WW3LsdnF0sOMNKewQkLD1w2DsmGzDDfnL2I-dCGANw2DE76ZOLdRNqz5RLXVi63E0E7rz4?purpose=inline)

2\. Student Management Systems

Store student names, addresses and email IDs.

Concepts: Character arrays, `fgets()`, `strcpy()`

[Chat UI Mobile :: Behance](https://images.openai.com/static-rsc-4/oGcxojdRV-uwU7luhA6g-sCedpT1JE6XP85aq-Mcqnr2IvAQGgEkx-d7OjS1gnJuNuDJX01CfUghpfJZyhGjvXCMNzx2cam4PcMWDS_B8qdxJMJEOCjjh-DSP-bm8nC9rcxz2suDvIj1gRPnnpprESduX1rGqtg6lp-dZQiXmeM?purpose=inline)

3\. Chat Applications

Store and process messages sent by users.

Concepts: String traversal, concatenation, length

[Shipro - Fast Sourcing & Delivery from China to Nigeria](https://images.openai.com/static-rsc-4/I1zMGb6dYOqvGdYcBj9l5gCYezGp9xLRS_ygORiVLeUYGSTWu0lUsvNmbZc-iBP_Oh_vVM4klPA8lU80O6DBPJomqdMcldoEYl-uTDPiFQsH6UtPxm1DZujnrw4Kokaq-EYr38VTdbaT_NpLOddASwEsdwd8AoJ8R409fcgfioE?purpose=inline)

4\. E-Commerce Applications

Search products using names and keywords.

Functions: `strcmp()`, `strstr()`

[User Onboarding - Blotout Cloud Docs](https://images.openai.com/static-rsc-4/9A2if0w3mFo0kiOwuqPIW3M1_-aQWDNQl_w5qiArEXyhWbA3eYznI8rzUobvyl5zmrPy2WbXLPdAhEC5yU2lqlGCozAQfqOzSW75gdRKXXnEcpRulaaw2Dcrh3oaFL0GN1GVvZztDfoK68ZLAX26KW7-XpOhtMHD0UqrrbGPuJs?purpose=inline)

5\. Registration Systems

Validate names, usernames and other text inputs.

Functions: `strlen()`, character checking

## 16. Practice Questions for Students

After completing the concepts and demonstrations, assign these programs.

Lab Practice

| No. | Programming question                           | Difficulty |
| --- | ---------------------------------------------- | ---------- |
| 1   | Read and display a string                      | Easy       |
| 2   | Find string length without `strlen()`          | Easy       |
| 3   | Count vowels and consonants                    | Easy       |
| 4   | Count uppercase and lowercase letters          | Easy       |
| 5   | Convert lowercase to uppercase                 | Easy       |
| 6   | Convert uppercase to lowercase                 | Easy       |
| 7   | Reverse a string                               | Medium     |
| 8   | Check palindrome                               | Medium     |
| 9   | Copy a string without `strcpy()`               | Medium     |
| 10  | Concatenate two strings without `strcat()`     | Medium     |
| 11  | Compare two strings without `strcmp()`         | Medium     |
| 12  | Count alphabets, digits and special characters | Medium     |
| 13  | Count words in a sentence                      | Medium     |
| 14  | Find the frequency of a particular character   | Medium     |
| 15  | Find the first occurrence of a character       | Medium     |
| 16  | Remove spaces from a string                    | Medium     |
| 17  | Count occurrences of a given character         | Medium     |
| 18  | Find the longest word in a sentence            | Advanced   |
| 19  | Check whether two strings are anagrams         | Advanced   |
| 20  | Find duplicate characters in a string          | Advanced   |

## 17. Quick Revision – Questions to Ask in Class

Use these questions to check whether students understood the concepts.

Strings – Mini Test

6 MCQs

1\. Which character indicates the end of a string in C?

\n

\0

\t

\b

2\. What is the output of strlen("HELLO")?

6

5

4

7

3\. Which function is used to copy a string?

strcat()

strcmp()

strcpy()

strlen()

4\. What does strcmp() return when two strings are equal?

1

-1

0

5

5\. Which function can read a full name containing spaces?

scanf("%s")

fgets()

strlen()

strcpy()

6\. How many array locations are needed for the string "CAT"?

3

2

4

5

Submit answers

## 18. Suggested Teaching Sequence

For first-year students who are completely new to programming, don't introduce all string functions at once. Teach them in this order.

| Class   | Topics                                                                   | Practical activity              |
| ------- | ------------------------------------------------------------------------ | ------------------------------- |
| Class 1 | Introduction, character vs string, null character, memory representation | Declare and print strings       |
| Class 2 | String input/output, `scanf()`, `fgets()`, `puts()`                      | Read full name and display      |
| Class 3 | String traversal, `strlen()`                                             | Count characters                |
| Class 4 | `strcpy()`, `strcat()`                                                   | Copy and join names             |
| Class 5 | `strcmp()`                                                               | Simple username comparison      |
| Class 6 | String operations using loops                                            | Vowels, reverse, palindrome     |
| Class 7 | Advanced string problems                                                 | Word count, frequency, anagrams |

## 19. Important Examination Questions

Short-answer questions (2 marks)

1. Define a string in C.
2. What is a null character?
3. Differentiate between a character and a string.
4. What is the purpose of `strlen()`?
5. What is the use of `strcpy()`?
6. What is the difference between `scanf()` and `fgets()`?
7. Why do we use `strcmp()`?
8. What is string concatenation?

Long-answer questions (5–10 marks)

1. Explain string declaration and initialization with examples.
2. Explain the memory representation of strings in C.
3. Explain the different string handling functions with examples.
4. Write a program to reverse a string.
5. Write a program to check whether a string is a palindrome.
6. Write a program to count vowels and consonants.
7. Write a program to compare two strings without using predefined functions.

## 20. How I Recommend Starting Your First Strings Class

Start with a small real-world story rather than immediately writing syntax on the board.

Story: Building a College Student Registration System

Tell your students:

"Imagine our college wants to develop a student registration application. Every student needs to enter their name, roll number, branch and email ID."

Write this on the board:

```
Student Details

Roll Number : 101
Name        : Narendar Reddy
Branch      : CSE
Email       : narendar@gmail.com
```

Ask students:

1. Which data type stores the roll number?
2. Which data type stores the name?
3. Can we store the name in a single `char`?
4. How can we store the complete name?

Then introduce character arrays and strings.

Your first practical demonstration should be this:

```
#include <stdio.h>

int main()
{
    char name[50];

    printf("Enter student name: ");
    fgets(name, sizeof(name), stdin);

    printf("\nStudent Registration");
    printf("\n-------------------");
    printf("\nName: %s", name);

    return 0;
}
```

This gives students an immediate understanding of why strings are needed.

My teaching recommendation: Spend more time on the null character, character-array indexing, and string traversal. These three concepts are the foundation for almost every string program. Don't rush into `strcpy()`, `strcat()` and `strcmp()` before students understand how characters are stored and accessed.

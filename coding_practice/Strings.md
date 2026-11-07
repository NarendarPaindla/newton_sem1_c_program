# C Programming – Strings: 30 Hands-on Programs

Important: Save each program separately and execute it in Dev-C++.

## 1. Find the Length of a String Without Using `strlen()`

Question: Write a C program to read a string and find its length without using the built-in `strlen()` function.

Concept: String traversal and null character (`'\0'`).

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

    printf("Length of the string = %d", i);

    return 0;
}
```

Expected Output:

```
Enter a string: Hello
Length of the string = 5
```

Why is this important? It teaches how a string is stored and how to identify its ending.

Where is it used? Counting characters in usernames, IDs and short text inputs.

## 2. Count Vowels and Consonants in a String

Question: Write a C program to count the number of vowels and consonants in a given string.

Concept: Character checking using conditions.

```
#include <stdio.h>
#include <ctype.h>

int main()
{
    char str[100];
    int i, vowels = 0, consonants = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        char ch = tolower((unsigned char)str[i]);

        if (ch >= 'a' && ch <= 'z')
        {
            if (ch == 'a' || ch == 'e' ||
                ch == 'i' || ch == 'o' || ch == 'u')
            {
                vowels++;
            }
            else
            {
                consonants++;
            }
        }
    }

    printf("Vowels = %d\n", vowels);
    printf("Consonants = %d\n", consonants);

    return 0;
}
```

Expected Output:

```
Enter a string: Education
Vowels = 5
Consonants = 4
```

Why is this important? Students learn how to process each character based on its value.

Where is it used? Text analysis, language-processing applications and basic text statistics.

## 3. Reverse a String

Question: Write a C program to reverse a given string without using the built-in string functions.

Concept: Finding the length and swapping characters.

```
#include <stdio.h>

int main()
{
    char str[100], temp;
    int i, length = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    while (str[length] != '\0')
    {
        length++;
    }

    for (i = 0; i < length / 2; i++)
    {
        temp = str[i];
        str[i] = str[length - 1 - i];
        str[length - 1 - i] = temp;
    }

    printf("Reversed string = %s", str);

    return 0;
}
```

Expected Output:

```
Enter a string: HELLO
Reversed string = OLLEH
```

Why is this important? It teaches indexing, swapping and working with characters from both ends.

Where is it used? Text manipulation, palindrome checking and certain data-processing tasks.

## 4. Check Whether a String Is a Palindrome

Question: Write a C program to check whether a given string is a palindrome.

A palindrome is a word that reads the same forward and backward.

Examples: `MADAM`, `LEVEL`, `MALAYALAM`.

Concept: Comparing characters from the beginning and end.

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char str[100];
    int i, j, flag = 1;

    printf("Enter a string: ");
    scanf("%99s", str);

    i = 0;
    j = strlen(str) - 1;

    while (i < j)
    {
        if (tolower((unsigned char)str[i]) !=
            tolower((unsigned char)str[j]))
        {
            flag = 0;
            break;
        }

        i++;
        j--;
    }

    if (flag == 1)
        printf("Palindrome");
    else
        printf("Not a palindrome");

    return 0;
}
```

Expected Output 1:

```
Enter a string: MADAM
Palindrome
```

Expected Output 2:

```
Enter a string: HELLO
Not a palindrome
```

Why is this important? It teaches two-pointer comparison and conditional logic.

Where is it used? Text validation and pattern-based programming problems.

## 5. Convert a String into Uppercase

Question: Write a C program to convert all lowercase letters in a string into uppercase.

Concept: Character conversion using `toupper()` from `ctype.h`.

```
#include <stdio.h>
#include <ctype.h>

int main()
{
    char str[100];
    int i;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        str[i] = toupper((unsigned char)str[i]);
    }

    printf("Uppercase string = %s", str);

    return 0;
}
```

Expected Output:

```
Enter a string: hello
Uppercase string = HELLO
```

Why is this important? It teaches how to modify individual characters in a string.

Where is it used? Converting usernames, normalizing text and formatting input.

## 6. Convert a String into Lowercase

Question: Write a C program to convert all uppercase letters in a string into lowercase.

Concept: Character conversion using `tolower()`.

```
#include <stdio.h>
#include <ctype.h>

int main()
{
    char str[100];
    int i;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        str[i] = tolower((unsigned char)str[i]);
    }

    printf("Lowercase string = %s", str);

    return 0;
}
```

Expected Output:

```
Enter a string: HELLO
Lowercase string = hello
```

Why is this important? It helps students understand case conversion and string modification.

Where is it used? Search functionality, email validation and case-insensitive comparisons.

## 7. Count Alphabets, Digits and Special Characters

Question: Write a C program to count the number of alphabets, digits and special characters in a string.

Concept: Character classification using `isalpha()`, `isdigit()` and `isalnum()`.

```
#include <stdio.h>
#include <ctype.h>

int main()
{
    char str[100];
    int i, alphabets = 0, digits = 0, special = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (isalpha((unsigned char)str[i]))
            alphabets++;
        else if (isdigit((unsigned char)str[i]))
            digits++;
        else
            special++;
    }

    printf("Alphabets = %d\n", alphabets);
    printf("Digits = %d\n", digits);
    printf("Special characters = %d\n", special);

    return 0;
}
```

Expected Output:

```
Enter a string: Hello@123
Alphabets = 5
Digits = 3
Special characters = 1
```

Why is this important? It teaches character classification.

Where is it used? Password validation, input validation and security checks.

## 8. Count the Occurrences of a Character in a String

Question: Write a C program to read a string and a character, then count how many times that character occurs in the string.

Concept: Character searching and frequency counting.

```
#include <stdio.h>

int main()
{
    char str[100], ch;
    int i, count = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    printf("Enter a character to search: ");
    scanf(" %c", &ch);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] == ch)
        {
            count++;
        }
    }

    printf("Character '%c' occurs %d times", ch, count);

    return 0;
}
```

Expected Output:

```
Enter a string: programming
Enter a character to search: m
Character 'm' occurs 2 times
```

Why is this important? It introduces frequency counting, a common programming technique.

Where is it used? Word analysis, text processing and character-frequency problems.

## 9. Remove All Spaces from a String

Question: Write a C program to remove all spaces from a given string.

Concept: Reading strings with spaces using `fgets()` and shifting characters.

```
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100];
    int i, j = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    str[strcspn(str, "\n")] = '\0';

    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] != ' ')
        {
            str[j] = str[i];
            j++;
        }
    }

    str[j] = '\0';

    printf("String without spaces = %s", str);

    return 0;
}
```

Expected Output:

```
Enter a sentence: Hello World C Programming
String without spaces = HelloWorldCProgramming
```

Why is this important? Students learn how to read complete sentences and modify string contents.

Where is it used? Cleaning user input, removing unwanted whitespace and preparing text for processing.

## 10. Count the Number of Words in a Sentence

Question: Write a C program to count the number of words in a sentence.

Concept: Detecting word boundaries using spaces.

```
#include <stdio.h>
#include <ctype.h>

int main()
{
    char str[200];
    int i, words = 0, inWord = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (!isspace((unsigned char)str[i]))
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

Expected Output:

```
Enter a sentence: C programming is easy to learn
Number of words = 6
```

Why is this important? It teaches students how to identify words rather than just individual characters.

Where is it used? Word counters, document analysis, search engines and text-processing applications.

## Important concepts students should remember

| Function / Concept | Purpose                                   |
| ------------------ | ----------------------------------------- |
| `'\0'`             | Marks the end of a string                 |
| `strlen()`         | Finds string length                       |
| `toupper()`        | Converts a character to uppercase         |
| `tolower()`        | Converts a character to lowercase         |
| `isalpha()`        | Checks whether a character is an alphabet |
| `isdigit()`        | Checks whether a character is a digit     |
| `isspace()`        | Checks whitespace characters              |
| `fgets()`          | Reads a complete line, including spaces   |
| `scanf("%s", str)` | Reads a word until whitespace             |

# C Programming – Strings: 30 Hands-on Programs



Part 2 of 3

Programs 11–20



These programs focus on string comparison, copying, concatenation, character frequency, searching and modifying strings.

## 11. Count Uppercase and Lowercase Letters

Question: Write a C program to count the uppercase and lowercase letters in a given string.

Concept: Character classification using `isupper()` and `islower()`.

```
#include <stdio.h>
#include <ctype.h>

int main()
{
    char str[100];
    int i, upper = 0, lower = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (isupper((unsigned char)str[i]))
            upper++;
        else if (islower((unsigned char)str[i]))
            lower++;
    }

    printf("Uppercase letters = %d\n", upper);
    printf("Lowercase letters = %d\n", lower);

    return 0;
}
```

Expected Output:

```
Enter a string: HeLLoWorld
Uppercase letters = 3
Lowercase letters = 7
```

Why is this important? Students learn to classify characters based on their case.

Where is it used? Password analysis, text formatting and input validation.

## 12. Compare Two Strings Without Using `strcmp()`

Question: Write a C program to compare two strings without using the built-in `strcmp()` function.

Concept: Comparing corresponding characters one by one.

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

Expected Output:

```
Enter first string: Hello
Enter second string: Hello
Strings are equal
```

Another Output:

```
Enter first string: Hello
Enter second string: World
Strings are not equal
```

Why is this important? It explains how string comparison works internally.

Where is it used? Login systems, username comparison and searching records.

## 13. Find the Frequency of Each Character in a String

Question: Write a C program to count how many times each character occurs in a string.

Concept: Frequency counting using an array.

```
#include <stdio.h>

int main()
{
    char str[100];
    int freq[256] = {0};
    int i;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        freq[(unsigned char)str[i]]++;
    }

    printf("Character frequencies:\n");

    for (i = 0; i < 256; i++)
    {
        if (freq[i] > 0)
        {
            printf("%c = %d\n", i, freq[i]);
        }
    }

    return 0;
}
```

Expected Output:

```
Enter a string: banana
Character frequencies:
a = 3
b = 1
n = 2
```

Why is this important? It combines strings and arrays, helping students understand how to store and count character frequencies.

Where is it used? Text analytics, word statistics and basic data compression concepts.

## 14. Find the First Position of a Character in a String

Question: Write a C program to search for a character in a string and display its first position.

Concept: Linear search on a string.

```
#include <stdio.h>

int main()
{
    char str[100], ch;
    int i, position = -1;

    printf("Enter a string: ");
    scanf("%99s", str);

    printf("Enter character to search: ");
    scanf(" %c", &ch);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] == ch)
        {
            position = i;
            break;
        }
    }

    if (position != -1)
        printf("Character found at index %d", position);
    else
        printf("Character not found");

    return 0;
}
```

Expected Output:

```
Enter a string: programming
Enter character to search: g
Character found at index 3
```

Remember: C string indexing starts from 0. Therefore, index 3 is the fourth character.

Why is this important? It teaches searching and the use of `break`.

Where is it used? Finding characters in text, searching keywords and validating input.

## 15. Replace a Character in a String

Question: Write a C program to replace every occurrence of a particular character with another character.

Concept: Updating individual string elements.

```
#include <stdio.h>

int main()
{
    char str[100], oldChar, newChar;
    int i, count = 0;

    printf("Enter a string: ");
    scanf("%99s", str);

    printf("Enter character to replace: ");
    scanf(" %c", &oldChar);

    printf("Enter new character: ");
    scanf(" %c", &newChar);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] == oldChar)
        {
            str[i] = newChar;
            count++;
        }
    }

    printf("Updated string = %s\n", str);
    printf("Replacements = %d", count);

    return 0;
}
```

Expected Output:

```
Enter a string: banana
Enter character to replace: a
Enter new character: o
Updated string = bonono
Replacements = 3
```

Why is this important? Students learn that string characters can be modified using array indexing.

Where is it used? Text editing, data cleaning and find-and-replace operations.

## 16. Count the Number of Spaces in a Sentence

Question: Write a C program to count the number of spaces in a sentence.

Concept: Reading complete sentences using `fgets()` and checking whitespace.

```
#include <stdio.h>

int main()
{
    char str[200];
    int i, spaces = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for (i = 0; str[i] != '\0'; i++)
    {
        if (str[i] == ' ')
        {
            spaces++;
        }
    }

    printf("Number of spaces = %d", spaces);

    return 0;
}
```

Expected Output:

```
Enter a sentence: C programming is very easy
Number of spaces = 4
```

Why is this important? It reinforces sentence input and character-by-character processing.

Where is it used? Document analysis, text formatting and word-count applications.

## 17. Reverse Each Word in a Sentence

Question: Write a C program to reverse every individual word in a sentence without changing the order of the words.

Concept: Finding word boundaries and reversing characters within each word.

```
#include <stdio.h>
#include <string.h>

int main()
{
    char str[200], temp;
    int i, start = 0, end;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    str[strcspn(str, "\n")] = '\0';

    for (i = 0; ; i++)
    {
        if (str[i] == ' ' || str[i] == '\0')
        {
            end = i - 1;

            while (start < end)
            {
                temp = str[start];
                str[start] = str[end];
                str[end] = temp;

                start++;
                end--;
            }

            if (str[i] == '\0')
                break;

            start = i + 1;
        }
    }

    printf("Result = %s", str);

    return 0;
}
```

Expected Output:

```
Enter a sentence: Hello World C Programming
Result = olleH dlroW C gnimmargorP
```

Why is this important? It teaches students how to process individual words inside a complete sentence.

Where is it used? Text manipulation and string-processing exercises.

## 18. Check Whether Two Strings Are Anagrams

Question: Write a C program to check whether two strings are anagrams.

Two strings are anagrams if they contain the same characters with the same frequencies, but possibly in a different order.

Example: `listen` and `silent`.

Concept: Character frequency arrays.

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char str1[100], str2[100];
    int freq[256] = {0};
    int i, flag = 1;

    printf("Enter first string: ");
    scanf("%99s", str1);

    printf("Enter second string: ");
    scanf("%99s", str2);

    if (strlen(str1) != strlen(str2))
    {
        flag = 0;
    }
    else
    {
        for (i = 0; str1[i] != '\0'; i++)
        {
            freq[(unsigned char)tolower((unsigned char)str1[i])]++;
            freq[(unsigned char)tolower((unsigned char)str2[i])]--;
        }

        for (i = 0; i < 256; i++)
        {
            if (freq[i] != 0)
            {
                flag = 0;
                break;
            }
        }
    }

    if (flag == 1)
        printf("Strings are anagrams");
    else
        printf("Strings are not anagrams");

    return 0;
}
```

Expected Output:

```
Enter first string: listen
Enter second string: silent
Strings are anagrams
```

Why is this important? It combines string operations, arrays and frequency counting.

Where is it used? Word games, text analysis and string-matching problems.

## 19. Remove Duplicate Characters from a String

Question: Write a C program to remove repeated characters from a string while keeping the first occurrence of each character.

Concept: Nested loops and character comparison.

```
#include <stdio.h>

int main()
{
    char str[100];
    int i, j, k;

    printf("Enter a string: ");
    scanf("%99s", str);

    for (i = 0; str[i] != '\0'; i++)
    {
        for (j = i + 1; str[j] != '\0'; )
        {
            if (str[i] == str[j])
            {
                for (k = j; str[k] != '\0'; k++)
                {
                    str[k] = str[k + 1];
                }
            }
            else
            {
                j++;
            }
        }
    }

    printf("String after removing duplicates = %s", str);

    return 0;
}
```

Expected Output:

```
Enter a string: programming
String after removing duplicates = progamin
```

Why is this important? It develops nested-loop logic and teaches how to delete elements from an array.

Where is it used? Removing duplicate characters, cleaning data and simplifying text.

## 20. Validate a Password Using String Operations

Question: Write a C program to check whether a password satisfies these conditions:

1. At least 8 characters long.
2. Contains at least one uppercase letter.
3. Contains at least one lowercase letter.
4. Contains at least one digit.
5. Contains at least one special character.

Concept: String traversal and character classification.

```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

int main()
{
    char password[100];
    int i;
    int upper = 0, lower = 0;
    int digit = 0, special = 0;

    printf("Enter password: ");
    scanf("%99s", password);

    for (i = 0; password[i] != '\0'; i++)
    {
        if (isupper((unsigned char)password[i]))
            upper = 1;
        else if (islower((unsigned char)password[i]))
            lower = 1;
        else if (isdigit((unsigned char)password[i]))
            digit = 1;
        else
            special = 1;
    }

    if (strlen(password) >= 8 &&
        upper && lower && digit && special)
    {
        printf("Password is valid");
    }
    else
    {
        printf("Password is invalid");
    }

    return 0;
}
```

Expected Output 1:

```
Enter password: Hello@123
Password is valid
```

Expected Output 2:

```
Enter password: hello123
Password is invalid
```

Why is this important? It combines multiple string and character operations into one practical application.

Where is it used? Registration forms, login systems and password-policy validation.

## Revision: Programs 11–20

| Program | Topic                         | Main concept             |
| ------- | ----------------------------- | ------------------------ |
| 11      | Uppercase and lowercase count | `isupper()`, `islower()` |
| 12      | Compare two strings           | Character comparison     |
| 13      | Character frequency           | Frequency array          |
| 14      | Search a character            | Linear search            |
| 15      | Replace a character           | String modification      |
| 16      | Count spaces                  | `fgets()`                |
| 17      | Reverse each word             | Word boundaries          |
| 18      | Anagram check                 | Frequency array          |
| 19      | Remove duplicates             | Nested loops             |
| 20      | Password validation           | Multiple conditions      |

# C Programming – Strings: 30 Hands-on Programs



Part 3 of 3

Programs 21–30



These final 10 programs introduce more practical string operations using `string.h`, arrays of strings, searching, sorting and sentence processing.

## 21. Copy One String into Another Without Using `strcpy()`

Question: Write a C program to copy the contents of one string into another string without using the built-in `strcpy()` function.

Concept: Character-by-character copying.

```
#include <stdio.h>

int main()
{
    char str1[100], str2[100];
    int i;

    printf("Enter a string: ");
    scanf("%99s", str1);

    for (i = 0; str1[i] != '\0'; i++)
    {
        str2[i] = str1[i];
    }

    str2[i] = '\0';

    printf("Original string = %s\n", str1);
    printf("Copied string = %s", str2);

    return 0;
}
```

Expected Output:

```
Enter a string: Programming
Original string = Programming
Copied string = Programming
```

Why is this important? Students understand how data is copied from one character array to another.

Where is it used? Copying usernames, names and text data between variables.

## 22. Concatenate Two Strings Without Using `strcat()`

Question: Write a C program to join two strings without using the built-in `strcat()` function.

Concept: Appending one string at the end of another.

```
#include <stdio.h>

int main()
{
    char str1[200], str2[100];
    int i, j;

    printf("Enter first string: ");
    scanf("%99s", str1);

    printf("Enter second string: ");
    scanf("%99s", str2);

    i = 0;

    while (str1[i] != '\0')
    {
        i++;
    }

    for (j = 0; str2[j] != '\0'; j++)
    {
        str1[i] = str2[j];
        i++;
    }

    str1[i] = '\0';

    printf("Concatenated string = %s", str1);

    return 0;
}
```

Expected Output:

```
Enter first string: Hello
Enter second string: World
Concatenated string = HelloWorld
```

Why is this important? It teaches students how to append characters and manage the null terminator.

Where is it used? Creating full names, combining messages and constructing file paths.

## 23. Find the Longest Word in a Sentence

Question: Write a C program to identify and display the longest word in a sentence.

Concept: Word boundary detection and length comparison.

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char str[200];
    char longest[100];
    char current[100];

    int i, j = 0;
    int maxLength = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for (i = 0; ; i++)
    {
        if (!isspace((unsigned char)str[i]) &&
            str[i] != '\0')
        {
            current[j++] = str[i];
        }
        else
        {
            current[j] = '\0';

            if (j > maxLength)
            {
                maxLength = j;
                strcpy(longest, current);
            }

            j = 0;

            if (str[i] == '\0')
                break;
        }
    }

    printf("Longest word = %s\n", longest);
    printf("Length = %d", maxLength);

    return 0;
}
```

Expected Output:

```
Enter a sentence: C programming is interesting
Longest word = programming
Length = 11
```

Why is this important? It combines string traversal, word extraction and comparison.

Where is it used? Document analysis, text statistics and language-processing applications.

## 24. Sort Characters of a String in Alphabetical Order

Question: Write a C program to arrange the characters of a string in alphabetical order.

Concept: Bubble sort applied to characters.

```
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100], temp;
    int i, j, n;

    printf("Enter a string: ");
    scanf("%99s", str);

    n = strlen(str);

    for (i = 0; i < n - 1; i++)
    {
        for (j = 0; j < n - i - 1; j++)
        {
            if (str[j] > str[j + 1])
            {
                temp = str[j];
                str[j] = str[j + 1];
                str[j + 1] = temp;
            }
        }
    }

    printf("Sorted string = %s", str);

    return 0;
}
```

Expected Output:

```
Enter a string: dcba
Sorted string = abcd
```

Why is this important? Students learn that sorting can also be performed on characters, not just numbers.

Where is it used? Alphabetical arrangement, anagram-related problems and text processing.

## 25. Check Whether a String Starts with a Given Prefix

Question: Write a C program to check whether a string starts with a given prefix.

Concept: Comparing the initial characters of two strings.

```
#include <stdio.h>

int main()
{
    char str[100], prefix[100];
    int i, flag = 1;

    printf("Enter a string: ");
    scanf("%99s", str);

    printf("Enter prefix: ");
    scanf("%99s", prefix);

    for (i = 0; prefix[i] != '\0'; i++)
    {
        if (str[i] == '\0' || str[i] != prefix[i])
        {
            flag = 0;
            break;
        }
    }

    if (flag == 1)
        printf("String starts with the given prefix");
    else
        printf("String does not start with the given prefix");

    return 0;
}
```

Expected Output:

```
Enter a string: programming
Enter prefix: pro
String starts with the given prefix
```

Why is this important? It teaches partial string comparison.

Where is it used? URL checking, file extension validation and searching words by their starting letters.

## 26. Check Whether a Word Exists in a Sentence

Question: Write a C program to search for a particular word in a sentence and display whether it exists.

Concept: Word extraction and string comparison.

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char sentence[200], word[50], current[50];
    int i, j = 0, found = 0;

    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    printf("Enter word to search: ");
    scanf("%49s", word);

    for (i = 0; ; i++)
    {
        if (!isspace((unsigned char)sentence[i]) &&
            sentence[i] != '\0')
        {
            current[j++] = sentence[i];
        }
        else
        {
            current[j] = '\0';

            if (strcmp(current, word) == 0)
            {
                found = 1;
                break;
            }

            j = 0;

            if (sentence[i] == '\0')
                break;
        }
    }

    if (found)
        printf("Word found in the sentence");
    else
        printf("Word not found in the sentence");

    return 0;
}
```

Expected Output:

```
Enter a sentence: C programming is interesting
Enter word to search: programming
Word found in the sentence
```

Why is this important? It teaches the difference between searching for a character and searching for a complete word.

Where is it used? Search engines, document search and text-analysis applications.

## 27. Store and Display Five Student Names Using a 2D Character Array

Question: Write a C program to read five student names and display them using a two-dimensional character array.

Concept: Array of strings.

```
#include <stdio.h>

int main()
{
    char names[5][50];
    int i;

    printf("Enter five student names:\n");

    for (i = 0; i < 5; i++)
    {
        printf("Student %d: ", i + 1);
        scanf("%49s", names[i]);
    }

    printf("\nStudent Names:\n");

    for (i = 0; i < 5; i++)
    {
        printf("%s\n", names[i]);
    }

    return 0;
}
```

Expected Output:

```
Enter five student names:
Student 1: Ravi
Student 2: Suresh
Student 3: Priya
Student 4: Kumar
Student 5: Anjali

Student Names:
Ravi
Suresh
Priya
Kumar
Anjali
```

Why is this important? Students learn how to store multiple strings in a single two-dimensional array.

Where is it used? Student management systems, employee records and contact lists.

## 28. Sort Five Student Names in Alphabetical Order

Question: Write a C program to read five student names and sort them alphabetically.

Concept: Two-dimensional character arrays, `strcmp()` and `strcpy()`.

```
#include <stdio.h>
#include <string.h>

int main()
{
    char names[5][50], temp[50];
    int i, j;

    printf("Enter five student names:\n");

    for (i = 0; i < 5; i++)
    {
        scanf("%49s", names[i]);
    }

    for (i = 0; i < 4; i++)
    {
        for (j = 0; j < 4 - i; j++)
        {
            if (strcmp(names[j], names[j + 1]) > 0)
            {
                strcpy(temp, names[j]);
                strcpy(names[j], names[j + 1]);
                strcpy(names[j + 1], temp);
            }
        }
    }

    printf("\nNames in alphabetical order:\n");

    for (i = 0; i < 5; i++)
    {
        printf("%s\n", names[i]);
    }

    return 0;
}
```

Expected Output:

```
Enter five student names:
Ravi
Suresh
Priya
Kumar
Anjali

Names in alphabetical order:
Anjali
Kumar
Priya
Ravi
Suresh
```

Why is this important? It combines sorting algorithms with string library functions.

Where is it used? Student databases, employee directories and contact management systems.

## 29. Count the Number of Lines, Words and Characters in Text

Question: Write a C program to count the number of lines, words and characters entered by the user. Stop reading when the user enters `END` on a separate line.

Concept: Multiple lines of input, string comparison and counters.

```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main()
{
    char line[200];
    int lines = 0, words = 0, characters = 0;
    int i, inWord;

    printf("Enter text (type END to stop):\n");

    while (fgets(line, sizeof(line), stdin) != NULL)
    {
        line[strcspn(line, "\n")] = '\0';

        if (strcmp(line, "END") == 0)
            break;

        lines++;
        inWord = 0;

        for (i = 0; line[i] != '\0'; i++)
        {
            characters++;

            if (!isspace((unsigned char)line[i]))
            {
                if (!inWord)
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
    }

    printf("\nLines = %d\n", lines);
    printf("Words = %d\n", words);
    printf("Characters = %d", characters);

    return 0;
}
```

Expected Output:

```
Enter text (type END to stop):
C programming
Strings are easy
END

Lines = 2
Words = 5
Characters = 28
```

Why is this important? It combines multiple string-processing operations and repeated input.

Where is it used? Text editors, document statistics and word-processing applications.

## 30. Simple Student Record Search Using an Array of Strings

Question: Write a C program to store five student names and search whether a particular student exists in the list.

Concept: Array of strings and linear search using `strcmp()`.

```
#include <stdio.h>
#include <string.h>

int main()
{
    char names[5][50];
    char searchName[50];
    int i, found = 0;

    printf("Enter five student names:\n");

    for (i = 0; i < 5; i++)
    {
        printf("Student %d: ", i + 1);
        scanf("%49s", names[i]);
    }

    printf("\nEnter student name to search: ");
    scanf("%49s", searchName);

    for (i = 0; i < 5; i++)
    {
        if (strcmp(names[i], searchName) == 0)
        {
            found = 1;
            break;
        }
    }

    if (found)
        printf("Student found at position %d", i + 1);
    else
        printf("Student not found");

    return 0;
}
```

Expected Output:

```
Enter five student names:
Student 1: Ravi
Student 2: Suresh
Student 3: Priya
Student 4: Kumar
Student 5: Anjali

Enter student name to search: Priya
Student found at position 3
```

Why is this important? It combines arrays, strings, searching and comparison into one application.

Where is it used? College management systems, attendance applications and student databases.

# Complete Strings Practice – 30 Programs

| Programs | Topics covered                                                                         |
| -------- | -------------------------------------------------------------------------------------- |
| 1–10     | Basic string operations, traversal, palindrome, character counting                     |
| 11–20    | Comparison, frequency, searching, replacement, anagrams, password validation           |
| 21–30    | Copying, concatenation, word processing, sorting, arrays of strings, searching records |

## Important string functions – Quick revision

| Function    | Purpose                                                                     |
| ----------- | --------------------------------------------------------------------------- |
| `strlen()`  | Finds string length                                                         |
| `strcpy()`  | Copies one string into another                                              |
| `strcat()`  | Joins two strings                                                           |
| `strcmp()`  | Compares two strings                                                        |
| `strchr()`  | Searches for a character                                                    |
| `strstr()`  | Searches for a substring                                                    |
| `strcspn()` | Finds the length of the initial segment not containing specified characters |

Important: Always ensure the destination array has enough space before using `strcpy()` or `strcat()`. Never use `gets()`; use `fgets()` for reading complete sentences.


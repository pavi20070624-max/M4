# EX-16-LEFT-SHIFT-OPERATION
## AIM
To write a C Program to perform the basic left shift operation for 44 integer number with 3 shifts.

## ALGORITHM
1.	Start the program.
2.	Assign values of a and b as 44 and 3.
3.	Use left shift operator (<<) and shift the value of a three times.
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>

int main() {
    int num = 44;
    int shifts = 3;
    int result;

    // Perform left shift
    result = num << shifts;

    printf("Original number: %d\n", num);
    printf("Number after left shifting by %d positions: %d\n", shifts, result);

    return 0;
}

```

## OUTPUT
<img width="425" height="186" alt="image" src="https://github.com/user-attachments/assets/b050b577-3320-4680-ac57-d3f98123e21c" />









## RESULT
Thus the program to perform the basic left shift operation for 44 integer number with 3 shifts has been executed successfully.




 
 


# EX-17-TWO-NUMBERS-ARE-EQUAL-OR-NOT


## AIM

Write a C Program to check whether the two numbers are equal or not using simple if statement.

## ALGORITHM

1.	Start the program.
2.	Read two numbers.
3.	If first number is equal to second number, display both are equal.
4.	Otherwise display both are not equal.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
int main() {
    int num1, num2;

    // Read two numbers from user
    printf("Enter the first number: ");
    scanf("%d", &num1);

    printf("Enter the second number: ");
    scanf("%d", &num2);

    // Check equality using simple if
    if (num1 == num2) {
        printf("The numbers are equal.\n");
    }

    return 0;
}
```


## OUTPUT
<img width="346" height="198" alt="image" src="https://github.com/user-attachments/assets/20750703-3fb5-4881-a0af-622aaae51815" />

           
## RESULT

Thus the program to check whether the two numbers are equal or not using simple if statement has been executed successfully
 
 


# EX-18-STRING-LOWERCASE-CONVERSION
## AIM
Write a C Program to convert the given string into lowercase.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using tolower( ) function convert the given string into its lowercase.
4.	Display the result.
5.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <ctype.h>   // for tolower()
#include <string.h>  // for string functions

int main() {
    char str[100];

    // Read string from user
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove newline character if present
    str[strcspn(str, "\n")] = '\0';

    // Convert each character to lowercase
    for (int i = 0; i < strlen(str); i++) {
        str[i] = tolower(str[i]);
    }

    // Print the lowercase string
    printf("Lowercase string: %s\n", str);

    return 0;
}
```

## OUTPUT
<img width="354" height="190" alt="image" src="https://github.com/user-attachments/assets/cbc9cc7b-6d5d-4988-9ddf-c3dfaa9b92f0" />




## RESULT
Thus the program to convert the given string into lowercase has been executed successfully
 
 


# EX-19-COUNT-OF-WORDS-IN-A-STRING
## AIM
Write a C Program to count the total number of words in a given string using do While loop.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using for loop, inspect the string character by character.
4.	Whenever a space is encountered increment count by 1.
5.	Display the result.
6.	Stop the program.

## PROGRAM
```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[200];
    int i = 0, wordCount = 0;

    // Read string from user
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    // Remove newline character if present
    str[strcspn(str, "\n")] = '\0';

    int len = strlen(str);

    // Count words using do-while loop
    do {
        // Skip spaces
        while (i < len && isspace(str[i])) {
            i++;
        }

        // If not end of string, count word
        if (i < len) {
            wordCount++;

            // Move to the end of the word
            while (i < len && !isspace(str[i])) {
                i++;
            }
        }
    } while (i < len);

    printf("Total number of words: %d\n", wordCount);

    return 0;
}

```

## OUTPUT

<img width="316" height="163" alt="image" src="https://github.com/user-attachments/assets/98eb3ad2-f289-4f2b-acb2-4e50e503fcfe" />




## RESULT
Thus the program to count the total number of words in a given string using do While loop has been executed successfully
 
 


# EX  -20 -COMPARING TWO STRINGS
## AIM
write a Program to compare two strings without using strcmp().
## ALGORITHM
Step 1: Start the program.
Step 2: Declare two character arrays c1 and c2 of size 100 to store the strings. Also, declare an integer variable
             flag and initialize it to 0, and i for indexing.      
Step 3: Read the first string c1 using scanf("%[^\n]", c1); — this reads input until a newline is encountered 
            (i.e., can include spaces).
Step 4: Read the second string c2 using scanf("%s", c2); — this reads input until a space or newline (i.e., no 
            spaces in the second string).
Step 5: Start comparing characters of both strings from index i = 0.
Step 6: Repeat the following while neither c1[i] nor c2[i] is '\0' (i.e., end of string):
•	If c1[i] is not equal to c2[i], set flag = 1.
•	Increment i by 1.
Step 7: After the loop, check the value of flag:
•	If flag == 0, print "strings are same".
•	Otherwise, print "strings are not same".
Step 8: End the program.

## PROGRAM
```c
#include <stdio.h>
#include<string.h>

int main() {
    char str1[100], str2[100];
    int i = 0, flag = 0;

    // Read two strings
    printf("Enter the first string: ");
    fgets(str1, sizeof(str1), stdin);
    printf("Enter the second string: ");
    fgets(str2, sizeof(str2), stdin);

    // Remove newline characters if present
    str1[strcspn(str1, "\n")] = '\0';
    str2[strcspn(str2, "\n")] = '\0';

    // Compare strings character by character
    while (str1[i] != '\0' && str2[i] != '\0') {
        if (str1[i] != str2[i]) {
            flag = 1; // strings are different
            break;
        }
        i++;
    }

    // If one string is longer than the other
    if (str1[i] != '\0' || str2[i] != '\0') {
        flag = 1;
    }

    // Print result
    if (flag == 0)
        printf("The strings are equal.\n");
    else
        printf("The strings are not equal.\n");

    return 0;
}

```



## OUTPUT
 <img width="329" height="194" alt="image" src="https://github.com/user-attachments/assets/0a802d6f-cd01-4716-b91a-fc5e33e0bb1b" />


## RESULT
Thus the C Program to compare two strings without using strcmp() has been executed successfully.


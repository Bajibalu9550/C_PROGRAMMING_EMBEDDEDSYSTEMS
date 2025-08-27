#  C Program to Remove All Characters Except Alphabets

This program reads a string from the user and removes all characters **except alphabets (A–Z, a–z).**

---

##  Code

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[200], result[200];
    int j = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strlen(str) - 1] = '\0';

    
    for (int i = 0; str[i] != '\0'; i++) {
        if (isalpha(str[i])) {
            result[j++] = str[i];
        }
    }
    result[j] = '\0';  // Null terminate

    printf("String after removing non-alphabets: %s\n", result);

    return 0;
}

**OUTPUT: **

Enter sting: Bajibalu123

String after removing non_alphabets: Bajibalu



# C Program to Replace Spaces in a String with a Specific Character

## Problem Explanation
The task is to **replace all spaces in a string** with a character provided by the user.  

**Example:**  

Input: "I love programming in C"
Replacement character: '_'
Output: "I_love_programming_in_C"


The program reads a string from the user, asks for the replacement character, and then replaces all spaces in the string with that character.

---

## C Program

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed\n");
        exit(1);
    }

    printf("Enter a string: ");
    fgets(str, 100, stdin);
    str[strcspn(str, "\n")] = '\0';  

    char replaceChar;
    printf("Enter the character to replace spaces: ");
    scanf(" %c", &replaceChar);

    
    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] == ' ') {
            str[i] = replaceChar;
        }
    }

    printf("Modified string: %s\n", str);

    free(str);
    return 0;
}

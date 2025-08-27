# C Program to Find the Largest and Smallest Words in a String

## Problem Explanation
The task is to **find the largest and smallest words** in a given string. A word is defined as a sequence of characters separated by spaces.  

**Example:**  
Input: `"I love programming in C"`  
- Smallest word: `"I"` (length 1)  
- Largest word: `"programming"` (length 11)  

To solve this problem, we need to:
1. Read the string from the user.
2. Split the string into words.
3. Compare the lengths of all words.
4. Keep track of the smallest and largest words.

---

## C Program

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed");
        exit(1);
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';

    int max, min;
    char small[50], large[100];
    char *token = strtok(str, " ");
    
    
    max = min = strlen(token);
    strcpy(small, token);
    strcpy(large, token);

    while (token != NULL) {
        if (max < strlen(token)) {
            max = strlen(token);
            strcpy(large, token);
        }
        if (min > strlen(token)) {
            min = strlen(token);
            strcpy(small, token);
        }
        token = strtok(NULL, " ");
    }

    printf("Smallest word: %s and length: %d\n", small, min);
    printf("Largest word: %s and length: %d\n", large, max);

    free(str);
    return 0;
}

# C Program to Print Initials Using `strtok()`

This program takes a string (such as a full name) as input and prints the initials of each word using the `strtok()` function to tokenize the string.

## Program Code

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed.");
        exit(1);
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';  r

    char *token = strtok(str, " ");
    while (token != NULL) {
        printf("%c", token[0]);  
        token = strtok(NULL, " ");
    }
}
```

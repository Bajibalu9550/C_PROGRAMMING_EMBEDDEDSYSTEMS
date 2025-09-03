# C Program to Remove All Occurrences of a Character from a String

This program takes a string and a character as input, then removes all occurrences of the specified character from the string.

## Program Code

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

void removee(char *str, char ch) {
    char str1[strlen(str)];
    int j = 0;
    for (int i = 0; str[i]; i++) {
        if (str[i] != ch)
            str1[j++] = str[i];
    }
    str1[j] = '\0';
    printf("Updated string: %s\n", str1);
}

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed");
        exit(1);
    }
    
    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';
    
    char ch;
    printf("Enter Character: ");
    scanf("%c", &ch);
    
    removee(str, ch);
}
```

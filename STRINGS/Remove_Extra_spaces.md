# C Program to Replace Multiple Adjacent Spaces with a Single Space

This program removes extra spaces from a string so that multiple adjacent spaces are replaced by a single space.

## Program Code

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

void remove_spaces(char *str) {
    int space = 0;
    int i = 0, j = 0;

    while (str[i]) {
        if (str[i] != ' ') {
            str[j++] = str[i];
            space = 0;
        } else {
            if (!space) {       
                str[j++] = ' ';
                space = 1;
            }
        }
        i++;
    }
    str[j] = '\0';

    printf("Extra Spaces Removed string: %s", str);
}

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed.");
        exit(1);
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';   

    remove_spaces(str);
}
```

#  Find the Length of a String Using Pointers and Dynamic Memory in C

This program dynamically allocates memory for a string, takes input from the user, and calculates the length of the string using pointer traversal.

---

## Source Code

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str = malloc(100 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strcspn(str, "\n")] = '\0';

    int n = 0;
    char *temp = str;
    while (*str != '\0') {
        str++;
        n++;
    }

    printf("Length of string: %d\n", n);
    free(temp);

    return 0;
}

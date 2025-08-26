# Write a program to compare two strings lexicographically (like the strcmp function) using pointers.

```
#include <stdio.h>
#include <stdlib.h>

int stringCompare(char *str1, char *str2) {
    while (*str1 != '\0' && *str2 != '\0') {
        if (*str1 != *str2)
            return (*str1 - *str2);  // difference of first unmatched characters
        str1++;
        str2++;
    }
    return (*str1 - *str2);  // handles strings of different lengths
}

int main() {
    char *str1 = malloc(100);
    char *str2 = malloc(100);

    if (str1 == NULL || str2 == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    printf("Enter first string: ");
    fgets(str1, 100, stdin);
    str1[strle(str1)-1]='\0';

    printf("Enter second string: ");
    fgets(str2, 100, stdin);
    str2[strlen(str2)-1]='\0';

    int result = stringCompare(str1, str2);

    if (result == 0)
        printf("Strings are equal.\n");
    else if (result < 0)
        printf("First string is lexicographically smaller.\n");
    else
        printf("First string is lexicographically greater.\n");

    free(str1);
    free(str2);
    return 0;
}

```

__OUTPUT :__

Enter first string: orange

Enter second string: grape

First string is lexicographically greater.


Enter first string: apple

Enter second string: banana

First string is lexicographically smaller.


Enter first string: mango

Enter second string: mango

Strings are equal.


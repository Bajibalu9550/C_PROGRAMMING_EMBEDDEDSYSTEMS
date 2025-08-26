#  write a program to concatenate two strings using pointers

```
#include <stdio.h>
#include <stdlib.h>

void stringConcat(char *dest, char *src) {
    
    while (*dest != '\0') {
        dest++;
    }

    // Copy src to dest
    while (*src != '\0') {
        *dest = *src;
        dest++;
        src++;
    }

    *dest = '\0'; 
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
    str1[strlen(str1)-1]='\0';
    printf("Enter second string: ");
    fgets(str2, 100, stdin);
    str2[styrlen(str2)-1]='\0';

    stringConcat(str1, str2);

    printf("Concatenated string: %s\n", str1);

    free(str1);
    free(str2);
    return 0;
}

```

__OUTPUT :__

Enter first string: Hello

Enter second string: World

Concatenated string: HelloWorld

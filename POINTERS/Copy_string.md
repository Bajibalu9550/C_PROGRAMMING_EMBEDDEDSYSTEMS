#  Implement a function to copy one string into another using pointers, without using any standard library function

```
#include <stdio.h>
#include <stdlib.h>

void stringCopy(char *dest, char *src) {
    while(*src != '\0') {
        *dest = *src;
        dest++;
        src++;
    }
    *dest = '\0';  
}

int main() {
    char *source = malloc(100);
    char *destination = malloc(100);

    if(source == NULL || destination == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    printf("Enter source string: ");
    fgets(source, 100, stdin);
    source[strlen(source)-1]='\0';

    stringCopy(destination, source);

    printf("Copied string: %s\n", destination);

    free(source);
    free(destination);
    return 0;
}

```

__OUTPUT :__

Enter source string: Hello World

Copied string: Hello World


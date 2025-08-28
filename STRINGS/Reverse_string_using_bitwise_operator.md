# Recursive Function to Reverse a String Using Bitwise Operators

```c
#include <stdio.h>
#include <string.h>

void reverse_string(char *str, int start, int end) {
    if (start >= end)
        return;

    str[start] ^= str[end];
    str[end]   ^= str[start];
    str[start] ^= str[end];

    reverse_string(str, start + 1, end - 1);
}

int main() {
    char str[100];

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    reverse_string(str, 0, strlen(str) - 1);

    printf("Reversed string: %s\n", str);

    return 0;
}

OUTPUT:
Enter a string: Hello
Reversed string: olleH



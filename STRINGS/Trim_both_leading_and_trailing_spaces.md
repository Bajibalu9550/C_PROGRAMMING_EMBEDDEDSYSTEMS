# C Program to Trim Both Leading and Trailing White Space Characters from a Given String

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[200];
    int i = 0, j = 0, len;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    while (isspace((unsigned char)str[i])) {
        i++;
    }

    len = strlen(str) - 1;
    while (len >= i && isspace((unsigned char)str[len])) {
        len--;
    }

    while (i <= len) {
        str[j++] = str[i++];
    }
    str[j] = '\0';

    printf("String after trimming leading and trailing white spaces: \"%s\"\n", str);

    return 0;
}

OUTPUT:
Enter a string:    hello world    
String after trimming leading and trailing white spaces: "hello world"

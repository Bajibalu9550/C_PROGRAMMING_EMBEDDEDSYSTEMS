# C Program to Trim Trailing White Space Characters from a Given String

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[200];
    int len;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    len = strlen(str) - 1;

    while (len >= 0 && isspace((unsigned char)str[len])) {
        len--;
    }

    str[len + 1] = '\0';

    printf("String after trimming trailing white spaces: \"%s\"\n", str);

    return 0;
}

OUTPUT:
Enter a string: hello world    
String after trimming trailing white spaces: "hello world"

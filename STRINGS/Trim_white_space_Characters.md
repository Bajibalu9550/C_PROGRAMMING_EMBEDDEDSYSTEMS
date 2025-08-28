# C Program to Trim Leading White Space Characters from a Given String

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[200];
    int i = 0, j = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    while (isspace((unsigned char)str[i])) {
        i++;
    }

    while (str[i] != '\0') {
        str[j++] = str[i++];
    }
    str[j] = '\0';

    printf("String after trimming leading white spaces: \"%s\"\n", str);

    return 0;
}

OUTPUT:
Enter a string:     hello world   
String after trimming leading white spaces: "hello world   "

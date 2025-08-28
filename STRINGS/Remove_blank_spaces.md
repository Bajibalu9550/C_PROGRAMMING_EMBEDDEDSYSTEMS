# C Program to Remove All Extra Blank Spaces from a Given String

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main() {
    char str[200], result[200];
    int i = 0, j = 0;
    int space_flag = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    while (isspace((unsigned char)str[i])) {
        i++;
    }

    for (; str[i] != '\0'; i++) {
        if (!isspace((unsigned char)str[i])) {
            result[j++] = str[i];
            space_flag = 0;
        } else if (!space_flag) {
            result[j++] = ' ';
            space_flag = 1;
        }
    }

    if (j > 0 && result[j - 1] == ' ') {
        j--;
    }

    result[j] = '\0';
    printf("String after removing extra blank spaces: \"%s\"\n", result);

    return 0;
}

OUTPUT:
Enter a string:   this   is    a   test   
String after removing extra blank spaces: "this is a test"


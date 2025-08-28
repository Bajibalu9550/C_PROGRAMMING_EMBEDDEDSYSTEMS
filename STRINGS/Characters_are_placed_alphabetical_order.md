# C Program to Sort Characters of a String in Alphabetical Order

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], temp;
    int i, j, len;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    len = strlen(str);

    for (i = 0; i < len - 1; i++) {
        for (j = i + 1; j < len; j++) {
            if (str[i] > str[j]) {
                temp = str[i];
                str[i] = str[j];
                str[j] = temp;
            }
        }
    }

    printf("String after arranging characters in alphabetical order: %s\n", str);

    return 0;
}

OUTPUT:
Enter a string: Devanshi
String after arranging characters in alphabetical order: aDehinsv

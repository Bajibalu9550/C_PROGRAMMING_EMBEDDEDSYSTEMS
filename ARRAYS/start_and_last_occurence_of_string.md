# C Program: Check if a String is at the Start or End of Another String

```c
#include <stdio.h>
#include <string.h>

int str_start(const char *str1, const char *str2) {
    while (*str2) {
        if (*str1 != *str2)
            return 0;
        str1++;
        str2++;
    }
    return 1;
}

int str_end(const char *str1, const char *str2) {
    int len1 = strlen(str1);
    int len2 = strlen(str2);

    if (len2 > len1)
        return 0;

    str1 += len1 - len2;

    while (*str2) {
        if (*str1 != *str2)
            return 0;
        str1++;
        str2++;
    }
    return 1;
}

int main() {
    char str1[100], str2[100];

    printf("Enter the first string: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0';

    printf("Enter the second string: ");
    fgets(str2, sizeof(str2), stdin);
    str2[strcspn(str2, "\n")] = '\0';

    if (str_start(str1, str2))
        printf("\"%s\" is at the start of \"%s\"\n", str2, str1);
    else
        printf("\"%s\" is NOT at the start of \"%s\"\n", str2, str1);

    if (str_end(str1, str2))
        printf("\"%s\" is at the end of \"%s\"\n", str2, str1);
    else
        printf("\"%s\" is NOT at the end of \"%s\"\n", str2, str1);

    return 0;
}
```

# C Function for Case-Insensitive String Comparison

```c
#include <stdio.h>
#include <ctype.h>

int strcasecmp_custom(const char *str1, const char *str2) {
    while (*str1 && *str2) {
        if (tolower((unsigned char)*str1) != tolower((unsigned char)*str2))
            return (tolower((unsigned char)*str1) - tolower((unsigned char)*str2));
        str1++;
        str2++;
    }
    return (tolower((unsigned char)*str1) - tolower((unsigned char)*str2));
}

int main() {
    char str1[100], str2[100];

    printf("Enter first string: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0';

    printf("Enter second string: ");
    fgets(str2, sizeof(str2), stdin);
    str2[strcspn(str2, "\n")] = '\0';

    int result = strcasecmp_custom(str1, str2);

    if (result == 0)
        printf("Strings are equal (case-insensitive)\n");
    else
        printf("Strings are not equal (case-insensitive)\n");

    return 0;
}

OUTPUT:
Enter first string: Hello
Enter second string: hello
Strings are equal (case-insensitive)

# Pointer Versions of `strcpy()`, `strncmp()`, and `strncat()` in C

```c
#include <stdio.h>

// Pointer version of strcpy
void my_strcpy(char *dest, const char *src) {
    while (*src != '\0') {
        *dest++ = *src++;
    }
    *dest = '\0';
}

// Pointer version of strncmp
int my_strncmp(const char *str1, const char *str2, int n) {
    int i;
    for (i = 0; i < n && (*str1 != '\0' || *str2 != '\0'); i++) {
        if (*str1 != *str2)
            return ((unsigned char)*str1 - (unsigned char)*str2);
        str1++;
        str2++;
    }
    return 0;
}

// Pointer version of strncat
void my_strncat(char *dest, const char *src, int n) {
    while (*dest != '\0') dest++;
    int i;
    for (i = 0; i < n && *src != '\0'; i++) {
        *dest++ = *src++;
    }
    *dest = '\0';
}

int main() {
    char str1[100], str2[100], str3[100];
    int n;

    printf("Enter first string: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0';

    printf("Enter second string: ");
    fgets(str2, sizeof(str2), stdin);
    str2[strcspn(str2, "\n")] = '\0';

    my_strcpy(str3, str1);
    printf("After my_strcpy: %s\n", str3);

    printf("Enter number of characters to compare: ");
    scanf("%d", &n);
    int cmp = my_strncmp(str1, str2, n);
    if (cmp == 0)
        printf("First %d characters are equal\n", n);
    else
        printf("First %d characters are not equal\n", n);

    my_strncat(str1, str2, n);
    printf("After my_strncat: %s\n", str1);

    return 0;
}

OUTPUT:
Enter first string: Hello
Enter second string: World
After my_strcpy: Hello
Enter number of characters to compare: 3
First 3 characters are not equal
After my_strncat: HelloWor


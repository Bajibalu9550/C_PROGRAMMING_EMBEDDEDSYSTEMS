# C Program: Pointer Versions of strcpy(), strncmp(), and strncat()

```c
#include <stdio.h>

char *my_strcpy(char *dest, char *src) {
    char *ptr = dest;
    while ((*ptr++ = *src++));
    return dest;
}

int my_strncmp(char *s1, char *s2, size_t n) {
    while (n && *s1 && (*s1 == *s2)) {
        s1++;
        s2++;
        n--;
    }
    if (n == 0)
        return 0;
    return *(char *)s1 - *(char *)s2;
}

char *my_strncat(char *dest, char *src, int n) {
    char *ptr = dest;
    while (*ptr)
        ptr++;
    while (n-- && (*src)) {
        *ptr++ = *src++;
    }
    *ptr = '\0';
    return dest;
}

int main() {
    char str1[50], str2[50];

   
    my_strcpy(str1, "Hello");
    printf("After my_strcpy: %s\n", str1);

    
    printf("my_strncmp(\"Hello\",\"Helium\",3) = %d\n", my_strncmp("Hello", "Helium", 3));
    printf("my_strncmp(\"Hello\",\"World\",3) = %d\n", my_strncmp("Hello", "World", 3));

   
    my_strcpy(str2, "World");
    my_strncat(str1, str2, 3);
    printf("After my_strncat: %s\n", str1);

    return 0;
}

OUTPUT:
After my_strcpy: Hello
my_strncmp("Hello","Helium",3) = 0
my_strncmp("Hello","World",3) = -15
After my_strncat: HelloWor

```

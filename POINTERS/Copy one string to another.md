#  Copy a String Using Pointers in C

C program that copies one string into another using pointer arithmetic.

---

## Source Code

```c
#include <stdio.h>
#include <string.h>


void copy(char *str, char *str1)
{
    int n = 0;
    while (*(str + n) != '\0') {
        *(str1 + n) = *(str + n);
        n++;
    }
    str1[n] = '\0';   
}

int main(void)
{
    char str[100], str1[100];

    printf("Enter String: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';  

    copy(str, str1);

    printf("Copied string is: %s\n", str1);

    return 0;
}




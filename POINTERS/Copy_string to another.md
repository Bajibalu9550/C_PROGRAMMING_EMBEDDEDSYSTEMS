#  Copy a String Using Pointers (Character by Character) in C

This program demonstrates how to copy one string into another **character by character** using **pointer manipulation** in C.

---

##  Source Code

```c
#include <stdio.h>
#include <string.h>


void copy(char *str1, char *str2) {
    while (*str1 != '\0') {
        *str2 = *str1;
        str1++;
        str2++;
    }
    *str2 = '\0';  
}

int main() {
    char str1[100], str2[100];

    printf("Enter String: ");
    fgets(str1, sizeof(str1), stdin);
    str1[strcspn(str1, "\n")] = '\0';  

    copy(str1, str2);

    printf("Copied string is: %s\n", str2);

    return 0;
}


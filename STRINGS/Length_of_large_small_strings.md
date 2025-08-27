#  C Program: Maximum and Minimum String Length Using Pointers and `malloc`

![C Language](https://img.shields.io/badge/Language-C-blue)
![Memory Allocation](https://img.shields.io/badge/Malloc-Dynamic-orange)

This program reads `n` strings dynamically using pointers and `malloc`, then finds the **maximum** and **minimum** string lengths among them.

---

##  Code

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    int n;
    char temp[100];

    printf("Enter number of strings: ");
    scanf("%d", &n);
    getchar();  

    char **str = (char **)malloc(n * sizeof(char *));
    if (str == NULL) {
        printf("Memory allocation failed\n");
        exit(1);
    }

    printf("Enter %d strings:\n", n);
    for (int i = 0; i < n; i++) {
        fgets(temp, sizeof(temp), stdin);
        temp[strlen(temp)-1]='\0';

        str[i] = malloc(strlen(temp) + 1);
        if (str[i] == NULL) {
            printf("Memory allocation failed\n");
            exit(1);
        }
        strcpy(str[i], temp);
    }

    int min = strlen(str[0]);
    int max = strlen(str[0]);

    for (int i = 1; i < n; i++) {
        int len = strlen(str[i]);
        if (len < min)
              min = len;
        if (len > max)
              max = len;
    }

    printf("Max string length: %d and Min string length: %d\n", max, min);

    for (int i = 0; i < n; i++) {
        free(str[i]);
    }
    free(str);

    return 0;
}

OUTPUT :
Enter number of strings: 4
Enter 4 strings:
apple
banana
grapes
kiwi
Max string length: 6 and Min string length: 4


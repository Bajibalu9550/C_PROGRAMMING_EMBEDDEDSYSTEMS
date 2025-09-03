# C Program to Find the Last Occurrence of a Substring

This program finds the last occurrence of the second string (`str2`) in the first string (`str1`) and prints the substring from that point onward.

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

void Last_occurence(char *str1, char *str2) {
    int m = strlen(str1);
    int n = strlen(str2);
    int found = 0, index = 0;

    for (int i = 0; i <= m - n; i++) {
        int j;
        for (j = 0; j < n; j++) {
            if (str1[i + j] != str2[j])
                break;
        }
        if (j == n) {   // full match found
            found = 1;
            index = i;
        }
    }

    if (found) {
        for (int i = index; i < m; i++) {
            printf("%c", str1[i]);
        }
        printf("\n");
    } else {
        printf("String2 is not present in String1.\n");
    }
}

int main() {
    char *str1 = malloc(100);
    char *str2 = malloc(100);

    if (str1 == NULL || str2 == NULL) {
        printf("Memory allocation failed.");
        exit(1);
    }

    printf("Enter first string: ");
    fgets(str1, 100, stdin);
    str1[strlen(str1) - 1] = '\0';

    printf("Enter second string: ");
    fgets(str2, 100, stdin);
    str2[strlen(str2) - 1] = '\0';

    Last_occurence(str1, str2);

    free(str1);
    free(str2);
}
```

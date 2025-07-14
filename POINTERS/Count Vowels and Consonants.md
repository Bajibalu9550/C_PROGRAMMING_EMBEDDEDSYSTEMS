#  Count Vowels, Consonants, and Special Characters Using Pointers in C

This program reads a string from the user and counts the number of **vowels**, **consonants**, and **special characters** using pointer arguments and character classification functions.

---

##  Source Code

```c
#include <string.h>
#include <ctype.h>
#include <stdio.h>
#include <stdlib.h>

int isvowel(char ch) {
    ch = tolower(ch);
    return (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u');
}

void count(char *str, int *x, int *y, int *z) {
    while (*str != '\0') {
        if (isalpha(*str) && isvowel(*str)) {
            (*x)++;
        } else if (isalpha(*str) && !isvowel(*str)) {
            (*y)++;
        } else {
            (*z)++;
        }
        str++;
    }
}

int main() {
    char *str = malloc(100 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation Failed.\n");
        return 1;
    }

    printf("Enter String: ");
    fgets(str, 100, stdin);
    str[strcspn(str, "\n")] = '\0';

    int v = 0, c = 0, s = 0;
    count(str, &v, &c, &s);

    printf("Number of vowels: %d\n", v);
    printf("Number of consonants: %d\n", c);
    printf("Number of special characters: %d\n", s);

    free(str);
    return 0;
}

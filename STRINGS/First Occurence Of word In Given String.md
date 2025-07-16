#  Program to Find the First Occurrence Index of a Word in a String in C

This program reads a main string and a word from the user, and finds the **index of the first occurrence** of that word in the string. If the word is not found, it notifies the user.

---

##  Source Code

```c
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int word_occu(char *str, char *sub) {
    int m = strlen(str);
    int n = strlen(sub);
    for (int i = 0; i <= m - n; i++) {
        int j;
        for (j = 0; j < n; j++) {
            if (str[i + j] != sub[j]) {
                break;
            }
        }
        if (j == n)
            return i;
    }
    return 0;
}

int main() {
    char *str = malloc(100 * sizeof(char));
    char *sub = malloc(10 * sizeof(char));
    if (str == NULL || sub == NULL) {
        printf("Memory allocation failed");
        return 1;
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';

    printf("Enter word: ");
    fgets(sub, 10, stdin);
    sub[strlen(sub) - 1] = '\0';

    int index = word_occu(str, sub);

    if (index)
        printf("The first occurrence index is: %d", index);
    else
        printf("Word is not found in given string");
}


Sample Output

Enter string: this is a simple string
Enter word: simple
The first occurrence index is: 10

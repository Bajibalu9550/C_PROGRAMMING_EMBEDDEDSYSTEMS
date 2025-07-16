# C Program to Reverse the Order of Words in a String

This program reverses the **word order** in a given input string using a two-step approach:

1. **Reverse the entire string.**
2. **Reverse each word in place.**

---

## Code

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <limits.h>

void reverse_words(char *str, int start, int end) {
    reverse(str, start, end);
    reverse_letters(str, start, end);
}

void reverse_letters(char *str, int start, int end) {
    int wst, wed;
    for (wst = wed = start; wed < end; wed++) {
        if (str[wed] == ' ') {
            continue;
        }
        wst = wed;
        while (str[wed] != ' ' && wed <= end) {
            wed++;
        }
        wed--;
        reverse(str, wst, wed);
    }
}

void reverse(char *str, int start, int end) {
    char temp;
    while (start <= end) {
        temp = str[start];
        str[start] = str[end];
        str[end] = temp;
        start++;
        end--;
    }
}

int main() {
    char *str = malloc(100 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed");
        return 1;
    }
    printf("Enter string Which contains words: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';
    reverse_words(str, 0, strlen(str)-1);
    printf("%s\n", str);
    free(str);
}


Input

Enter string Which contains words: Hello World from C

 Output

C from World Hello

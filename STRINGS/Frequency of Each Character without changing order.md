#  C Program to Count Frequency of Characters Using `unsigned char`

This program reads a string and prints the frequency of each character using a single array and safe indexing with `unsigned char`. This prevents invalid memory access when extended ASCII values are used.

---

##  Source Code

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#define max 128

void max_count(char *str, int freq[]) {
    int len = strlen(str);

    for (int i = 0; i < len; i++) {
        unsigned char ch = (unsigned char)str[i];
        freq[ch]++;
    }

    for (int i = 0; i < len; i++) {
        unsigned char ch = (unsigned char)str[i];
        if (freq[ch] > 0) {
            printf("%c   %d\n", ch, freq[ch]);
            freq[ch] = 0;
        }
    }
}

int main() {
    char *str = malloc(100 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed");
        return 1;
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';

    int freq[max] = {0};
    max_count(str, freq);

    free(str);
    return 0;
}

Sample Output:
---
Enter string: Hello C
H   1
e   1
l   2
o   1
    1
C   1

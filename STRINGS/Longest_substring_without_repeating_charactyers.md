# C Program to Find the Longest Substring Without Repeating Characters

## C Program

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

void longest(char *str) {
    int max = 0, start = 0;
    int index = 0;
    int freq[128];
    for (int i = 0; i < 128; i++) freq[i] = -1;

    for (int i = 0; str[i]; i++) {
        if (freq[str[i]] != -1 && freq[str[i]] >= start) {
            start = freq[str[i]] + 1;
        }
        freq[str[i]] = i;

        if (max < i - start + 1) {
            max = i - start + 1;
            index = start;
        }
    }

    printf("Substring: ");
    for (int i = index; i < index + max; i++) {
        printf("%c", str[i]);
    }
    printf("\n");
    printf("Longest length of the substring without repeating characters: %d", max);
}

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed");
        exit(1);
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';

    longest(str);
    free(str);
    return 0;
}
OUTPUT :
Enter string: abcabcbb
Substring: abc
Longest length of the substring without repeating characters: 3

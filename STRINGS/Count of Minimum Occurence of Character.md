#  Program to Find the Minimum Occurring Character in a String in C

##  Source Code

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define max 256
#define INT_MAX 2147483647

void max_freq(char *str, int freq[]) {
    int len = strlen(str);
    for (int i = 0; i < len; i++) {
        freq[(unsigned char)str[i]]++;
    }

    int mamm = INT_MAX;
    unsigned char ch;
    for (int i = 0; i < len; i++) {
        if (mamm > freq[(unsigned char)str[i]]) {
            mamm = freq[(unsigned char)str[i]];
            ch = str[i];
        }
    }

    printf("Minimum Occurrence Character '%c' count:%d\n", ch, mamm);
}

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed.");
        return 1;
    }

    printf("Enter String:");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';

    int freq[max] = {0};
    max_freq(str, freq);

    free(str);
    return 0;
}


Sample Output

Enter String: bajibalu pagolu
Minimum Occurrence Character 'j' count: 1

# C Program to Find the Highest Frequency Character in a String

## Program

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int freq[256] = {0}; 

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    
    str[strcspn(str, "\n")] = '\0';

    
    for (int i = 0; str[i] != '\0'; i++) {
        freq[(unsigned char)str[i]]++;
    }

    
    int max = 0;
    char maxChar;
    for (int i = 0; i < 256; i++) {
        if (freq[i] > max) {
            max = freq[i];
            maxChar = (char)i;
        }
    }

    printf("Highest frequency character: '%c' occurs %d times.\n", maxChar, max);

    return 0;
}

OUTPUT :
Enter a string: hello world
Highest frequency character: 'l' occurs 3 times.

#  Frequency Count of Characters in a String

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void freq_count(char *str) {
    int freq[256];
    for (int i = 0; i < 256; i++)
        freq[i] = -1;

    for (int i = 0; str[i] != '\0'; i++) {
        unsigned char ch = (unsigned char)str[i];
        if (freq[ch] != -1)
            continue;

        int count = 1;
        for (int j = i + 1; str[j] != '\0'; j++) {
            if (str[i] == str[j]) {
                count++;
                freq[(unsigned char)str[j]] = 0;
            }
        }
        freq[ch] = count;
    }

    for (int i = 0; str[i] != '\0'; i++) {
        unsigned char ch = (unsigned char)str[i];
        if (freq[ch] > 0) {
            printf("The character: %c and value: %d\n", ch, freq[ch]);
            freq[ch] = 0;
        }
    }
}

int main() {
    char *str = malloc(100 * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';

    freq_count(str);
    free(str);
    return 0;
}

**Sample Output**

Enter string: bajibalu
The character: b and value: 2
The character: a and value: 2
The character: j and value: 1
The character: i and value: 1
The character: l and value: 1
The character: u and value: 1

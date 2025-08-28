# C Program to Remove All Occurrences of a Word in a Given String

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[200], word[50], result[200];
    int i, j = 0, k, len, wlen, match;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter the word to remove: ");
    scanf("%s", word);

    len = strlen(str);
    wlen = strlen(word);

    for (i = 0; i < len; i++) {
        match = 1;
        if (str[i] == word[0]) {
            for (k = 0; k < wlen; k++) {
                if (str[i + k] != word[k]) {
                    match = 0;
                    break;
                }
            }
            if (match && (str[i + wlen] == ' ' || str[i + wlen] == '\0') && (i == 0 || str[i - 1] == ' ')) {
                i += wlen - 1;
                continue;
            }
        }
        result[j++] = str[i];
    }

    result[j] = '\0';
    printf("String after removing all occurrences of \"%s\": %s\n", word, result);

    return 0;
}

OUTPUT: 
Enter a string: this is a test and this test is simple
Enter the word to remove: test
String after removing all occurrences of "test": this is a and this is simple


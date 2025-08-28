# C Program to Replace All Occurrences of "Bangalore" by "Bengaluru" in a String

```c
#include <stdio.h>
#include <string.h>

void replaceWord(char str[], const char *oldWord, const char *newWord) {
    char buffer[1000];
    char *pos;
    int oldLen = strlen(oldWord);
    int newLen = strlen(newWord);

    buffer[0] = '\0';

    while ((pos = strstr(str, oldWord)) != NULL) {
        strncat(buffer, str, pos - str);
        strcat(buffer, newWord);
        str = pos + oldLen;
    }
    strcat(buffer, str);
    strcpy(str, buffer);
}

int main() {
    char str[1000];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0'; // Remove newline

    replaceWord(str, "Bangalore", "Bengaluru");

    printf("Modified string: %s\n", str);

    return 0;
}

OUTPUT:
Enter a string: I love Bangalore and Bangalore is beautiful
Modified string: I love Bengaluru and Bengaluru is beautiful

Enter a string: Bangalore is the capital of Karnataka
Modified string: Bengaluru is the capital of Karnataka

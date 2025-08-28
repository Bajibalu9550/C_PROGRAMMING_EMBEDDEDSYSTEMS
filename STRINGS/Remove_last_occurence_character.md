# C Program to Remove the Last Occurrence of a Character from a String

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], ch;
    int i, j, len, pos = -1;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter the character to remove: ");
    scanf("%c", &ch);

    len = strlen(str);

    for (i = len - 1; i >= 0; i--) {
        if (str[i] == ch) {
            pos = i;
            break;
        }
    }

    if (pos != -1) {
        for (j = pos; j < len; j++) {
            str[j] = str[j + 1];
        }
        printf("String after removing last occurrence of '%c': %s\n", ch, str);
    } else {
        printf("Character '%c' not found in the string.\n", ch);
    }

    return 0;
}

OUTPUT:
Enter a string: programming
Enter the character to remove: g
String after removing last occurrence of 'g': programmin

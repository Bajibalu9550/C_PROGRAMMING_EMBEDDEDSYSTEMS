# C Program to Remove the First Occurrence of a Character from a String

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], ch;
    int i, j, len, found = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    
    str[strcspn(str, "\n")] = '\0';

    printf("Enter the character to remove: ");
    scanf("%c", &ch);

    len = strlen(str);

    for (i = 0; i < len; i++) {
        if (str[i] == ch) {
            found = 1;
            
            for (j = i; j < len; j++) {
                str[j] = str[j + 1];
            }
            break;  
        }
    }

    if (found)
        printf("String after removing '%c': %s\n", ch, str);
    else
        printf("Character '%c' not found in the string.\n", ch);

    return 0;
}

OUTPUT:
Enter a string: programming
Enter the character to remove: g
String after removing 'g': proramming

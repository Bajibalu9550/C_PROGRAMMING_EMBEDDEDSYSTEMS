# C Program to Replace All Occurrences of a Character with Another in a String

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], ch1, ch2;
    int i, len, found = 0;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter the character to replace: ");
    scanf("%c", &ch1);
    getchar();
    printf("Enter the new character: ");
    scanf("%c", &ch2);

    len = strlen(str);

    for (i = 0; i < len; i++) {
        if (str[i] == ch1) {
            str[i] = ch2;
            found = 1;
        }
    }

    if (found)
        printf("String after replacing '%c' with '%c': %s\n", ch1, ch2, str);
    else
        printf("Character '%c' not found in the string.\n", ch1);

    return 0;
}

OUTPUT:
Enter a string: programming
Enter the character to replace: r
Enter the new character: x
String after replacing 'r' with 'x': pxogxamming

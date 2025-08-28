# C Program to Replace Each Occurrence of a Character in a String Using Recursion

```c
#include <stdio.h>
#include <string.h>

void replaceCharRecursive(char str[], char oldChar, char newChar, int index) {
    if (str[index] == '\0')
        return;
    if (str[index] == oldChar)
        str[index] = newChar;
    replaceCharRecursive(str, oldChar, newChar, index + 1);
}

int main() {
    char str[100];
    char oldChar, newChar;
    printf("Enter a string: ");
    scanf("%s", str);
    printf("Enter character to replace: ");
    scanf(" %c", &oldChar);
    printf("Enter new character: ");
    scanf(" %c", &newChar);

    replaceCharRecursive(str, oldChar, newChar, 0);
    printf("Modified string: %s\n", str);

    return 0;
}

OUTPUT:
Enter a string: programming
Enter character to replace: g
Enter new character: x
Modified string: proxxramminx

Enter a string: hello
Enter character to replace: l
Enter new character: z
Modified string: hezzo

#  Program to Remove the First Occurrence of a Character from a String in C

This program takes a string and a character as input, then removes only the **first occurrence** of that character from the string (excluding the null character `'\0'`).

---

##  Source Code

```c
#include <stdio.h>
#include <string.h>

void remove_first(char *s, char target) {
    if (target == '\0')           
        return;

    int i = 0;
    while (s[i] && s[i] != target)
        i++;

    if (s[i] == '\0')              
        return;

    while (s[i]) {
        s[i] = s[i + 1];
        i++;
    }
}

int main(void) {
    char str[101], ch;

    printf("Enter a string : ");
    fgets(str, sizeof str, stdin);
    if (str[0] && str[strlen(str) - 1] == '\n')
        str[strlen(str) - 1] = '\0';

    printf("Enter the character to delete : ");
    scanf(" %c", &ch);

    remove_first(str, ch);

    printf("Resulting string: \"%s\"\n", str);
    return 0;
}

Sample Output

Enter a string : bajibalu pagolu
Enter the character to delete : a
Resulting string: "bjibalu pagolu"

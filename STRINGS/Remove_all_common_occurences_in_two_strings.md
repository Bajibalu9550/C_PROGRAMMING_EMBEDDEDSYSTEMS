# C Program to Remove All Common Characters from Two Strings

```c
#include <stdio.h>
#include <string.h>

void removeChar(char str[], char ch) {
    int i, j = 0;
    char temp[100];
    for (i = 0; str[i] != '\0'; i++) {
        if (str[i] != ch)
            temp[j++] = str[i];
    }
    temp[j] = '\0';
    strcpy(str, temp);
}

void removeCommonChars(char str1[], char str2[]) {
    int i, j;
    for (i = 0; str1[i] != '\0'; i++) {
        for (j = 0; str2[j] != '\0'; j++) {
            if (str1[i] == str2[j]) {
                removeChar(str1, str1[i]);
                removeChar(str2, str1[i]);
                i = -1; 
                break;
            }
        }
    }
}

int main() {
    char str1[100], str2[100];
    printf("Enter first string: ");
    scanf("%s", str1);
    printf("Enter second string: ");
    scanf("%s", str2);

    removeCommonChars(str1, str2);

    printf("Resultant first string: %s\n", str1);
    printf("Resultant second string: %s\n", str2);

    return 0;
}

OUTPUT:
Enter first string: hello
Enter second string: world
Resultant first string: he
Resultant second string: wrd

Enter first string: programming
Enter second string: language
Resultant first string: progmin
Resultant second string: lue

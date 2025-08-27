# C Program to Convert Vowels in a String to Uppercase

## C Program

```c
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<ctype.h>

int isvowel(char ch) {
    ch = tolower(ch);
    return (ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u');
}

void convert(char *str) {
    while (*str != '\0') {
        if (isvowel(*str)) {
            *str = toupper(*str);
        }
        str++;
    }
}

int main() {
    char *str = malloc(100);
    if (str == NULL) {
        printf("Memory allocation failed");
        exit(1);
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str)-1] = '\0';

    convert(str);
    printf("Updated string: %s\n", str);

    free(str);
    return 0;
}

OUTPUT :

Enter string: programming in c

Updated string: prOgrAmmIng In c

#  C Program to Convert Lowercase Characters to Uppercase

This program reads a sentence from the user and converts all **lowercase characters** into **uppercase**.

---

##  Code

```c
#include <stdio.h>
#include <string.h>
#include <ctype.h>   

int main() {
    char str[200];

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);
    str[strlen(str)-1] = '\0';   

    for (int i = 0; str[i] != '\0'; i++) {
        if (islower(str[i])) {
            str[i] = toupper(str[i]);   
        }
    }

    printf("Converted sentence: %s\n", str);

    return 0;
}

OUTPUT :
Enter a sentence: bajiBaLu
Converted sentence: BAJIbAlU


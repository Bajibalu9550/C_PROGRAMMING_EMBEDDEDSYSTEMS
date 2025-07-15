# 🧵 Extract the substring from Given string

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int substring(char *str, char *sub) {
    int m = strlen(str);
    int n = strlen(sub);
    for (int i = 0; i <= m - n; i++) {
        int j;
        for (j = 0; j < n; j++) {
            if (str[i + j] != sub[j])
                break;
        }
        if (j == n)
            return i;
    }
    return 0;
}

int main() {
    char *str = malloc(100 * sizeof(char));
    char *sub = malloc(50 * sizeof(char));
    if (str == NULL || sub == NULL) {
        printf("Memory allocation failed");
        return 1;
    }

    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str) - 1] = '\0';

    printf("Enter substring: ");
    fgets(sub, 50, stdin);
    sub[strlen(sub) - 1] = '\0';

    int c = substring(str, sub);
    int n = strlen(sub);

    printf("\nSubstring is: ");
    for (int i = c; i < c + n; i++) {
        printf("%c", str[i]);
    }
    printf("\n");

    free(str);
    free(sub);
}


 **Sample Output**

Enter string: programming in C
Enter substring: in

Substring is: in

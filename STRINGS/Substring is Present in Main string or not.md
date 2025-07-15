#  Substring is present or not in given string

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
            return 1;
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
    if (c)
        printf("Substring is present");
    else
        printf("Substring is not present");
}


---

###  Sample Output

Enter string: welcome to coding
Enter substring: to
Substring is present

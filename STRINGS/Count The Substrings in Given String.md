#  Count of Substrings in Given String

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int substring(char *str, char *sub) {
    int m = strlen(str);
    int n = strlen(sub);
    int c = 0;
    for (int i = 0; i <= m - n; i++) {
        int j;
        for (j = 0; j < n; j++) {
            if (str[i + j] != sub[j])
                break;
        }
        if (j == n)
            ++c;
    }
    return c;
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

    int d = substring(str, sub);
    printf("count of substring present in given string: %d\n", d);

    free(str);
    free(sub);
}


**Sample Output**

Enter string: ababcababc
Enter substring: ab
count of substring present in given string: 3

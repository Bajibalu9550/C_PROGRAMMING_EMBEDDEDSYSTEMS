#  Longest Common Substring 

This version of your code attempts to find and print the **longest common substring** between two given strings, using a **brute-force approach** by sliding `str2` over `str1`.

---

## Code

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <limits.h>

void longest(char *str1, char *str2) {
    int m = strlen(str1);
    int n = strlen(str2);
    int max = INT_MIN, count, index = -1;

    for (int i = 0; i < m; i++) {
        int j, count = 0;
        for (j = 0; j < n; j++) {
            if (str1[i + j] != str2[j]) {
                count = 0;
            } else {
                count++;
                if (count > max) {
                    max = count;
                    index = i;
                }
            }
        }
    }

    printf("Length of Longest subsequence: %d\n", max);
    printf("Longest Common Substring is: ");
    for (int i = index; i < index + max; i++) {
        printf("%c", str1[i]);
    }
    printf("\n");
}

int main() {
    char *str1 = malloc(100 * sizeof(char));
    char *str2 = malloc(100 * sizeof(char));

    if (str1 == NULL || str2 == NULL) {
        printf("Memory allocation failed");
        return 1;
    }

    printf("Enter first string: ");
    fgets(str1, 100, stdin);
    str1[strlen(str1) - 1] = '\0';

    printf("Enter second string: ");
    fgets(str2, 100, stdin);
    str2[strlen(str2) - 1] = '\0';

    longest(str1, str2);

    free(str1);
    free(str2);
}

Sample Output
▶ Input:

Enter first string: abcdefgh
Enter second string: cde

✅ Output:

Length of Longest subsequence: 3
Longest Common Substring is: cde

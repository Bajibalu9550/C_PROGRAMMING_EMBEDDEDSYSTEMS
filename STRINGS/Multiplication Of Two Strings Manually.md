# Multiplication of Two Strings And Result is also String

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void multiplication(char *str1, char *str2) {
    int m = strlen(str1);
    int n = strlen(str2);
    int *result = malloc((m + n) * sizeof(int));
    if (result == NULL) {
        printf("Memory allocation failed");
        exit(1);
    }

    for (int i = m - 1; i >= 0; i--) {
        for (int j = n - 1; j >= 0; j--) {
            int mul = (str1[i] - '0') * (str2[j] - '0');
            int p1 = i + j;
            int p2 = i + j + 1;
            mul += result[p2];
            result[p2] = mul % 10;
            result[p1] += mul / 10;
        }
    }

    char *str3 = malloc(m + n + 1);
    if (str3 == NULL) {
        printf("Memory allocation failed");
        exit(1);
    }

    int index = 0;
    int leadingZero = 1;
    for (int i = 0; i < m + n; i++) {
        if (result[i] == 0 && leadingZero) {
            continue;
        }
        leadingZero = 0;
        str3[index++] = result[i] + '0';
    }
    str3[index] = '\0';
    printf("%s", str3);
    free(str3);
    free(result);
}

int main() {
    char *str1 = malloc(10 * sizeof(char));
    char *str2 = malloc(10 * sizeof(char));
    if (str1 == NULL || str2 == NULL) {
        printf("Memory Alloocation failed.");
        return 1;
    }

    printf("ENTER STRING1: ");
    fgets(str1, 10, stdin);
    str1[strlen(str1) - 1] = '\0';

    printf("Enter String2: ");
    fgets(str2, 10, stdin);
    str2[strlen(str2) - 1] = '\0';

    multiplication(str1, str2);
    free(str1);
    free(str2);
}


**Sample Output**

ENTER STRING1: 123
Enter String2: 456
56088

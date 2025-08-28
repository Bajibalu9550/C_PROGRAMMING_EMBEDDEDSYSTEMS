# C Function to Extract a Substring from a String

```c
#include <stdio.h>
#include <string.h>

void substring(char source[], char dest[], int start, int n) {
    int i;
    for (i = 0; i < n && source[start + i] != '\0'; i++) {
        dest[i] = source[start + i];
    }
    dest[i] = '\0';
}

int main() {
    char str[100], sub[100];
    int start, n;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';

    printf("Enter starting index: ");
    scanf("%d", &start);
    printf("Enter length of substring: ");
    scanf("%d", &n);

    substring(str, sub, start, n);

    printf("Extracted substring: %s\n", sub);

    return 0;
}

OUTPUT:
Enter a string: Devanshi
Enter starting index: 2
Enter length of substring: 4
Extracted substring: vans

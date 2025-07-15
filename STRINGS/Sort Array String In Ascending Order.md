#  Sorting of Array Strings in Ascending Order Using Bubble Sort

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char **str = (char **)malloc(5 * sizeof(char *));
    if (str == NULL) {
        printf("Memory allocation failed.");
        return 1;
    }

    for (int i = 0; i < 5; i++) {
        str[i] = malloc(100 * sizeof(char));
        if (str[i] == NULL) {
            printf("Memory allocation failed.");
            return 1;
        }

        printf("Enter string %d: ", i + 1);
        fgets(str[i], 100, stdin);
        str[i][strlen(str[i]) - 1] = '\0';
    }

    for (int i = 0; i < 5 - 1; i++) {
        for (int j = 0; j < 5 - i - 1; j++) {
            if (strcmp(str[j], str[j + 1]) > 0) {
                char *temp = str[j];
                str[j] = str[j + 1];
                str[j + 1] = temp;
            }
        }
    }

    printf("Sorted array of strings: ");
    for (int i = 0; i < 5; i++) {
        printf("%s ", str[i]);
    }
    printf("\n");

    for (int i = 0; i < 5; i++) {
        free(str[i]);
    }
    free(str);

    return 0;
}


**Sample Input/Output**

Enter string 1: orange
Enter string 2: apple
Enter string 3: banana
Enter string 4: mango
Enter string 5: grape
Sorted array of strings: apple banana grape mango orange 

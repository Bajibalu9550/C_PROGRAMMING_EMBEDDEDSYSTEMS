#  Program: Add Two 2D Arrays Using Double Pointers in C

This program uses dynamic memory allocation to create two 2D arrays, adds their elements, and stores the result in a third dynamically allocated 2D array. It demonstrates the use of double pointers (`int **`) in C.

---

##  Source Code

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int **a, **b, **sum, rows, col;

    printf("Enter Number of rows and columns: ");
    scanf("%d %d", &rows, &col);

    a = (int **)malloc(rows * sizeof(int *));
    b = (int **)malloc(rows * sizeof(int *));
    sum = (int **)malloc(rows * sizeof(int *));

    if (a == NULL || b == NULL || sum == NULL) {
        printf("Memory allocation failed.");
        return 1;
    }

    for (int i = 0; i < rows; i++) {
        a[i] = malloc(col * sizeof(int));
        b[i] = malloc(col * sizeof(int));
        sum[i] = malloc(col * sizeof(int));
        if (a[i] == NULL || b[i] == NULL || sum[i] == NULL) {
            printf("Memory allocation failed.");
            return 1;
        }
    }

    printf("Enter First array Elements: ");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < col; j++) {
            scanf("%d", &a[i][j]);
        }
    }

    printf("Enter Second array Elements: ");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < col; j++) {
            scanf("%d", &b[i][j]);
        }
    }

    printf("\nFirst array elements are:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < col; j++) {
            printf("%d ", *(*(a + i) + j));
        }
        printf("\n");
    }

    printf("\nSecond array elements are:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < col; j++) {
            printf("%d ", *(*(b + i) + j));
        }
        printf("\n");
    }

    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < col; j++) {
            *(*(sum + i) + j) = *(*(a + i) + j) + *(*(b + i) + j);
        }
    }

    printf("\nSum array is:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < col; j++) {
            printf("%d ", *(*(sum + i) + j));
        }
        printf("\n");
    }

    for (int i = 0; i < rows; i++) {
        free(a[i]);
        free(b[i]);
        free(sum[i]);
    }

    free(a);
    free(b);
    free(sum);

    return 0;
}

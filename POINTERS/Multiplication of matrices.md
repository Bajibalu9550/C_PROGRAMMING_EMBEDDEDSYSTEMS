#  Program: Multiply Two 2D Arrays Using Double Pointers in C

This program demonstrates how to perform matrix multiplication of two 2D arrays using dynamic memory allocation with double pointers (`int **`) in C.

---

##  Source Code

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int **a, **b, **product;
    int r1, c1, r2, c2;

    printf("Enter rows and columns for first matrix: ");
    scanf("%d %d", &r1, &c1);

    printf("Enter rows and columns for second matrix: ");
    scanf("%d %d", &r2, &c2);

    if (c1 != r2) {
        printf("Matrix multiplication not possible (columns of A != rows of B).\n");
        return 1;
    }

    a = (int **)malloc(r1 * sizeof(int *));
    b = (int **)malloc(r2 * sizeof(int *));
    product = (int **)malloc(r1 * sizeof(int *));

    if (a == NULL || b == NULL || product == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    for (int i = 0; i < r1; i++) {
        a[i] = malloc(c1 * sizeof(int));
        product[i] = malloc(c2 * sizeof(int));
        if (a[i] == NULL || product[i] == NULL) {
            printf("Memory allocation failed.\n");
            return 1;
        }
    }

    for (int i = 0; i < r2; i++) {
        b[i] = malloc(c2 * sizeof(int));
        if (b[i] == NULL) {
            printf("Memory allocation failed.\n");
            return 1;
        }
    }

    printf("Enter elements of first matrix:\n");
    for (int i = 0; i < r1; i++)
        for (int j = 0; j < c1; j++)
            scanf("%d", &a[i][j]);

    printf("Enter elements of second matrix:\n");
    for (int i = 0; i < r2; i++)
        for (int j = 0; j < c2; j++)
            scanf("%d", &b[i][j]);

    
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            product[i][j] = 0;

            for (int k = 0; k < c1; k++) {
                product[i][j] += a[i][k] * b[k][j];
            }
        }
    }

    printf("\nProduct matrix is:\n");
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            printf("%d ", product[i][j]);
        }
        printf("\n");
    }

    for (int i = 0; i < r1; i++) {
        free(a[i]);
        free(product[i]);
    }
    for (int i = 0; i < r2; i++) {
        free(b[i]);
    }

    free(a);
    free(b);
    free(product);

    return 0;
}

# Write a  program to add two matrices using pointers.

```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int rows, cols;

    printf("Enter number of rows: ");
    scanf("%d", &rows);
    printf("Enter number of columns: ");
    scanf("%d", &cols);

    
    int *A = malloc(rows * cols * sizeof(int));
    int *B = malloc(rows * cols * sizeof(int));
    int *C = malloc(rows * cols * sizeof(int));

    if (A == NULL || B == NULL || C == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    printf("Enter elements of matrix A:\n");
    for (int i = 0; i < rows * cols; i++)
        scanf("%d", A + i);

    printf("Enter elements of matrix B:\n");
    for (int i = 0; i < rows * cols; i++)
        scanf("%d", B + i);

    
    for (int i = 0; i < rows * cols; i++)
        *(C + i) = *(A + i) + *(B + i);

    
    printf("Sum of matrices:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++)
            printf("%d ", *(C + i * cols + j));
        printf("\n");
    }

    
    free(A);
    free(B);
    free(C);

    return 0;
}

```

__OUTPUT :__

Enter number of rows: 2

Enter number of columns: 3

Enter elements of matrix A:

1 2 3 4 5 6

Enter elements of matrix B:

6 5 4 3 2 1

Sum of matrices:

7 7 7

7 7 7

#  Write a program to multiply two matrix using pointers.
```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int r1, c1, r2, c2;

    printf("Enter rows and columns of first matrix: ");
    scanf("%d %d", &r1, &c1);
    printf("Enter rows and columns of second matrix: ");
    scanf("%d %d", &r2, &c2);

    if (c1 != r2) {
        printf("Matrix multiplication not possible.\n");
        return 1;
    }

    int **A = malloc(r1 * sizeof(int*));
    int **B = malloc(r2 * sizeof(int*));
    int **C = malloc(r1 * sizeof(int*));

    for (int i = 0; i < r1; i++)
        A[i] = malloc(c1 * sizeof(int));
    for (int i = 0; i < r2; i++)
        B[i] = malloc(c2 * sizeof(int));
    for (int i = 0; i < r1; i++)
        C[i] = malloc(c2 * sizeof(int));

    printf("Enter elements of matrix A:\n");
    for(int i = 0; i < r1; i++)
        for(int j = 0; j < c1; j++)
            scanf("%d", &A[i][j]);

    printf("Enter elements of matrix B:\n");
    for(int i = 0; i < r2; i++)
        for(int j = 0; j < c2; j++)
            scanf("%d", &B[i][j]);

    
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < c1; k++)
                *(*(C+i)+j) += (*(*(A+i)+k)) * (*(*(B+k)+j));
        }
    }

    printf("Product of matrices:\n");
    for (int i = 0; i < r1; i++) {
        for (int j = 0; j < c2; j++)
            printf("%d ", *(*(C+i)+j));
        printf("\n");
    }

    // Free memory
    for(int i=0;i<r1;i++) 
        free(A[i]);
    for(int i=0;i<r2;i++) 
        free(B[i]);
    for(int i=0;i<r1;i++) 
        free(C[i]);
    free(A); 
    free(B); 
    free(C);

    return 0;
}

```

__OUTPUT :__

Enter rows and columns of first matrix: 2 3

Enter rows and columns of second matrix: 3 2

Enter elements of matrix A:

1 2 3

4 5 6

Enter elements of matrix B:

7 8

9 10

11 12

Product of matrices:

58 64

139 154

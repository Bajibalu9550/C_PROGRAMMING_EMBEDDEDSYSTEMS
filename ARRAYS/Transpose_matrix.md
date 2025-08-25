# Transpose of a matrix

```
#include <stdio.h>

int main() {
    int rows, cols;

    printf("Enter number of rows: ");
    scanf("%d", &rows);
    printf("Enter number of columns: ");
    scanf("%d", &cols);

    int A[rows][cols], T[cols][rows];

    
    printf("Enter elements of the matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            scanf("%d", &A[i][j]);
        }
    }

    
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            T[j][i] = A[i][j];
        }
    }

    
    printf("Transpose of the matrix:\n");
    for (int i = 0; i < cols; i++) {
        for (int j = 0; j < rows; j++) {
            printf("%d ", T[i][j]);
        }
        printf("\n");
    }

    return 0;
}

```

__OUTPUT :__

Enter number of rows: 2

Enter number of columns: 3

Enter elements of the matrix:

1 2 3

4 5 6

Transpose of the matrix:

1 4

2 5

3 6

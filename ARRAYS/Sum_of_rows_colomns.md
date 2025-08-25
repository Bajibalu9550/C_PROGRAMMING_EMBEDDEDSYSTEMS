# Find the sum of rows and coloumns of matrix

```
#include <stdio.h>

int main() {
    int rows, cols;

    printf("Enter number of rows: ");
    scanf("%d", &rows);
    printf("Enter number of columns: ");
    scanf("%d", &cols);

    int A[rows][cols];

  
    printf("Enter elements of the matrix:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            scanf("%d", &A[i][j]);
        }
    }

    
    printf("Sum of each row:\n");
    for (int i = 0; i < rows; i++) {
        int rowSum = 0;
        for (int j = 0; j < cols; j++) {
            rowSum += A[i][j];
        }
        printf("Row %d = %d\n", i + 1, rowSum);
    }

   
    printf("Sum of each column:\n");
    for (int j = 0; j < cols; j++) {
        int colSum = 0;
        for (int i = 0; i < rows; i++) {
            colSum += A[i][j];
        }
        printf("Column %d = %d\n", j + 1, colSum);
    }

    return 0;
}

```

__OUTPUT :__

Enter number of rows: 3

Enter number of columns: 3

Enter elements of the matrix:

1 2 3

4 5 6

7 8 9

Sum of each row:

Row 1 = 6

Row 2 = 15

Row 3 = 24

Sum of each column:

Column 1 = 12

Column 2 = 15

Column 3 = 18



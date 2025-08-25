# Multiplication of two square matrices

```
#include <stdio.h>

int main() {
    int n;

    printf("Enter size of square matrices (n x n): ");
    scanf("%d", &n);

    int A[n][n], B[n][n], C[n][n];

    
    printf("Enter elements of first matrix:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &A[i][j]);
        }
    }

    
    printf("Enter elements of second matrix:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &B[i][j]);
        }
    }


    
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            c[i][j]=0;
            for (int k = 0; k < n; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }

  
    printf("Resultant Matrix after Multiplication:\n");
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            printf("%d ", C[i][j]);
        }
        printf("\n");
    }

    return 0;
}

```

__OUTPUT :__

Enter size of square matrices (n x n): 2

Enter elements of first matrix:

1 2

3 4

Enter elements of second matrix:

5 6

7 8

Resultant Matrix after Multiplication:

19 22

43 50


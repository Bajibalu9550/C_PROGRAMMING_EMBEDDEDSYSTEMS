# Program to dynamically allocate a 2-D array using array of pointers

```
#include <stdio.h>
#include <stdlib.h>

int main() {
    int rows, cols;
    int **arr;

    printf("Enter number of rows: ");
    scanf("%d", &rows);
    printf("Enter number of columns: ");
    scanf("%d", &cols);

    
    arr = (int **)malloc(rows * sizeof(int *));
    if (arr == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    
    for (int i = 0; i < rows; i++) {
        arr[i] = (int *)malloc(cols * sizeof(int));
        if (arr[i] == NULL) {
            printf("Memory allocation failed for row %d.\n", i);
            return 1;
        }
    }

    
    printf("Enter elements of the 2-D array:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            scanf("%d", &arr[i][j]);
        }
    }

   
    printf("The 2-D array is:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            printf("%d ", arr[i][j]);
        }
        printf("\n");
    }

    
    for (int i = 0; i < rows; i++) {
        free(arr[i]);
    }
    free(arr);

    return 0;
}

```

__OUTPUT :__

Enter number of rows: 3

Enter number of columns: 4

Enter elements of the 2-D array:

1 2 3 4

5 6 7 8

9 10 11 12

The 2-D array is:

1 2 3 4

5 6 7 8

9 10 11 12

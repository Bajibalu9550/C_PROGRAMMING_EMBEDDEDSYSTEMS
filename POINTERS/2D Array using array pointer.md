#  Program: Dynamically Allocate a 2D Array Using Array of Pointers in C

This program demonstrates how to dynamically allocate a 2D array using an **array of pointers**, input data into it, display it, and then deallocate the memory.

---

## Source Code

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int rows, cols;
    int **arr;

    printf("Enter number of rows and columns: ");
    scanf("%d %d", &rows, &cols);

    
    arr = (int **)malloc(rows * sizeof(int *));
    if (arr == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    
    for (int i = 0; i < rows; i++) {
        arr[i] = (int *)malloc(cols * sizeof(int));
        if (arr[i] == NULL) {
            printf("Memory allocation failed at row %d.\n", i);
            return 1;
        }
    }

  
    printf("Enter elements of the 2D array:\n");
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            scanf("%d", &arr[i][j]);
        }
    }

    
    printf("\n2D Array Elements:\n");
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

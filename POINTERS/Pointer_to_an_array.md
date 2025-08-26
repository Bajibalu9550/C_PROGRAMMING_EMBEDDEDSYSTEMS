# Program to print  elements of a 2-D array by subscripting a pointer to an array variable.

```
#include <stdio.h>

int main() {
    int a[3][4] = {
        {1, 2, 3, 4},
        {5, 6, 7, 8},
        {9, 10, 11, 12}
    };

    int (*p)[4];   
    p = a;         

    printf("Accessing elements using pointer to array:\n");
    for(int i=0; i<3; i++) {
        for(int j=0; j<4; j++) {
            printf("%d ", p[i][j]);   
          
        }
        printf("\n");
    }

    return 0;
}

```

__OUTPUT :__

Accessing elements using pointer to array:

1 2 3 4

5 6 7 8

9 10 11 12


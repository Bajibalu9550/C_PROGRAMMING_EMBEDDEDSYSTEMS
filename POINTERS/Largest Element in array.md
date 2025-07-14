# Find the Largest Element in a Dynamically Allocated Array (C)

This C program demonstrates how to use **dynamic memory allocation** (`malloc`) to create an integer array and find the **largest element** using **pointers**.

---

##  Source Code

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);

    
    int *a = malloc(n * sizeof(int));

    if (a == NULL) {
        printf("Memory allocation failed.\n");
        return 1;  
    }

    
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }

    
    int max = *a;  
    for (int i = 1; i < n; i++) {
        if (max < *(a + i)) {
            max = *(a + i);
        }
    }

    free(a);  

    printf("Largest element: %d\n", max);

    return 0;
}

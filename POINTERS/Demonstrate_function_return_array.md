#  Write a  program to demonstrate how a function returns a pointer

```
#include <stdio.h>
#include <stdlib.h>


int* createArray(int size) {
    int *arr = malloc(size * sizeof(int));
    if (arr == NULL) {
        printf("Memory allocation failed\n");
        return NULL;
    }

    for (int i = 0; i < size; i++) {
        arr[i] = i + 1;  
    }

    return arr;  
}

int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);

    int *ptr = createArray(n);  

    if (ptr == NULL) {
        return 1;
    }

    printf("Array elements in main function: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", ptr[i]);
    }
    printf("\n");

    free(ptr);  
    return 0;
}

```

__OUTPUT :__

Enter size of array: 5

Array elements in main function: 1 2 3 4 5

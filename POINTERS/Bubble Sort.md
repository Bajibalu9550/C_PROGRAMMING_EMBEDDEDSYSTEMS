# Bubble Sort in C Using Dynamic Memory and Arithmetic Swap

This program sorts an array of integers in **ascending order** using **bubble sort** with dynamic memory allocation. It uses an **arithmetic swap** (no temporary variable) to exchange values.

---

##  Source Code

```c
#include <stdio.h>
#include <stdlib.h>

void sort(int *a, int n) {
    for (int i = 0; i < n - 1; i++) {
        int swap = 0;
        for (int j = 0; j < n - 1 - i; j++) {
            if (*(a + j) > *(a + j + 1)) {
                *(a + j) = (*(a + j) + *(a + j + 1)) - (*(a + j + 1) = *(a + j));
                swap = 1;
            }
        }
        if (!swap)
            break;
    }
}

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

    sort(a, n);

    printf("Sorted Array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", a[i]);
    }
    printf("\n");

    free(a);
    return 0;
}

# Write a program to print the value of array elements  using pointers and subscript notation
---
```
#include <stdio.h>

int main() {
    int n;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];

    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    printf("\nUsing Subscript Notation:\n");
    for (int i = 0; i < n; i++) {
        printf("arr[%d] = %d\n", i, arr[i]);
    }

    printf("\nUsing Pointer Notation:\n");
    for (int i = 0; i < n; i++) {
        printf("*(arr + %d) = %d\n", i, *(arr + i));
    }

    return 0;
}


```

__OUTPUT :__

Enter number of elements: 5

Enter 5 elements:

11 22 33 44 55

Using Subscript Notation:

arr[0] = 11

arr[1] = 22

arr[2] = 33

arr[3] = 44

arr[4] = 55

Using Pointer Notation:

*(arr + 0) = 11

*(arr + 1) = 22

*(arr + 2) = 33

*(arr + 3) = 44

*(arr + 4) = 55


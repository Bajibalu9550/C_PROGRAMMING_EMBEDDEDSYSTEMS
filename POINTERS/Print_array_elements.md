# Print the value of array elements  using pointers and subscript notation.
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

    printf("\nPrinting using subscript notation:\n");
    for (int i = 0; i < n; i++) {
        printf("arr[%d] = %d\n", i, arr[i]);
    }

    printf("\nPrinting using pointer notation:\n");
    for (int i = 0; i < n; i++) {
        printf("*(arr + %d) = %d\n", i, *(arr + i));
    }

    return 0;
}

```

__OUTPUT :__

Enter number of elements: 5

Enter 5 elements:

10 20 30 40 50

Printing using subscript notation:

arr[0] = 10

arr[1] = 20

arr[2] = 30

arr[3] = 40

arr[4] = 50

Printing using pointer notation:

*(arr + 0) = 10

*(arr + 1) = 20

*(arr + 2) = 30

*(arr + 3) = 40

*(arr + 4) = 50


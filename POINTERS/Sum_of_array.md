# Write a program that calculates the sum of all elements in an integer array using pointer arithmetic

```
#include <stdio.h>

int main() {
    int n, i, sum = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];

    printf("Enter %d elements:\n", n);
    for(i = 0; i < n; i++) {
        scanf("%d", (arr + i));
    }

    int *ptr = arr;

    for(i = 0; i < n; i++) {
        sum += *(ptr + i);
    }

    printf("Sum of array elements = %d\n", sum);

    return 0;
}

```

__OUTPUT :__

Enter number of elements: 5

Enter 5 elements:

1 2 3 4 5

Sum of array elements = 15



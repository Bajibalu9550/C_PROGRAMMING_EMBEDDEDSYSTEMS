# Logic to search an element in an array using pointers.

```
#include <stdio.h>

int main() {
    int n, key, found = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++)
        scanf("%d", arr + i);

    printf("Enter element to search: ");
    scanf("%d", &key);

    int *ptr = arr;
    for (int i = 0; i < n; i++) {
        if (*(ptr + i) == key) {
            printf("Element %d found at index %d\n", key, i);
            found = 1;
            break;
        }
    }

    if (!found)
        printf("Element %d not found in the array\n", key);

    return 0;
}

```

__OUTPUT :__

Enter number of elements: 5

Enter 5 elements:

10 20 30 40 50

Enter element to search: 30

Element 30 found at index 2

# Program to print the value and address of  elements of an array using pointers notation

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

    printf("\nValue and Address of Array Elements:\n");
    for (int i = 0; i < n; i++) {
        printf("Element %d: Value = %d, Address = %p\n", i, *(arr + i), (arr + i));
    }

    return 0;
}

```

__OUTPUT :__

Enter number of elements: 5

Enter 5 elements:

10 20 30 40 50

Value and Address of Array Elements:

Element 0: Value = 10, Address = 0x7ffeef4b8a20

Element 1: Value = 20, Address = 0x7ffeef4b8a24

Element 2: Value = 30, Address = 0x7ffeef4b8a28

Element 3: Value = 40, Address = 0x7ffeef4b8a2c

Element 4: Value = 50, Address = 0x7ffeef4b8a30

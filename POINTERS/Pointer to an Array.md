#  Program: Pointer to an Array in C

This program shows how to declare a **pointer to an entire array**, access array elements using this pointer, and print their values and addresses.

---

##  Source Code

```c
#include <stdio.h>

int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    int (*ptr)[5] = &arr;  
    printf("Accessing array elements using pointer to an array:\n");

    for (int i = 0; i < 5; i++) {
        printf("Value: %d\tAddress: %p\n", (*ptr)[i], &(*ptr)[i]);
    }

    return 0;
}

**Sample Output**

Accessing array elements using pointer to an array:
Value: 10    Address: 0x...
Value: 20    Address: 0x...
Value: 30    Address: 0x...
Value: 40    Address: 0x...
Value: 50    Address: 0x...

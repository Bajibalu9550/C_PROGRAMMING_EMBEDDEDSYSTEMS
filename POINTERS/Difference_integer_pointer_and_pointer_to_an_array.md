#  Program to understand the difference between a  to   an integer and a pointer to an array of integers.
---
```
#include <stdio.h>

int main() {
    int arr[5] = {10, 20, 30, 40, 50};

    int *p;          // pointer to an integer
    int (*ptr)[5];   // pointer to an array of 5 integers

    p = arr;     // points to first element (10)
    ptr = &arr;  // points to the whole array

    printf("Array base address: %p\n", arr);

    printf("\n--- Pointer to int (p) ---\n");
    printf("p = %p, *p = %d\n", p, *p);
    printf("p+1 = %p, *(p+1) = %d\n", p+1, *(p+1));

    printf("\n--- Pointer to array of 5 ints (ptr) ---\n");
    printf("ptr = %p, *ptr = %p\n", ptr, *ptr);
    printf("ptr+1 = %p  (moves by 5 integers)\n", ptr+1);

    return 0;
}

```

__OUTPUT :__

Array base address: 0x7ffeefbff590


--- Pointer to int (p) ---

p = 0x7ffeefbff590, *p = 10

p+1 = 0x7ffeefbff594, *(p+1) = 20


--- Pointer to array of 5 ints (ptr) ---

ptr = 0x7ffeefbff590, *ptr = 0x7ffeefbff590

ptr+1 = 0x7ffeefbff5a4  (moves by 5 integers)


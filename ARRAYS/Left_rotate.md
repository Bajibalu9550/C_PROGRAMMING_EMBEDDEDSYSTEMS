# Array Rotation Using Reversal Algorithm (C Program)

This program performs **left rotation** of an array by `k` positions using the **reversal algorithm**.  
It uses the **XOR swap technique** to reverse elements in place.

---

## Algorithm Steps
1. Reverse the first `k` elements.
2. Reverse the remaining `n - k` elements.
3. Reverse the entire array.

---

##  C Program
```c
#include<stdio.h>

void reverse(int *a, int start, int end) {
    while (start < end) {
        a[start] = a[start] ^ a[end];
        a[end]   = a[start] ^ a[end];
        a[start] = a[start] ^ a[end];
        start++;
        end--;
    }
}

int main() {
    int n;
    printf("Enter array size: ");
    scanf("%d", &n);

    int a[n];
    printf("Enter array elements: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }

    int k;
    printf("Enter Positions: ");
    scanf("%d", &k);

    k = k % n;  

    reverse(a, 0, k - 1);
    reverse(a, k, n - 1);
    reverse(a, 0, n - 1);

    printf("Array after left rotation: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", a[i]);
    }

    return 0;
}
```

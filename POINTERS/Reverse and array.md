#  Reverse an Array Using Pointers in C

This C program reverses an array **in-place** using **pointer arithmetic** and **without using a temporary variable** — instead, it uses arithmetic operations to swap values.

---

## Source Code

```c
#include <stdio.h>

void reverse(int *a, int n) {
    int s = 0, e = n - 1;
    while (s < e) {
        *(a + s) = (*(a + s) + *(a + e)) - (*(a + e) = *(a + s));
        s++;
        e--;
    }
}

int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);

    int a[n];  

    printf("Enter %d elements:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }

    reverse(a, n);

    printf("Reversed array is: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", a[i]);
    }

    return 0;
}

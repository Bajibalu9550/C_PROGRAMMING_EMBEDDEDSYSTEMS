# Partial Array Reversal Using XOR Swap in C

This program reverses a **specific portion** of an array (from index `k` to `l`) using the **XOR swap technique**.  
Instead of rotating, it directly reverses the subarray between the given positions.

---

## 🔹 Algorithm Steps
1. Input the array size `n` and the elements.  
2. Input two positions `k` and `l`.  
3. Reverse the elements in the range `[k, l]` (1-based indexing in this program).  
4. Print the final array.

---

## 🔹 C Program
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

    int k, l;
    printf("Enter Positions (k l): ");
    scanf("%d %d", &k, &l);

    k = k % n;
    l = l % n;
    reverse(a, k - 1, l - 1);

    printf("Array after reversing subarray: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", a[i]);
    }
```
    return 0;
}

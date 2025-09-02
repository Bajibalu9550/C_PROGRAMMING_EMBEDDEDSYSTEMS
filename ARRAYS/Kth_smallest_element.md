# K-th Smallest Element in an Array (C Program)

This program finds the **k-th smallest element** in an array.  
It sorts the array using a simple **nested loop** (selection-sort style) and then prints the element at position `k`.

---

## 🔹 C Program
```c
#include<stdio.h>
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
    printf("Enter position number: ");
    scanf("%d", &k);

    
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (a[i] > a[j]) {
                // Swap without using temp variable
                a[i] = (a[i] + a[j]) - (a[j] = a[i]);
            }
        }
    }

   
    printf("K-th Smallest element is: %d\n", a[k - 1]);

    return 0;
}

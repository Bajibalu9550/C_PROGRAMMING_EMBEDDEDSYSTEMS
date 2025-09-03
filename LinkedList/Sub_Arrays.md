# C Program to Print All Subarrays of an Array

```c
#include <stdio.h>

int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);
    
    int a[n];
    printf("Enter array elements: ");
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }

    printf("All subarrays are:\n");
    
    for (int start = 0; start < n; start++) {
        for (int end = start; end < n; end++) {
            printf("[");
            for (int k = start; k <= end; k++) {
                printf("%d", a[k]);
                if (k != end) 
                    printf(",");
            }
            printf("]\n");
        }
    }

    return 0;
}
```

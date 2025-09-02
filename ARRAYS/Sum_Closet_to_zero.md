# C Program to Find Two Elements Whose Sum is Closest to Zero in an Array

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter array elements:\n");
    for(int i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    int min_sum = arr[0] + arr[1];
    int pair1 = arr[0], pair2 = arr[1];

    for(int i = 0; i < n-1; i++) {
        for(int j = i+1; j < n; j++) {
            int sum = arr[i] + arr[j];
            if(abs(sum) < abs(min_sum)) {
                min_sum = sum;
                pair1 = arr[i];
                pair2 = arr[j];
            }
        }
    }

    printf("Two elements whose sum is closest to zero: %d and %d\n", pair1, pair2);
    printf("Their sum: %d\n", min_sum);

    return 0;
}
```

# C Program to Find the Sum of All Elements of an Array Using Recursion

```c
#include <stdio.h>

int sumArray(int arr[], int start, int end) {
    if(start == end)
        return arr[start];

    int mid = (start + end) / 2;

    return sumArray(arr, start, mid) + sumArray(arr, mid + 1, end);
}

int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter array elements: ");
    for(int i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    int total = sumArray(arr, 0, n - 1);
    printf("Sum of all elements: %d\n", total);

    return 0;
}
```

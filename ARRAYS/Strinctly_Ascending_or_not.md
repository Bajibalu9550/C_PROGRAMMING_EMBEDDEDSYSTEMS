# C Program to Check if an Array is in Strict Ascending Order Using Recursion

```c
#include <stdio.h>

int isAscending(int arr[], int n) {
   
    if (n == 0 || n == 1)
        return 1;

    if (arr[n-2] >= arr[n-1])
        return 0;

    return isAscending(arr, n-1);
}

int main() {
    int n;
    printf("Enter size of array: ");
    scanf("%d", &n);

    int arr[n];
    printf("Enter array elements: ");
    for(int i = 0; i < n; i++)
        scanf("%d", &arr[i]);

    if(isAscending(arr, n))
        printf("The array is in strict ascending order.\n");
    else
        printf("The array is NOT in strict ascending order.\n");

    return 0;
}
```

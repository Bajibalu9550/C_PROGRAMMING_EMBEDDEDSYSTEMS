# C Program to Find the Sum of Even Numbers in an Array Using Recursion

```c
#include<stdio.h>

int sum(int *a, int n) {
    static int sum1 = 0;
    if(n < 0)
        return sum1;
    if(a[n] % 2 == 0)
        sum1 += a[n];
    return sum(a, n - 1);
}

int main() {
    int n;
    printf("Enter array size: ");
    scanf("%d", &n);

    int a[n];
    printf("Enter array elements: ");
    for(int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }

    printf("Sum of all even numbers: %d\n", sum(a, n - 1));

    return 0;
}
```

# Write a program to print array of pointer

```
#include <stdio.h>

int main() {
    
    char *arr[] = {"Apple", "Banana", "Cherry", "Date", "Elderberry"};
    int n = sizeof(arr) / sizeof(arr[0]);  // Number of elements

    printf("Array of pointers contains:\n");
    for(int i = 0; i < n; i++) {
        printf("%s\n", arr[i]);
    }

    return 0;
}

```

__OUTPUT :__

Apple

Banana

Cherry

Date

Elderberry

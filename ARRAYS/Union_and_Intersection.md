# C Program to Find the Union and Intersection of Two Arrays

```c
#include <stdio.h>

int main() {
    int n1, n2;
    printf("Enter size of first array: ");
    scanf("%d", &n1);
    int arr1[n1];
    printf("Enter elements of first array:\n");
    for(int i = 0; i < n1; i++)
        scanf("%d", &arr1[i]);

    printf("Enter size of second array: ");
    scanf("%d", &n2);
    int arr2[n2];
    printf("Enter elements of second array:\n");
    for(int i = 0; i < n2; i++)
        scanf("%d", &arr2[i]);

    int unionArr[n1 + n2];
    int k = 0;

   
    for(int i = 0; i < n1; i++)
        unionArr[k++] = arr1[i];

    
    for(int i = 0; i < n2; i++) {
        int found = 0;
        for(int j = 0; j < n1; j++) {
            if(arr2[i] == arr1[j]) {
                found = 1;
                break;
            }
        }
        if(!found)
            unionArr[k++] = arr2[i];
    }

    printf("Union of the two arrays: ");
    for(int i = 0; i < k; i++)
        printf("%d ", unionArr[i]);
    printf("\n");

    printf("Intersection of the two arrays: ");
    for(int i = 0; i < n1; i++) {
        for(int j = 0; j < n2; j++) {
            if(arr1[i] == arr2[j]) {
                printf("%d ", arr1[i]);
                break;
            }
        }
    }
    printf("\n");

    return 0;
}
```

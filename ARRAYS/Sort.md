# C Program to Move all negative elements to left side and all positive elements to right side of array

```c
#include<stdio.h>
void sort(int *a,int start,int end){
    while(start<end){
        while(a[start]<0 && start<end){
            start++;
        }
        while(a[end]>=0 && start<end){
            end--;
        }
        a[start] = (a[start] + a[end]) - (a[end] = a[start]); // swap without temp variable
        start++;
        end--;
    }
}
int main(){
    int n;
    printf("Enter size of arrray: ");
    scanf("%d",&n);
    int a[n];
    printf("Enter element: ");
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    sort(a,0,n-1);
    printf("Sorted array: ");
    for(int i=0;i<n;i++){
        printf("%d ",a[i]);
    }
}
```

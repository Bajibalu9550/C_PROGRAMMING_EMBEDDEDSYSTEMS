# C Program to Find the Next Greater Element in an Array

```c
#include<stdio.h>
int main(){
    int n;
    printf("Enter size of array: ");
    scanf("%d",&n);
    int a[n];
    printf("Enter array elements: ");
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    
    for(int i=0;i<n;i++){
        int found=0;
        for(int j=i+1;j<n;j++){
            if(a[i]<a[j]){
                found=1;
                a[i]=a[j];
                break;
            }
        }
        if(!found){
            a[i]=-1;
        }
    }
    printf("Next_gen array: ");
    for(int i=0;i<n;i++){
        printf("%d ",a[i]);
    }
}
```

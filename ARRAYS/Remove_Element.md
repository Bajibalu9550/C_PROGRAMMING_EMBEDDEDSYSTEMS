# Delete an element at a desired position from an array

```
#include<stdio.h>
int main(){
    int n;
    printf("Enter array size: ");
    scanf("%d",&n);
    int a[n];
    printf("Enter array elements: ");
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    int pos;
    printf("Enter position you want to delete: ");
    scanf("%d",&pos);
    for(int i=0;i<n-1;i++){
        if(i>=pos){
            a[i]=a[i+1];
        }
    }

    printf("Updated array: ");
    for(int i=0;i<n-1;i++){
        printf("%d ",a[i]);
    }
}
```

__OUTPUT :__

Enter array size: 5

Enter array elements: 1 2 3 4 5

Enter position you want to delete: 2

Updated array: 1 2 4 5

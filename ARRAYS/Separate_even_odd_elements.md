# To separate odd and even integers into separate arrays

````
#include<stdio.h>
void separate(int *a,int n){
    int evensize=0,oddsize=0;
    int even[10],odd[10];
    for(int i=0;i<n;i++){
        if(a[i]%2==0){
            even[evensize++]=a[i];
        }
        else {
            odd[oddsize++]=a[i];
        }
    }
    printf("Even array: ");
    for(int i=0;i<evensize;i++){
        printf("%d ",even[i]);
    }
    printf("\n");
    printf("Odd Numbers array: ");
    for(int i=0;i<oddsize;i++){
        printf("%d ",odd[i]);
    }
}
int main(){
    int n;
    printf("Enter array size: ");
    scanf("%d",&n);
    int a[n];
    printf("Enter array elements: ");
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    separate(a,n);
}
````

__OUTPUT :__

Enter array size: 8

Enter array elements: 1 2 3 4 5 6 7 8

Even Numbers array: 2 4 6 8

Odd Numbers array: 1 3 5 7

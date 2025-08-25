# Unique Elements in an Array
````
#include<stdio.h>
void unique(int *a,int n){
    for(int i=0;i<n;i++){
        int found=0;
        for(int j=0;j<n;j++){
            if(a[i]==a[j]){
                found++;
            }
        }
        if(found==1){
            printf("%d ",a[i]);
        }
    }
}
int main(){
  int n;
  printf("Enetr array size: ");
  scanf("%d",&n);
  int a[n];
  printf("Enter array elements: ");
  for(int i=0;i<n;i++){
    scanf("%d",&a[i]);
  }
printf("Unique array: ");
  unique(a,n);
}
````

__OUTPUT :__

Enter array size: 5

Enter array elements: 1 2 3 2 1

Unique array: 3

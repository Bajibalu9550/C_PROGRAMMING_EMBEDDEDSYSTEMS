# Reverse an array Using two pointer concept

```
#include<stdio.h>
void reverse(int *a,int start,int end){
  while(start<end){
  *(a+end) = (*(a+start) + *(a+end)) - (*(a+start) = *(a+end));
  start++;
  end--;
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
  reverse(a,0,n-1);
  
  printf("Reversed array: ");
  for(int i=0;i<n;i++){
    printf("%d",a[i]);
  }
}

```

__OUTPUT :__

Enter array size: 5

Enter array elements: 1 2 3 4 5

Reversed array: 5 4 3 2 1

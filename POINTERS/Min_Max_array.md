# Write a program to find the maximum and minimum elements in an array using pointers

```
#include<stdio.h>
int main(){
    int a[5]={1,2,3,4,5};
    int min=a[0];
    int max=a[0];
    int *ptr=a;
    for(int i=0;i<5;i++){
        if(*(ptr+i)<min){
            min=*(ptr+i);
        }
        if(*(ptr+i)>max){
            max=*(ptr+i);
        }
    }
    printf("MIN = %d  and  MAX = %d\n",min,max);
}
```

__OUTPUT :__

MIN = 1  and  MAX = 5.

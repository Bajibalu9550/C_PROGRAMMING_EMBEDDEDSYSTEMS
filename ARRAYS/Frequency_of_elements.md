# Print the frequency of each element of an array.

````
#include<stdio.h>
#include<stdlib.h>
int main(){
    int n;
    printf("Enter array size: ");
    scanf("%d",&n);
    int *arr=malloc(sizeof(int)*n);
    if(arr==NULL){
        printf("Memory allocation failed");
        exit(1);
    }
    printf("Enter array elements: ");
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    int freq[100]={0};
    for(int i=0;i<n;i++){
        freq[arr[i]]++;
    }
    for(int i=0;i<n;i++){
        if(freq[arr[i]]>=1){ 
            printf("The element \"%d\" frequecy is = %d\n",arr[i],freq[arr[i]]);
            freq[arr[i]]=0;
        }
    }
}
````

__OUTPUT :__

Enter array size: 5

Enter array elements: 1 2 4 5 1

The element \"1\" frequecy is = 2

The element \"2\" frequecy is = 1

The element \"4\" frequecy is = 1

The element \"5\" frequecy is = 1


# Count the duplicates in array 

`````
#include<stdio.h>
void count_dup(int *a,int n){
    int freq[n];
    for(int i=0;i<n;i++){
        freq[i]=0;
    }
    int count=0;
    
    for(int i=0;i<n;i++){
        if(freq[i])
            continue;
        int dup=0;
        for(int j=i+1;j<n;j++){
            if(a[i]==a[j]){
                freq[j]=1;
                dup=1;
               
            }
        }
        if(dup)
            count++;
    }
    printf("Count of Duplicate elements: %d",count);

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
  count_dup(a,n);
}
  
`````

__OUTPUT :__

Enter array size: 8

Enter array elements: 1 2 2 1 4 3 1 2

Count of Duplicate elements: 2  (i.e, 1,2)

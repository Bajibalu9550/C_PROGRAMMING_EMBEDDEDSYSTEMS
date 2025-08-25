# Merge two arrays of the same size sorted in descending order

````
 #include<stdio.h>
void merge(int *a,int *b,int n){
    int result[2*n];
     int i=0,j=0,k=0;
     while(i<n&&j<n){
        if(a[i]>b[j])
            result[k++]=a[i++];
        else 
            result[k++]=b[j++];
     }
     while(i<n){
        result[k++]=a[i++];
     }
     while(j<n){
        result[k++]=b[j++];
     }

     
     printf("Merged array: ");
     for(int i=0;i<k;i++){
        printf("%d ",result[i]);
     }
}
int main(){
    int n;
    printf("Enter array size: ");
    scanf("%d",&n);
    int a[n],b[n];
    printf("Enter array one elements in descending order: ");
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    printf("Enter array second elements in descending order: ");
    for(int i=0;i<n;i++){
        scanf("%d",&b[i]);
    }

    merge(a,b,n);
}
````

__OUTPUT :__
Enter array size: 5

Enter array one elements in descending order: 10 9 5 3 2

Enter array second elements in descending order: 8 7 6 4 1

Merged array: 10 9 8 7 6 5 4 3 2 1

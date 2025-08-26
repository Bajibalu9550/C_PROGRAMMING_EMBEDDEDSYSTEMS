#  Write a program to find the factorial of a given number using pointers.

```
#include<stdio.h>
int fact(int n){
    int f=1;
    if(n==1){
        return 1;
    }
    return n*fact(n-1);
}
int main(){
    int n;
    printf("Enter Number: ");
    scanf("%d",&n);
    int *ptr=&n;
    int result=fact(*ptr);
    printf("Factorial of given number %d is: %d",n,result);
}
```

__OUTPUT :__

Enter Number: 5

Factorial of given number 5 is: 120

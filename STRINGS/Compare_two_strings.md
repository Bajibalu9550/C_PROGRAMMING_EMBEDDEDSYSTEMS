# Write a program in C to compare two strings without using string library functions.
---

```
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
void compare(char *str1,char *str2){
    while(*str1!='\0'&&*str2!='\0'){
        if(*str1==*str2){
            str1++;
            str2++;
        }
        else if(*str1>*str2){
            printf("String 1 is big and String 2 is small.\n");
            return;
        }
        else {
            printf("String 1 is small and String 2 is big.\n");
            return;
        }
    }
    printf("Both strings are equal\n");
}
int main(){
    char *str1=malloc(100);
    char *str2=malloc(100);
    if(str1==NULL || str2==NULL){
        printf("Memory allocation failed");
        exit(1);
    }
    printf("Enter first string: ");
    fgets(str1,100,stdin);
    str1[strlen(str1)-1]='\0';
    printf("Enter second string: ");
    fgets(str2,100,stdin);
    str2[strlen(str2)-1]='\0';

    compare(str1,str2);
}
```

__OUTPUT :__

Enter first string: apple

Enter second string: banana

String 1 is small and String 2 is big.



Enter first string: mango

Enter second string: mango

Both strings are equal



Enter first string: zebra

Enter second string: ant

String 1 is big and String 2 is small.

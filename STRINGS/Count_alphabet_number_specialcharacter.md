# Write a program in C to count the total number of alphabets, digits and special characters in a string.
-----

````
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
void count(char *str){
    int a=0,d=0,s=0;
    while(*str!='\0'){
        if(isalpha(*str)){
            a++;
            str++;
        }
        else if(isdigit(*str)){
            d++;
            str++;
        }
        else {
            s++;
            str++;
        }
    }
    printf("Alphabets count: %d, Digits count: %d and Special character count: %d\n",a,d,s);
}
int main(){
    char *str=malloc(100);
    if(str==NULL){
        printf("Memory allocation failed");
        exit(1);
    }
    printf("Enter string: ");
    fgets(str,100,stdin);
    str[strlen(str)-1]='\0';

    count(str);
}
````

__OUTPUT :__

Enter string: baji balu 123

Alphabets count: 8, Digits count: 3 and Special character count: 2

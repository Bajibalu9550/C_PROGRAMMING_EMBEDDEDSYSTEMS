# Develop a function to reverse a string in place using pointers.

```
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
void reverse(char *str,int start,int end){
    while(start<end){
        char temp=*(str+start);
        *(str+start)=*(str+end);
        *(str+end)=temp;
        start++;
        end--;
    }
}
int main(){
    char *str=malloc(100);
    if(str==NULL){
        printf("ERROR");
        exit(1);    
    }
    printf("Enter string: ");
    fgets(str,100,stdin);
    str[strlen(str)-1]='\0';
    reverse(str,0,strlen(str)-1);

    printf("Reversed string: %s",str);
}
```

__OUTPUT :__

Enter string: Balu

Reversed String: ualB

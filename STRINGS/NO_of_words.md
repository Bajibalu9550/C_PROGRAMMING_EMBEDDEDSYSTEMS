# Write a program in C to count the total number of words in a string.

```
#include<string.h>
#include<stdlib.h>
#include<Stdio.h>
#include<ctype.h>
int remove_Spaces(char *str){
    int count=0;
    while(*str){
        if(*str==' '){
           count++;
        }
        str++;
    }
   
    return count+1;

}
int main(){
    char *str=malloc(sizeof(char)*100);
    if(str==NULL){
        printf("Memory allocation failed");
        exit(1);
    }
    printf("Enter string: ");
    fgets(str,100,stdin);
    str[strlen(str)-1]='\0';
    
    printf("No of words in give string is: %d",remove_Spaces(str));
    
    free(str);
}
```

__OUTPUT :__

Enter string: baji balu pagolu

No of words in given string is: 3

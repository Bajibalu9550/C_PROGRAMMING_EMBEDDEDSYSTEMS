#  Write a program to count the number of vowels and consonants in a string using a pointer.

```
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#include<ctype.h>
int isVowel(char ch){
    ch=tolower(ch);
    return (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u');
}
void Count(char *str){
    int i=0,j=strlen(str);
    int vc=0,cc=0;
    while(i<j){
        if(isVowel(*(str+i))){
            vc++;
        }
        else {
            cc++;
        }
        i++;
    }
    printf("Vowels count= %d  and consonants count: %d",vc,cc);
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
    Count(str);
}
```

__OUTPUT :__

Enter string: bajibalu

Vowels count: 4 and consonants count: 4

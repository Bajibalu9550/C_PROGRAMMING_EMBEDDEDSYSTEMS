# C Program to Reverse the Order of Words in a String

This program reverses the **word order** in a given input string using a two-step approach:

1. **Reverse the entire string.**
2. **Reverse each word in place.**

---

## Code

```c
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

void reverse_words(char *str,int start,int end){
    int w_start,w_end;
    for(w_start=w_end=start;w_end<end;w_end++){
        if(str[w_end]==' ')
            continue;
        w_start=w_end;
        while(str[w_end]!=' '&&str[w_end]!='\0')
            w_end++;
        w_end--;
        reverse(str,w_start,w_end);
    }
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
    reverse(str,0,strlen(str)-1);
    reverse_words(str,0,strlen(str));
    printf("Reversed string: %s\n",str);
    free(str);
}

Input

Enter string Which contains words: Hello World from C

 Output:

C from World Hello

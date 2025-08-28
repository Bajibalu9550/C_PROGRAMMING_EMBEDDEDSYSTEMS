# C Program to Reverse Vowels in a String

```c
#include<stdio.h>
#include<string.h>
#include<stdlib.h>

int isvowel(char ch){
    ch = tolower(ch);
    return (ch=='a' || ch=='e' || ch=='i' || ch=='o' || ch=='u');
}

void Reverse_vowels(char *str){
    int len = strlen(str);
    int start = 0;
    while(start < len){ 
        if(!isvowel(str[start])){
            start++;
        }
        else if(!isvowel(str[len])){
            len--;
        }
        else {
            char temp = str[start];
            str[start] = str[len];
            str[len] = temp;
            start++;
            len--;
        }
    }
    printf("Updated string: %s\n", str);
}

int main(){
    char *str = malloc(100);
    if(str == NULL){
        printf("Memory allocation failed");
        exit(1);
    }
    printf("Enter string: ");
    fgets(str, 100, stdin);
    str[strlen(str)-1] = '\0';
    Reverse_vowels(str);
}


Enter string: hello world

Updated string: hollo werld


# C Program to Split Strings by Space into Words

## Problem Explanation
The task is to read a string and **split it into words** using spaces as delimiters.  
For example:  

Input: "I love programming in C"


Output:

I

love

programming

in

C

---

## C Program

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[200];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0';  

    char *token = strtok(str, " ");
    while (token != NULL) {
        printf("%s\n", token);
        token = strtok(NULL, " ");
    }

    return 0;
}

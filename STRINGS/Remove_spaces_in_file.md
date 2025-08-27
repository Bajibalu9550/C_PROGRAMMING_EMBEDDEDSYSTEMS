# C Program to Read a File and Remove Spaces Between Words

## Problem Explanation
The task is to read the contents of a file and **remove all spaces** from it.  


---

## C Program

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    char filename[100];
    printf("Enter the filename: ");
    scanf("%s", filename);

    FILE *fp = fopen(filename, "r");
    if (fp == NULL) {
        printf("Cannot open file %s\n", filename);
        return 1;
    }

    fseek(fp, 0, SEEK_END);
    long filesize = ftell(fp);
    fseek(fp, 0, SEEK_SET);

    char *content = malloc(filesize + 1);
    if (content == NULL) {
        printf("Memory allocation failed\n");
        fclose(fp);
        return 1;
    }

    fread(content, 1, filesize, fp);
    content[filesize] = '\0';
    fclose(fp);

    char *result = malloc(filesize + 1);
    if (result == NULL) {
        printf("Memory allocation failed\n");
        free(content);
        return 1;
    }

    int j = 0;
    for (int i = 0; content[i] != '\0'; i++) {
        if (content[i] != ' ')
            result[j++] = content[i];
    }
    result[j] = '\0';

    printf("Content after removing spaces:\n%s\n", result);

    free(content);
    free(result);

    return 0;
}
OUTPUT :
Enter the filename: sample.txt
Content after removing spaces:
Cisapowerfullanguage
Iloveprogramming



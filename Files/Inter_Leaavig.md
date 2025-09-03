# C Program to Interleave Two Files

This program reads two input files and writes their contents alternately into a third file.

## 1st Method
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *fp1, *fp2, *fp3;
    char ch1, ch2;

    fp1 = fopen("file1.txt", "r");
    fp2 = fopen("file2.txt", "r");
    fp3 = fopen("output.txt", "w");

    if (fp1 == NULL || fp2 == NULL || fp3 == NULL) {
        printf("Error opening file(s).\n");
        return 1;
    }

   
    while (1) {
        ch1 = fgetc(fp1);
        ch2 = fgetc(fp2);

        if (ch1 == EOF && ch2 == EOF)
            break;

        if (ch1 != EOF)
            fputc(ch1, fp3);
        if (ch2 != EOF)
            fputc(ch2, fp3);
    }

    fclose(fp1);
    fclose(fp2);
    fclose(fp3);

    printf("Files interleaved successfully into output.txt\n");
    return 0;
}

```
## 2nd Method
# C Program to Interleave Two Files Word by Word Using fscanf()

This program reads two input files word by word and writes their contents alternately into a third file.

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *fp1, *fp2, *fp3;
    char word1[100], word2[100];

    fp1 = fopen("file1.txt", "r");
    fp2 = fopen("file2.txt", "r");
    fp3 = fopen("output.txt", "w");

    if (fp1 == NULL || fp2 == NULL || fp3 == NULL) {
        printf("Error opening file(s).\n");
        return 1;
    }

    
    while (1) {
        int read1 = fscanf(fp1, "%s", word1);
        int read2 = fscanf(fp2, "%s", word2);

        if (read1 == EOF && read2 == EOF)
            break;

        if (read1 != EOF)
            fprintf(fp3, "%s ", word1);
        if (read2 != EOF)
            fprintf(fp3, "%s ", word2);
    }

    fclose(fp1);
    fclose(fp2);
    fclose(fp3);

    printf("Files interleaved successfully into output.txt\n");
    return 0;
}
```



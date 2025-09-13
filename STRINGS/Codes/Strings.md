1. Input a string and print it
```
#include <stdio.h>
int main() {
    char str[100];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);  // safer than gets
    printf("You entered: %s", str);
    return 0;
}
```
2. Find the length of a string without library functions
```
#include <stdio.h>
int main() {
    char str[100];
    int length = 0;
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    while (str[length] != '\0' && str[length] != '\n') {
        length++;
    }
    printf("Length: %d\n", length);
    return 0;
}
```
3. Separate individual characters from a string
```
#include <stdio.h>
int main() {
    char str[100];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    for (int i = 0; str[i] != '\0' && str[i] != '\n'; i++) {
        printf("%c\n", str[i]);
    }
    return 0;
}
```
4. Print individual characters in reverse order
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    int len = 0;
    while (str[len] != '\0' && str[len] != '\n') len++;
    for (int i = len - 1; i >= 0; i--) {
        printf("%c\n", str[i]);
    }
    return 0;
}
```
5. Count total number of words in a string
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[200];
    int words = 0;
    int inWord = 0;
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    for (int i = 0; str[i] != '\0'; i++) {
        if (isspace(str[i])) {
            inWord = 0;
        } else if (!inWord) {
            inWord = 1;
            words++;
        }
    }
    printf("Total words: %d\n", words);
    return 0;
}
```
6. Compare two strings without library functions
```
#include <stdio.h>
int main() {
    char str1[100], str2[100];
    int i = 0, flag = 0;
    printf("Enter first string: "); fgets(str1, sizeof(str1), stdin);
    printf("Enter second string: "); fgets(str2, sizeof(str2), stdin);

    while (str1[i] != '\0' && str2[i] != '\0') {
        if (str1[i] != str2[i]) {
            flag = 1;
            break;
        }
        i++;
    }
    if (str1[i] != str2[i]) flag = 1;

    if (flag) printf("Strings are not equal\n");
    else printf("Strings are equal\n");
    return 0;
}
```
7. Count alphabets, digits, and special characters
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    int alphabets = 0, digits = 0, special = 0;
    printf("Enter a string: "); fgets(str, sizeof(str), stdin);
    for (int i = 0; str[i] != '\0' && str[i] != '\n'; i++) {
        if (isalpha(str[i])) alphabets++;
        else if (isdigit(str[i])) digits++;
        else special++;
    }
    printf("Alphabets=%d, Digits=%d, Special=%d\n", alphabets, digits, special);
    return 0;
}
```
8. Copy one string to another
```
#include <stdio.h>
int main() {
    char str1[100], str2[100];
    printf("Enter a string: "); fgets(str1, sizeof(str1), stdin);
    int i = 0;
    while (str1[i] != '\0') {
        str2[i] = str1[i];
        i++;
    }
    str2[i] = '\0';
    printf("Copied string: %s", str2);
    return 0;
}
```
9. Count vowels and consonants
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    int vowels = 0, consonants = 0;
    printf("Enter a string: "); fgets(str, sizeof(str), stdin);
    for (int i = 0; str[i] != '\0' && str[i] != '\n'; i++) {
        char ch = tolower(str[i]);
        if (isalpha(ch)) {
            if (ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u') vowels++;
            else consonants++;
        }
    }
    printf("Vowels=%d, Consonants=%d\n", vowels, consonants);
    return 0;
}
```
10. Find maximum number of characters (length) in string
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    printf("Enter a string: "); fgets(str, sizeof(str), stdin);
    int len = 0;
    while (str[len] != '\0' && str[len] != '\n') len++;
    printf("Maximum number of characters: %d\n", len);
    return 0;
}
```
11. Sort a string array ascending and descending
```
#include <stdio.h>
#include <string.h>
int main() {
    char arr[3][100] = {"apple","orange","banana"};
    char temp[100];

   
    for (int i=0;i<3-1;i++)
        for (int j=i+1;j<3;j++)
            if (strcmp(arr[i],arr[j])>0){
                strcpy(temp,arr[i]);
                strcpy(arr[i],arr[j]);
                strcpy(arr[j],temp);
            }
    printf("Ascending: ");
    for(int i=0;i<3;i++) printf("%s ",arr[i]);
    

    for (int i=0;i<3-1;i++)
        for (int j=i+1;j<3;j++)
            if (strcmp(arr[i],arr[j])<0){
                strcpy(temp,arr[i]);
                strcpy(arr[i],arr[j]);
                strcpy(arr[j],temp);
            }
    printf("\nDescending: ");
    for(int i=0;i<3;i++) printf("%s ",arr[i]);
    
    return 0;
}
```
12. Sort characters in string using bubble sort
```
#include <stdio.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    int len=0;
    while (str[len]!='\0' && str[len]!='\n') len++;

    for(int i=0;i<len-1;i++)
        for(int j=0;j<len-i-1;j++)
            if(str[j]>str[j+1]){
                char t=str[j]; str[j]=str[j+1]; str[j+1]=t;
            }

    printf("Sorted string: %s\n", str);
    return 0;
}
```
13. Extract substring
```
#include <stdio.h>
int main() {
    char str[100], sub[100];
    int start, length;
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    printf("Enter start index and length: ");
    scanf("%d %d",&start,&length);
    for(int i=0;i<length;i++) sub[i]=str[start+i];
    sub[length]='\0';
    printf("Substring: %s\n", sub);
    return 0;
}
```
14. Check if substring is present
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], sub[100];
    printf("Enter main string: "); fgets(str, sizeof(str), stdin);
    printf("Enter substring: "); fgets(sub, sizeof(sub), stdin);
    if(strstr(str, sub) != NULL) printf("Substring found\n");
    else printf("Substring not found\n");
    return 0;
}
```
15. Replace lowercase with uppercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter sentence: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++) str[i] = toupper(str[i]);
    printf("Uppercase: %s", str);
    return 0;
}
```
16. Count occurrences of the word "the"
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    int count=0;
    char *ptr=str;
    while((ptr=strstr(ptr,"the"))!=NULL){
        count++;
        ptr+=3;
    }
    printf("Occurrences of 'the': %d\n", count);
    return 0;
}
```
17. Remove characters except alphabets
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100], result[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    int j=0;
    for(int i=0; str[i]!='\0'; i++)
        if(isalpha(str[i])) result[j++]=str[i];
    result[j]='\0';
    printf("Alphabets only: %s\n", result);
    return 0;
}
```
18. Frequency of characters
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    int freq[256] = {0};
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++) freq[(unsigned char)str[i]]++;
    for(int i=0;i<256;i++)
        if(freq[i]>0) printf("%c=%d\n", i, freq[i]);
    return 0;
}
```
19. Combine two strings manually
```
#include <stdio.h>
int main() {
    char str1[100], str2[100], result[200];
    int i=0, j=0;
    printf("Enter first string: "); fgets(str1, sizeof(str1), stdin);
    printf("Enter second string: "); fgets(str2, sizeof(str2), stdin);

    while(str1[i] != '\0' && str1[i] != '\n') { result[j++] = str1[i++]; }
    i=0;
    while(str2[i] != '\0' && str2[i] != '\n') { result[j++] = str2[i++]; }
    result[j] = '\0';
    printf("Combined string: %s\n", result);
    return 0;
}
```
20. Find largest and smallest words in a string
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main() {
    char str[200];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);

    int maxLen=0, minLen=100, len=0, start=0;
    char maxWord[100], minWord[100], word[100];

    for(int i=0; ; i++) {
        if(str[i]==' ' || str[i]=='\0' || str[i]=='\n') {
            if(len>0) {
                word[len]='\0';
                if(len>maxLen){ maxLen=len; strcpy(maxWord, word);}
                if(len<minLen){ minLen=len; strcpy(minWord, word);}
            }
            len=0;
            if(str[i]=='\0'||str[i]=='\n') break;
        } else word[len++]=str[i];
    }
    printf("Largest: %s\nSmallest: %s\n", maxWord, minWord);
    return 0;
}
```
21. Convert a string to uppercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++) str[i]=toupper(str[i]);
    printf("Uppercase: %s\n", str);
    return 0;
}
```
22. Convert a string to lowercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++) str[i]=tolower(str[i]);
    printf("Lowercase: %s\n", str);
    return 0;
}
```
23. Check if character is hexadecimal digit
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char ch;
    printf("Enter a character: "); scanf("%c",&ch);
    if(isxdigit(ch)) printf("Hexadecimal digit\n");
    else printf("Not a hexadecimal digit\n");
    return 0;
}
```
24. Check if letter is uppercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char ch;
    printf("Enter a letter: "); scanf("%c",&ch);
    if(isupper(ch)) printf("Uppercase\n");
    else printf("Not uppercase\n");
    return 0;
}
```
25. Replace spaces with specific character
```
#include <stdio.h>
int main() {
    char str[100];
    char ch;
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    printf("Enter replacement character: "); scanf(" %c", &ch);
    for(int i=0; str[i]!='\0'; i++) if(str[i]==' ') str[i]=ch;
    printf("Modified string: %s\n", str);
    return 0;
}
```
26. Count punctuation characters
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[200];
    int count=0;
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++)
        if(ispunct(str[i])) count++;
    printf("Punctuation count: %d\n", count);
    return 0;
}
```
27. Print string before newline
```
#include <stdio.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0' && str[i]!='\n'; i++) printf("%c", str[i]);
    printf("\n");
    return 0;
}
```
28. Check if letter is lowercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char ch;
    printf("Enter a letter: "); scanf("%c",&ch);
    if(islower(ch)) printf("Lowercase\n");
    else printf("Not lowercase\n");
    return 0;
}
```
29. Remove spaces between words from file
```
#include <stdio.h>
int main() {
    FILE *fp = fopen("input.txt","r");
    char ch;
    if(fp==NULL){ printf("File not found\n"); return 1;}
    while((ch=fgetc(fp))!=EOF) if(ch!=' ') putchar(ch);
    fclose(fp);
    return 0;
}
```
30. Check if character is a digit
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char ch;
    printf("Enter character: "); scanf("%c",&ch);
    if(isdigit(ch)) printf("Digit\n");
    else printf("Not a digit\n");
    return 0;
}
```
31. Split string by space into words
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    char *word = strtok(str, " \n");
    while(word!=NULL) {
        printf("%s\n", word);
        word = strtok(NULL, " \n");
    }
    return 0;
}
```
32. Find repeated character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    int freq[256] = {0};
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0' && str[i]!='\n'; i++) freq[(unsigned char)str[i]]++;
    for(int i=0;i<256;i++) if(freq[i]>1) printf("%c is repeated %d times\n", i, freq[i]);
    return 0;
}
```
33. Count each character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    int freq[256] = {0};
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0' && str[i]!='\n'; i++) freq[(unsigned char)str[i]]++;
    for(int i=0;i<256;i++) if(freq[i]>0) printf("%c=%d\n", i, freq[i]);
    return 0;
}
```
34. Convert vowels to uppercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0' && str[i]!='\n'; i++)
        if(str[i]=='a'||str[i]=='e'||str[i]=='i'||str[i]=='o'||str[i]=='u')
            str[i]=toupper(str[i]);
    printf("Modified string: %s\n", str);
    return 0;
}
```
35. Length of longest substring without repeating characters
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    int maxLen=0, start=0;
    int seen[256];
    for(int i=0;i<256;i++) seen[i]=-1;

    int i=0,j=0;
    while(str[i]!='\0' && str[i]!='\n') {
        if(seen[(unsigned char)str[i]]>=j) j = seen[(unsigned char)str[i]]+1;
        seen[(unsigned char)str[i]] = i;
        if(i-j+1>maxLen) maxLen=i-j+1;
        i++;
    }
    printf("Length of longest substring: %d\n", maxLen);
    return 0;
}
```
36. Check if brackets in string are valid
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    char stack[100];
    int top=-1;
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    int valid=1;
    for(int i=0; str[i]!='\0' && str[i]!='\n'; i++) {
        char c=str[i];
        if(c=='('||c=='{'||c=='['||c=='<' ) stack[++top]=c;
        else if(c==')'||c=='}'||c==']'||c=='>') {
            if(top<0){ valid=0; break;}
            char open = stack[top--];
            if((c==')'&&open!='(')||(c=='}'&&open!='{')||(c==']'&&open!='[')||(c=='>'&&open!='<')) {
                valid=0; break;
            }
        }
    }
    if(top>=0) valid=0;
    if(valid) printf("Valid brackets\n");
    else printf("Invalid brackets\n");
    return 0;
}
```
37. Multiply two positive numbers as strings
```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

void multiply(char num1[], char num2[], char result[]) {
    int len1 = strlen(num1), len2 = strlen(num2);
    int *res = calloc(len1+len2, sizeof(int));

    for(int i=len1-1;i>=0;i--) {
        for(int j=len2-1;j>=0;j--) {
            int mul = (num1[i]-'0')*(num2[j]-'0');
            int sum = mul + res[i+j+1];
            res[i+j+1] = sum%10;
            res[i+j] += sum/10;
        }
    }

    int k=0, i=0;
    while(i<len1+len2 && res[i]==0) i++;
    if(i==len1+len2) { result[k++]='0'; }
    else { for(;i<len1+len2;i++) result[k++]=res[i]+'0'; }
    result[k]='\0';
    free(res);
}

int main() {
    char num1[100], num2[100], prod[200];
    printf("Enter two numbers: "); scanf("%s %s", num1, num2);
    multiply(num1, num2, prod);
    printf("Product: %s\n", prod);
    return 0;
}
```
38. Reverse all vowels in a string
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int isVowel(char ch){ ch=tolower(ch); return ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u'; }

void reverseVowels(char str[]) {
    int i=0, j=strlen(str)-1;
    while(i<j){
        if(!isVowel(str[i])) { i++; continue; }
        if(!isVowel(str[j])) { j--; continue; }
        char temp=str[i]; str[i]=str[j]; str[j]=temp;
        i++; j--;
    }
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    reverseVowels(str);
    printf("Result: %s\n", str);
    return 0;
}
```
39. Longest palindromic substring
```
#include <stdio.h>
#include <string.h>

int expand(char s[], int left, int right) {
    while(left>=0 && right<strlen(s) && s[left]==s[right]) { left--; right++; }
    return right-left-1;
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    str[strcspn(str,"\n")]='\0';

    int start=0, maxLen=0;
    for(int i=0; i<strlen(str); i++){
        int len1=expand(str,i,i);
        int len2=expand(str,i,i+1);
        int len=len1>len2?len1:len2;
        if(len>maxLen){ maxLen=len; start=i-(len-1)/2; }
    }
    for(int i=start;i<start+maxLen;i++) printf("%c", str[i]);
    printf("\n");
    return 0;
}
```
40. Replace lowercase with uppercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++) if(islower(str[i])) str[i]=toupper(str[i]);
    printf("Uppercase: %s\n", str);
    return 0;
}
```
41. Length of longest common subsequence (LCS)
```
#include <stdio.h>
#include <string.h>

int max(int a,int b){ return a>b?a:b; }

int main() {
    char X[100], Y[100];
    printf("Enter two strings: "); scanf("%s %s", X, Y);
    int m=strlen(X), n=strlen(Y);
    int L[m+1][n+1];
    for(int i=0;i<=m;i++){
        for(int j=0;j<=n;j++){
            if(i==0 || j==0) L[i][j]=0;
            else if(X[i-1]==Y[j-1]) L[i][j]=L[i-1][j-1]+1;
            else L[i][j]=max(L[i-1][j],L[i][j-1]);
        }
    }
    printf("Length of LCS: %d\n", L[m][n]);
    return 0;
}
```
42. Find length of a string
```
#include <stdio.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    int len=0;
    while(str[len]!='\0' && str[len]!='\n') len++;
    printf("Length: %d\n", len);
    return 0;
}
```
43. Copy one string to another
```
#include <stdio.h>
int main() {
    char src[100], dest[100];
    printf("Enter string: "); fgets(src, sizeof(src), stdin);
    int i=0;
    while(src[i]!='\0') { dest[i]=src[i]; i++; }
    dest[i]='\0';
    printf("Copied string: %s\n", dest);
    return 0;
}
```
44. Concatenate two strings
```
#include <stdio.h>
int main() {
    char str1[100], str2[100], result[200];
    printf("Enter first string: "); fgets(str1, sizeof(str1), stdin);
    printf("Enter second string: "); fgets(str2, sizeof(str2), stdin);
    int i=0,j=0;
    while(str1[i]!='\0' && str1[i]!='\n') result[j++]=str1[i++];
    i=0;
    while(str2[i]!='\0' && str2[i]!='\n') result[j++]=str2[i++];
    result[j]='\0';
    printf("Concatenated string: %s\n", result);
    return 0;
}
```
45. Compare two strings
```
#include <stdio.h>
int main() {
    char str1[100], str2[100];
    printf("Enter two strings: "); fgets(str1,sizeof(str1),stdin); fgets(str2,sizeof(str2),stdin);
    int i=0, cmp=0;
    while(str1[i]!='\0' && str2[i]!='\0' && str1[i]==str2[i]) i++;
    if(str1[i]==str2[i]) cmp=0;
    else cmp=(str1[i]-str2[i]);
    if(cmp==0) printf("Equal\n");
    else if(cmp>0) printf("str1 > str2\n");
    else printf("str1 < str2\n");
    return 0;
}

```

47. Uppercase → Lowercase
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++) if(isupper(str[i])) str[i]=tolower(str[i]);
    printf("Lowercase: %s\n", str);
    return 0;
}
```
48. Toggle case
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    for(int i=0; str[i]!='\0'; i++) {
        if(islower(str[i])) str[i]=toupper(str[i]);
        else if(isupper(str[i])) str[i]=tolower(str[i]);
    }
    printf("Toggled: %s\n", str);
    return 0;
}
```
49. Count alphabets, digits, special chars
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100]; int alph=0,digit=0,special=0;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    for(int i=0; str[i]!='\0'; i++){
        if(isalpha(str[i])) alph++;
        else if(isdigit(str[i])) digit++;
        else if(!isspace(str[i])) special++;
    }
    printf("Alphabets=%d, Digits=%d, Special=%d\n", alph,digit,special);
    return 0;
}
```
50. Count vowels and consonants
```
#include <stdio.h>
#include <ctype.h>
int main() {
    char str[100]; int vowels=0, consonants=0;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    for(int i=0; str[i]!='\0'; i++){
        char ch=tolower(str[i]);
        if(isalpha(ch)){
            if(ch=='a'||ch=='e'||ch=='i'||ch=='o'||ch=='u') vowels++;
            else consonants++;
        }
    }
    printf("Vowels=%d, Consonants=%d\n", vowels, consonants);
    return 0;
}
```
51. Count words in a string
```
#include <stdio.h>
int main() {
    char str[200]; int words=0;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    for(int i=0; str[i]!='\0'; i++)
        if(str[i]==' ' || str[i]=='\n') words++;
    printf("Words=%d\n", words+1); 
    return 0;
}
```
52. Reverse a string
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    int len=strcspn(str,"\n");
    for(int i=len-1;i>=0;i--) printf("%c", str[i]);
    printf("\n");
    return 0;
}
```
53. Check palindrome
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>
int main() {
    char str[100]; int flag=1;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    int len=strcspn(str,"\n");
    for(int i=0;i<len/2;i++)
        if(str[i]!=str[len-i-1]) { flag=0; break; }
    if(flag) printf("Palindrome\n"); else printf("Not Palindrome\n");
    return 0;
}
```
54. Reverse order of words in a string
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[200], temp[200];
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    str[strcspn(str,"\n")]='\0';
    int len=strlen(str), k=0;

    for(int i=len-1;i>=0;i--) {
        if(str[i]==' ' || i==0) {
            int start = (i==0)?0:i+1;
            for(int j=start; j<=len && str[j]!=' '; j++) temp[k++] = str[j];
            temp[k++]=' ';
        }
    }
    temp[k-1]='\0';
    printf("Reversed words: %s\n", temp);
    return 0;
}
```
55. First occurrence of a character
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], ch;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf("%c", &ch);

    char *ptr = strchr(str,ch);
    if(ptr) printf("First occurrence at index: %ld\n", ptr-str);
    else printf("Character not found\n");
    return 0;
}
```
56. Last occurrence of a character
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], ch;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf("%c",&ch);

    char *ptr = strrchr(str,ch);
    if(ptr) printf("Last occurrence at index: %ld\n", ptr-str);
    else printf("Character not found\n");
    return 0;
}
```
57. Search all occurrences of a character
```
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], ch;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf("%c",&ch);

    printf("Occurrences at indexes: ");
    for(int i=0; str[i]!='\0'; i++)
        if(str[i]==ch) printf("%d ", i);
    printf("\n");
    return 0;
}
```
58. Count occurrences of a character
```
#include <stdio.h>
int main() {
    char str[100], ch; int count=0;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf("%c",&ch);

    for(int i=0; str[i]!='\0'; i++)
        if(str[i]==ch) count++;
    printf("Occurrences: %d\n", count);
    return 0;
}
```
59. Highest frequency character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100]; int freq[256]={0};
    printf("Enter string: "); fgets(str,sizeof(str),stdin);

    for(int i=0; str[i]!='\0'; i++) freq[(unsigned char)str[i]]++;
    int max=0; char ch;
    for(int i=0;i<256;i++)
        if(freq[i]>max){ max=freq[i]; ch=i; }
    printf("Highest frequency character: %c (%d times)\n", ch, max);
    return 0;
}
```
60. Lowest frequency character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100]; int freq[256]={0};
    printf("Enter string: "); fgets(str,sizeof(str),stdin);

    for(int i=0; str[i]!='\0'; i++) freq[(unsigned char)str[i]]++;
    int min=1000; char ch;
    for(int i=0;i<256;i++)
        if(freq[i]>0 && freq[i]<min){ min=freq[i]; ch=i; }
    printf("Lowest frequency character: %c (%d times)\n", ch, min);
    return 0;
}
```
61. Frequency of each character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100]; int freq[256]={0};
    printf("Enter string: "); fgets(str,sizeof(str),stdin);

    for(int i=0; str[i]!='\0'; i++) freq[(unsigned char)str[i]]++;
    for(int i=0;i<256;i++)
        if(freq[i]>0) printf("%c: %d\n", i, freq[i]);
    return 0;
}
```
62. Remove first occurrence of a character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], ch;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf("%c",&ch);

    char *ptr = strchr(str,ch);
    if(ptr) memmove(ptr, ptr+1, strlen(ptr));
    printf("Result: %s\n", str);
    return 0;
}
```

63. Remove last occurrence of a character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], ch;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf("%c",&ch);

    char *ptr = strrchr(str,ch);
    if(ptr) memmove(ptr, ptr+1, strlen(ptr));
    printf("Result: %s\n", str);
    return 0;
}
```
64. Remove all occurrences of a character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], ch;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf("%c",&ch);

    int k=0;
    for(int i=0; str[i]!='\0'; i++)
        if(str[i]!=ch) str[k++]=str[i];
    str[k]='\0';
    printf("Result: %s\n", str);
    return 0;
}
```
65. Remove all repeated characters
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100]; int freq[256]={0};
    printf("Enter string: "); fgets(str,sizeof(str),stdin);

    int k=0;
    for(int i=0; str[i]!='\0'; i++){
        if(freq[(unsigned char)str[i]]==0) str[k++]=str[i];
        freq[(unsigned char)str[i]]++;
    }
    str[k]='\0';
    printf("Result: %s\n", str);
    return 0;
}
```
66. Replace first occurrence of a character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], ch1, ch2;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter old and new char: "); scanf("%c %c",&ch1,&ch2);

    char *ptr = strchr(str,ch1);
    if(ptr) *ptr=ch2;
    printf("Result: %s\n", str);
    return 0;
}
```
67. Replace last occurrence of a character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], ch1, ch2;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter old and new char: "); scanf("%c %c",&ch1,&ch2);

    char *ptr = strrchr(str,ch1);
    if(ptr) *ptr=ch2;
    printf("Result: %s\n", str);
    return 0;
}
```
68. Replace all occurrences of a character
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[100], ch1, ch2;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter old and new char: "); scanf("%c %c",&ch1,&ch2);

    for(int i=0; str[i]!='\0'; i++)
        if(str[i]==ch1) str[i]=ch2;
    printf("Result: %s\n", str);
    return 0;
}
```
69. First occurrence of a word in a string
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200], word[50];
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    str[strcspn(str,"\n")]='\0';
    printf("Enter word to search: "); scanf("%s", word);

    char *ptr = strstr(str, word);
    if(ptr) printf("First occurrence at index: %ld\n", ptr-str);
    else printf("Word not found\n");
    return 0;
}
```
70. Last occurrence of a word in a string
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200], word[50], *ptr, *last=NULL;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    str[strcspn(str,"\n")]='\0';
    printf("Enter word to search: "); scanf("%s", word);

    ptr = str;
    while((ptr = strstr(ptr, word)) != NULL) {
        last = ptr;
        ptr++;  // move forward
    }

    if(last) printf("Last occurrence at index: %ld\n", last-str);
    else printf("Word not found\n");
    return 0;
}
```
71. Search all occurrences of a word
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200], word[50], *ptr;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    str[strcspn(str,"\n")]='\0';
    printf("Enter word: "); scanf("%s", word);

    ptr = str;
    printf("Occurrences at indexes: ");
    while((ptr = strstr(ptr, word)) != NULL) {
        printf("%ld ", ptr-str);
        ptr++;
    }
    printf("\n");
    return 0;
}
```
72. Count occurrences of a word
```
#include <stdio.h>
#include <string.h>
int main() {
    char str[200], word[50], *ptr;
    int count=0;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    str[strcspn(str,"\n")]='\0';
    printf("Enter word: "); scanf("%s", word);

    ptr = str;
    while((ptr = strstr(ptr, word)) != NULL) {
        count++;
        ptr++;
    }
    printf("Occurrences: %d\n", count);
    return 0;
}
```
73. Remove first occurrence of a word
```
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

void remove_first(char *str,char *word){
        int m=strlen(str);
        int n=strlen(word);

        for(int i=0;i<=m-n;i++){
                int found=1;
                int j;
                for( j=0;j<n;j++){
                        if(str[i+j]!=word[j])
                                break;
                }
                if(j==n){
                        for(int k=i;k<=m-n;k++){
                                str[k]=str[k+n];
                        }
                        break;
                }
        }
        printf("Updated string: %s\n",str);
}
int main(){
        char *str1=malloc(100);
        char *word=malloc(50);
        if(str1==NULL || word==NULL){
                printf("Memory allocatio failed.\n");
                exit(1);
        }

        printf("Enter string: ");
        fgets(str1,100,stdin);
        str1[strlen(str1)-1]='\0';

        printf("Enter word: ");
        fgets(word,50,stdin);
        word[strlen(word)-1]='\0';


        remove_first(str1,word);
}

```
74. Remove last occurrence of a word
```
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

void remove_first(char *str,char *word){
        int m=strlen(str);
        int n=strlen(word);
        int index;

        for(int i=0;i<=m-n;i++){
                int found=1;
                int j;
                for( j=0;j<n;j++){
                        if(str[i+j]!=word[j])
                                break;
                }
                if(j==n){
                        index=i;
                }
        }
        for(int k=index;k<=m-n;k++){
                str[k]=str[k+n];
        }
        printf("Updated string: %s\n",str);
}
int main(){
        char *str1=malloc(100);
        char *word=malloc(50);
        if(str1==NULL || word==NULL){
                printf("Memory allocatio failed.\n");
                exit(1);
        }

        printf("Enter string: ");
        fgets(str1,100,stdin);
        str1[strlen(str1)-1]='\0';

        printf("Enter word: ");
        fgets(word,50,stdin);
        word[strlen(word)-1]='\0';


        remove_first(str1,word);
}

```
75. Remove all occurrences of a word
```
#include<stdio.h>
#include<stdlib.h>
#include<string.h>

void remove_first(char *str,char *word){
        int m=strlen(str);
        int n=strlen(word);

        for(int i=0;i<=m-n;i++){
                int found=1;
                int j;
                for( j=0;j<n;j++){
                        if(str[i+j]!=word[j])
                                break;
                }
                if(j==n){
                        for(int k=i;k<=m-n;k++){
                                str[k]=str[k+n];
                        }
                        
                }
        }
        printf("Updated string: %s\n",str);
}
int main(){
        char *str1=malloc(100);
        char *word=malloc(50);
        if(str1==NULL || word==NULL){
                printf("Memory allocatio failed.\n");
                exit(1);
        }

        printf("Enter string: ");
        fgets(str1,100,stdin);
        str1[strlen(str1)-1]='\0';

        printf("Enter word: ");
        fgets(word,50,stdin);
        word[strlen(word)-1]='\0';


        remove_first(str1,word);
}

```
76. Trim leading white space
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void trim_leading(char *str) {
    int i = 0, j = 0;
    while(isspace(str[i])) i++;
    while(str[i]) str[j++] = str[i++];
    str[j] = '\0';
}

int main() {
    char str[100];
    printf("Enter string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str,"\n")] = 0;

    trim_leading(str);
    printf("Trimmed leading spaces: '%s'\n", str);
    return 0;
}
```
77. Trim trailing white space
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void trim_trailing(char *str) {
    int i = strlen(str) - 1;
    while(i >= 0 && isspace(str[i])) str[i--] = '\0';
}

int main() {
    char str[100];
    printf("Enter string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str,"\n")] = 0;

    trim_trailing(str);
    printf("Trimmed trailing spaces: '%s'\n", str);
    return 0;
}
```
78. Trim both leading and trailing
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void trim(char *str) {
    int i = 0, j = 0;
    while(isspace(str[i])) i++;
    int len = strlen(str);
    while(len > i && isspace(str[len-1])) len--;
    while(i < len) str[j++] = str[i++];
    str[j] = '\0';
}

int main() {
    char str[100];
    printf("Enter string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str,"\n")] = 0;

    trim(str);
    printf("Trimmed string: '%s'\n", str);
    return 0;
}
```
79. Remove all extra blank spaces
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void remove_extra_spaces(char *str) {
    int i=0, j=0;
    int space = 0;
    while(str[i]) {
        if(!isspace(str[i])) {
            str[j++] = str[i];
            space = 0;
        } else if(space == 0) {
            str[j++] = ' ';
            space = 1;
        }
        i++;
    }
    if(j>0 && str[j-1]==' ') j--;
    str[j]='\0';
}

int main() {
    char str[200];
    printf("Enter string: ");
    fgets(str,sizeof(str),stdin);
    str[strcspn(str,"\n")]=0;

    remove_extra_spaces(str);
    printf("Result: '%s'\n", str);
    return 0;
}
```
80. Convert string to uppercase
```
#include <stdio.h>
#include <ctype.h>

void to_uppercase(char *str) {
    while(*str) {
        *str = toupper(*str);
        str++;
    }
}

int main() {
    char str[100];
    printf("Enter string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str,"\n")] = 0;

    to_uppercase(str);
    printf("Uppercase: %s\n", str);
    return 0;
}
```
81. Case-insensitive string comparison
```
#include <stdio.h>
#include <ctype.h>

int strcmpi(const char *s1, const char *s2) {
    while(*s1 && *s2) {
        if(tolower(*s1) != tolower(*s2)) return tolower(*s1) - tolower(*s2);
        s1++; s2++;
    }
    return tolower(*s1) - tolower(*s2);
}

int main() {
    char str1[100], str2[100];
    printf("Enter first string: "); fgets(str1,sizeof(str1),stdin); str1[strcspn(str1,"\n")]=0;
    printf("Enter second string: "); fgets(str2,sizeof(str2),stdin); str2[strcspn(str2,"\n")]=0;

    int res = strcmpi(str1,str2);
    if(res==0) printf("Strings are equal\n");
    else printf("Strings are not equal\n");
    return 0;
}
```
82. Recursive string reverse using bitwise
```
#include <stdio.h>
#include <string.h>

void reverse(char *str, int start, int end) {
    if(start >= end) return;
    str[start] ^= str[end];
    str[end] ^= str[start];
    str[start] ^= str[end];
    reverse(str, start+1, end-1);
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    reverse(str, 0, strlen(str)-1);
    printf("Reversed string: %s\n", str);
    return 0;
}
```
83. Removing newline from fgets
```
fgets(str, sizeof(str), stdin);
str[strcspn(str, "\n")] = 0;
```
84. Remove leading and trailing blanks
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

void trim_blanks(char *str) {
    int start = 0, end = strlen(str)-1;
    while(isspace(str[start])) start++;
    while(end >= start && isspace(str[end])) end--;
    int j = 0;
    for(int i=start;i<=end;i++) str[j++] = str[i];
    str[j] = '\0';
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    trim_blanks(str);
    printf("Trimmed: '%s'\n", str);
    return 0;
}
```
85. Alphabetical ordering of characters
```
#include <stdio.h>
#include <string.h>

void sort_string(char *str) {
    int len = strlen(str);
    for(int i=0;i<len-1;i++)
        for(int j=i+1;j<len;j++)
            if(str[i] > str[j]) {
                char temp = str[i];
                str[i] = str[j];
                str[j] = temp;
            }
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    sort_string(str);
    printf("Sorted string: %s\n", str);
    return 0;
}
```
86. Abbreviate input text
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void abbreviate(char *str, char *abbr) {
    int j = 0, cap = 1;
    for(int i=0; str[i]; i++) {
        if(cap && isalpha(str[i])) { abbr[j++] = toupper(str[i]); cap=0; }
        if(isspace(str[i])) cap=1;
    }
    abbr[j]='\0';
}

int main() {
    char str[200], abbr[50];
    printf("Enter text: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    abbreviate(str, abbr);
    printf("Abbreviation: %s\n", abbr);
    return 0;
}
```
87. Extract a substring from a string
```
#include <stdio.h>
#include <string.h>

void substring(char *source, char *dest, int start, int n) {
    int i;
    for(i = 0; i < n && source[start + i] != '\0'; i++) {
        dest[i] = source[start + i];
    }
    dest[i] = '\0';
}

int main() {
    char str[100], sub[100];
    int start, len;
    printf("Enter string: "); fgets(str, sizeof(str), stdin);
    str[strcspn(str,"\n")] = 0;
    printf("Enter start index and length: "); scanf("%d %d", &start, &len);

    substring(str, sub, start, len);
    printf("Substring: %s\n", sub);
    return 0;
}
```
88. Replace adjacent multiple spaces with single space
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void remove_multiple_spaces(char *str) {
    int i=0, j=0, space=0;
    while(str[i]) {
        if(!isspace(str[i])) {
            str[j++] = str[i];
            space = 0;
        } else if(space == 0) {
            str[j++] = ' ';
            space = 1;
        }
        i++;
    }
    str[j] = '\0';
}

int main() {
    char str[200];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    remove_multiple_spaces(str);
    printf("Result: '%s'\n", str);
    return 0;
}
```
89. Pointer versions of strcpy, strncmp, strncat

```
Custom strcpy using pointers

void my_strcpy(char *dest, const char *src) {
    while((*dest++ = *src++));
}


Custom strncmp using pointers

int my_strncmp(const char *s1, const char *s2, int n) {
    while(n-- && *s1 && *s1==*s2) { s1++; s2++; }
    if(n<0) return 0;
    return *(unsigned char*)s1 - *(unsigned char*)s2;
}


Custom strncat using pointers

void my_strncat(char *dest, const char *src, int n) {
    while(*dest) dest++;
    while(n-- && (*dest++ = *src++));
    *dest = '\0';
}
```
90. strrstr() – Last occurrence of substring
```
#include <stdio.h>
#include <string.h>

char* strrstr(const char *haystack, const char *needle) {
    char *result = NULL;
    if(!*needle) return (char*)haystack;
    while(*haystack) {
        const char *h = haystack;
        const char *n = needle;
        while(*h && *n && *h == *n) { h++; n++; }
        if(!*n) result = (char*)haystack;
        haystack++;
    }
    return result;
}

int main() {
    char str[100], sub[50];
    printf("Enter main string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    printf("Enter substring: "); fgets(sub,sizeof(sub),stdin); sub[strcspn(sub,"\n")]=0;

    char *pos = strrstr(str, sub);
    if(pos) printf("Last occurrence at position: %ld\n", pos-str);
    else printf("Substring not found\n");
    return 0;
}
```
91. Find index of first and last occurrence of substring
```
#include <stdio.h>
#include <string.h>

int find_indexF(const char *str, const char *sub) {
    char *pos = strstr(str, sub);
    return pos ? (pos - str) : -1;
}

int find_indexL(const char *str, const char *sub) {
    char *pos = NULL;
    char *temp = (char*)str;
    while(1) {
        char *p = strstr(temp, sub);
        if(!p) break;
        pos = p;
        temp = p + 1;
    }
    return pos ? (pos - str) : -1;
}

int main() {
    char str[200], sub[50];
    printf("Enter main string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    printf("Enter substring: "); fgets(sub,sizeof(sub),stdin); sub[strcspn(sub,"\n")]=0;

    printf("First occurrence index: %d\n", find_indexF(str, sub));
    printf("Last occurrence index: %d\n", find_indexL(str, sub));
    return 0;
}
```
92. Check if a string starts or ends with another string
```
#include <stdio.h>
#include <string.h>

int str_start(const char *str1, const char *str2) {
    while(*str2) {
        if(*str1++ != *str2++) return 0;
    }
    return 1;
}

int str_end(const char *str1, const char *str2) {
    int len1 = strlen(str1), len2 = strlen(str2);
    if(len2 > len1) return 0;
    str1 += len1 - len2;
    while(*str2) {
        if(*str1++ != *str2++) return 0;
    }
    return 1;
}

int main() {
    char str1[100], str2[50];
    printf("Enter main string: "); fgets(str1,sizeof(str1),stdin); str1[strcspn(str1,"\n")]=0;
    printf("Enter substring: "); fgets(str2,sizeof(str2),stdin); str2[strcspn(str2,"\n")]=0;

    printf("Starts with: %d\n", str_start(str1,str2));
    printf("Ends with: %d\n", str_end(str1,str2));
    return 0;
}
```
93. Replace all occurrences of "Bangalore" with "Bengaluru"
```
#include <stdio.h>
#include <string.h>

void replaceWord(char *str, const char *oldW, const char *newW) {
    char buffer[1000]; buffer[0] = '\0';
    char *pos = str;
    int lenOld = strlen(oldW), lenNew = strlen(newW);

    while((pos = strstr(pos, oldW))) {
        strncat(buffer, str, pos - str);
        strcat(buffer, newW);
        pos += lenOld;
        str = pos;
    }
    strcat(buffer, str);
    strcpy(str, buffer);
}

int main() {
    char str[1000];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;

    replaceWord(str, "Bangalore", "Bengaluru");
    printf("Result: %s\n", str);
    return 0;
}
```
94. Count occurrences of a word
```
#include <stdio.h>
#include <string.h>

int countWord(char *str, const char *word) {
    int count = 0;
    char *pos = str;
    int len = strlen(word);
    while((pos = strstr(pos, word))) {
        count++;
        pos += len;
    }
    return count;
}

int main() {
    char str[1000], word[50];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    printf("Enter word to count: "); scanf("%s", word);

    printf("Occurrences: %d\n", countWord(str, word));
    return 0;
}
```
95. Remove common characters from two strings
```
#include <stdio.h>
#include <string.h>

void removeCommon(char *s1, char *s2) {
    int hash[256] = {0};
    for(int i=0; s1[i]; i++) hash[(unsigned char)s1[i]]++;
    for(int i=0; s2[i]; i++) if(hash[(unsigned char)s2[i]]) hash[(unsigned char)s2[i]] = 0;
    
    int j=0;
    for(int i=0; s1[i]; i++) if(hash[(unsigned char)s1[i]]) s1[j++] = s1[i];
    s1[j] = '\0';
    j=0;
    for(int i=0; s2[i]; i++) if(hash[(unsigned char)s2[i]] == 0) s2[j++] = s2[i];
    s2[j] = '\0';
}

int main() {
    char s1[100], s2[100];
    printf("Enter first string: "); fgets(s1,sizeof(s1),stdin); s1[strcspn(s1,"\n")]=0;
    printf("Enter second string: "); fgets(s2,sizeof(s2),stdin); s2[strcspn(s2,"\n")]=0;

    removeCommon(s1, s2);
    printf("Resultant strings:\n%s\n%s\n", s1, s2);
    return 0;
}
```
97. Recursive function to count vowels
```
#include <stdio.h>
#include <ctype.h>

int countVowels(char *str, int i) {
    if(str[i]=='\0') return 0;
    char c = tolower(str[i]);
    return (c=='a'||c=='e'||c=='i'||c=='o'||c=='u') + countVowels(str,i+1);
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Number of vowels: %d\n", countVowels(str,0));
}
```
98. Recursive replace character
```
#include <stdio.h>

void replaceChar(char *str, char oldC, char newC, int i) {
    if(str[i]=='\0') return;
    if(str[i]==oldC) str[i]=newC;
    replaceChar(str, oldC, newC, i+1);
}

int main() {
    char str[100]; char oldC, newC;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter old and new char: "); scanf(" %c %c",&oldC,&newC);
    replaceChar(str, oldC, newC, 0);
    printf("Result: %s\n", str);
}
```
99. Recursive reverse string
```
#include <stdio.h>
#include <string.h>

void reverseString(char *str, int start, int end) {
    if(start >= end) return;
    char temp = str[start]; str[start]=str[end]; str[end]=temp;
    reverseString(str,start+1,end-1);
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    reverseString(str,0,strlen(str)-1);
    printf("Reversed: %s\n", str);
}
```
100 & 101. Recursive first and last occurrence of a character
```
#include <stdio.h>
#include <string.h>

int firstOccur(char *str, char c, int i) {
    if(str[i]=='\0') return -1;
    if(str[i]==c) return i;
    return firstOccur(str,c,i+1);
}

int lastOccur(char *str, char c, int i) {
    if(str[i]=='\0') return -1;
    int rest = lastOccur(str,c,i+1);
    if(rest != -1) return rest;
    if(str[i]==c) return i;
    return -1;
}

int main() {
    char str[100], c;
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    printf("Enter character: "); scanf(" %c",&c);
    printf("First occurrence: %d\n", firstOccur(str,c,0));
    printf("Last occurrence: %d\n", lastOccur(str,c,0));
}
```
102. Recursive palindrome check
```
#include <stdio.h>
#include <string.h>

int isPalindrome(char *str, int start, int end) {
    if(start >= end) return 1;
    if(str[start] != str[end]) return 0;
    return isPalindrome(str, start+1, end-1);
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    printf("%d\n", isPalindrome(str,0,strlen(str)-1));
}
```
103. Palindrome ignoring spaces, punctuation, case
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>

int isPalindromeChar(char *str, int start, int end) {
    while(start<end && !isalnum(str[start])) start++;
    while(start<end && !isalnum(str[end])) end--;
    if(start>=end) return 1;
    if(tolower(str[start]) != tolower(str[end])) return 0;
    return isPalindromeChar(str, start+1, end-1);
}

int main() {
    char str[200];
    printf("Enter string: "); fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    printf("%d\n", isPalindromeChar(str,0,strlen(str)-1));
}
```
104. Recursive function to convert string of numbers to an integer
```
#include <stdio.h>

int strToInt(char *str, int n) {
    if(n == 0) return 0;
    return strToInt(str, n-1)*10 + (str[n-1]-'0');
}

int main() {
    char str[100];
    printf("Enter number string: "); scanf("%s", str);
    int len = 0;
    while(str[len]) len++;
    int num = strToInt(str, len);
    printf("Integer: %d\n", num);
}
```
105. Convert string to uppercase
```
#include <stdio.h>
#include <ctype.h>

void toUpperCase(char *str) {
    while(*str) { *str = toupper(*str); str++; }
}

int main() {
    char str[100];
    printf("Enter string: "); fgets(str,sizeof(str),stdin);
    toUpperCase(str);
    printf("Uppercase: %s\n", str);
}
```
106. Case-insensitive string comparison
```
#include <stdio.h>
#include <ctype.h>

int strcmpIgnoreCase(char *s1, char *s2) {
    while(*s1 && *s2) {
        if(tolower(*s1) != tolower(*s2)) return tolower(*s1)-tolower(*s2);
        s1++; s2++;
    }
    return *s1 - *s2;
}

int main() {
    char s1[100], s2[100];
    printf("Enter two strings: "); fgets(s1,sizeof(s1),stdin); fgets(s2,sizeof(s2),stdin);
    s1[strcspn(s1,"\n")]=0; s2[strcspn(s2,"\n")]=0;
    printf("Result: %d\n", strcmpIgnoreCase(s1,s2));
}
```
107. Remove newline character from fgets
```
fgets(str, sizeof(str), stdin);
str[strcspn(str, "\n")] = 0;  
```
Trim leading and trailing blanks
```
#include <stdio.h>
#include <string.h>
#include <ctype.h>

void trim(char *str) {
    int start=0, end=strlen(str)-1;
    while(isspace(str[start])) start++;
    while(end>=start && isspace(str[end])) end--;
    int j=0;
    for(int i=start;i<=end;i++) str[j++]=str[i];
    str[j]='\0';
}

int main() {
    char str[100];
    fgets(str,sizeof(str),stdin);
    str[strcspn(str,"\n")]=0;
    trim(str);
    printf("Trimmed: '%s'\n", str);
}
```
108. Sort characters in a string
```
#include <stdio.h>
#include <string.h>

void sortString(char *str) {
    int len = strlen(str);
    for(int i=0;i<len-1;i++) {
        for(int j=0;j<len-i-1;j++) {
            if(str[j] > str[j+1]) { char temp=str[j]; str[j]=str[j+1]; str[j+1]=temp; }
        }
    }
}

int main() {
    char str[100];
    fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    sortString(str);
    printf("Sorted string: %s\n", str);
}
```

Abbreviate input text (e.g., WHO)
```
#include <stdio.h>
#include <ctype.h>

void abbreviate(char *str) {
    for(int i=0; str[i]; i++) {
        if(i==0 || str[i-1]==' ') putchar(toupper(str[i]));
    }
    printf("\n");
}

int main() {
    char str[100];
    fgets(str,sizeof(str),stdin);
    abbreviate(str);
}
```
109. Extract substring
```
#include <stdio.h>
#include <string.h>

void substring(char *src, int start, int n, char *dest) {
    int i; 
    for(i=0; i<n && src[start+i]; i++) dest[i]=src[start+i];
    dest[i]='\0';
}

int main() {
    char str[100], sub[100];
    fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    int start, n; scanf("%d %d",&start,&n);
    substring(str, start, n, sub);
    printf("Substring: %s\n", sub);
}
```
110. Replace multiple spaces by single space
```
#include <stdio.h>

void removeExtraSpaces(char *str) {
    int i=0, j=0;
    int space=0;
    while(str[i]) {
        if(str[i]!=' ') { str[j++]=str[i]; space=0; }
        else if(space==0) { str[j++]=str[i]; space=1; }
        i++;
    }
    str[j]='\0';
}

int main() {
    char str[200];
    fgets(str,sizeof(str),stdin);
    removeExtraSpaces(str);
    printf("%s\n", str);
}
```
111. Pointer versions of library functions

```
// Example: strlen using pointer
int my_strlen(char *str) {
    char *p=str; while(*p)p++; return p-str;
}

// strncmp using pointers
int my_strncmp(char *s1, char *s2, int n) {
    while(n-- && *s1 && *s2) { if(*s1!=*s2) return *s1-*s2; s1++; s2++; }
    return 0;
}


void my_strncat(char *dest, char *src, int n) {
    while(*dest) dest++;
    while(n-- && *src) *dest++=*src++;
    *dest='\0';
}
```
112. strrstr() last occurrence of substring
```
#include <string.h>

char* strrstr(char *haystack, char *needle) {
    char *res = NULL;
    char *p = haystack;
    int len = strlen(needle);
    while((p = strstr(p, needle))) { res = p; p++; }
    return res;
}
```
113. Index of first and last occurrence of substring
```
int find_indexF(char *str, char *sub) {
    char *p=strstr(str,sub);
    return p ? (p-str) : -1;
}

int find_indexL(char *str, char *sub) {
    char *res=NULL, *p=str;
    while((p=strstr(p,sub))) { res=p; p++; }
    return res ? (res-str) : -1;
}
```
114. Check if substring is at start or end
```
int str_start(const char *str1, const char *str2) {
    while(*str2) if(*str1++!=*str2++) return 0; return 1;
}

int str_end(const char *str1, const char *str2) {
    int len1=strlen(str1), len2=strlen(str2);
    if(len2>len1) 
    return 0; 
    str1+=len1-len2;
    while(*str2) if(*str1++!=*str2++) return 0; return 1;
}
```
115. Replace all occurrences of "Bangalore" with "Bengaluru"
```
#include <stdio.h>
#include <string.h>

void replaceWord(char *str, const char *oldW, const char *newW) {
    char buffer[1024]; buffer[0]='\0';
    char *pos = str;
    while((pos = strstr(pos, oldW))) {
        strncat(buffer, str, pos-str);
        strcat(buffer, newW);
        pos += strlen(oldW);
        str = pos;
    }
    strcat(buffer, str);
    strcpy(str, buffer);
}

int main() {
    char str[1024];
    fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    replaceWord(str, "Bangalore", "Bengaluru");
    printf("%s\n", str);
}
```
116. Count occurrences of a particular word
```
#include <stdio.h>
#include <string.h>

int countWord(char *str, char *word) {
    int count=0; char *p=str;
    while((p=strstr(p,word))) { count++; p+=strlen(word); }
    return count;
}

int main() {
    char str[1024], word[100];
    fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    scanf("%s", word);
    printf("Occurrences: %d\n", countWord(str, word));
}
```
117. Remove all common characters from two strings
```
#include <stdio.h>
#include <string.h>

void removeCommon(char *s1, char *s2) {
    int hash[256]={0};
    for(int i=0;s2[i];i++) hash[(unsigned char)s2[i]]++;
    int i,j=0;
    char temp[256];
    for(i=0;s1[i];i++) if(!hash[(unsigned char)s1[i]]) temp[j++]=s1[i];
    temp[j]='\0'; strcpy(s1,temp);
    
    memset(hash,0,sizeof(hash));
    for(i=0;s1[i];i++) hash[(unsigned char)s1[i]]++;
    j=0;
    for(i=0;s2[i];i++) if(!hash[(unsigned char)s2[i]]) temp[j++]=s2[i];
    temp[j]='\0'; strcpy(s2,temp);
}

int main() {
    char str1[100], str2[100];
    fgets(str1,sizeof(str1),stdin); fgets(str2,sizeof(str2),stdin);
    str1[strcspn(str1,"\n")]=0; str2[strcspn(str2,"\n")]=0;
    removeCommon(str1,str2);
    printf("Resultant Strings:\n%s\n%s\n", str1,str2);
}
```
118. Recursive count of vowels
```
#include <stdio.h>
#include <ctype.h>

int countVowels(char *str) {
    if(!*str) return 0;
    char c=tolower(*str);
    return ((c=='a'||c=='e'||c=='i'||c=='o'||c=='u') ? 1:0) + countVowels(str+1);
}

int main() {
    char str[100]; fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    printf("Vowels: %d\n", countVowels(str));
}
```
119. Recursive replace character
```
void replaceChar(char *str, char oldC, char newC) {
    if(!*str) return;
    if(*str==oldC) *str=newC;
    replaceChar(str+1, oldC, newC);
}
```
120. Recursive string reverse
```
#include <stdio.h>
#include <string.h>

void reverseStr(char *str, int start, int end) {
    if(start>=end) return;
    char temp=str[start]; str[start]=str[end]; str[end]=temp;
    reverseStr(str,start+1,end-1);
}

int main() {
    char str[100]; fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    reverseStr(str,0,strlen(str)-1);
    printf("Reversed: %s\n", str);
}
```
121. Recursive index of first occurrence
```
int firstIndex(char *str, char ch, int idx) {
    if(!str[idx])
     return -1;
    return (str[idx]==ch)? idx : firstIndex(str,ch,idx+1);
}
```
122. Recursive index of last occurrence
```
int lastIndex(char *str, char ch, int idx) {
    if(!str[idx]) return -1;
    int res = lastIndex(str,ch,idx+1);
    return (res==-1 && str[idx]==ch) ? idx : res;
}
```
123. Recursive palindrome check
```
int isPalindrome(char *str, int start, int end) {
    if(start>=end) return 1;
    if(str[start]!=str[end]) return 0;
    return isPalindrome(str,start+1,end-1);
}
```
124. Palindrome ignoring spaces, punctuations, case
```
#include <ctype.h>

int isPalindromeSmart(char *str, int start, int end) {
    while(start<end && !isalnum(str[start])) start++;
    while(end>start && !isalnum(str[end])) end--;
    if(start>=end) return 1;
    if(tolower(str[start])!=tolower(str[end])) return 0;
    return isPalindromeSmart(str,start+1,end-1);
}

125. Recursive string-to-integer
int strToIntRec(char *str, int n) {
    if(n==0) return 0;
    return strToIntRec(str,n-1)*10 + (str[n-1]-'0');
}
```
126. Recursive permutations of a string
```
#include <stdio.h>
#include <string.h>

void swap(char *x,char *y){char temp=*x;*x=*y;*y=temp;}

void permute(char *str,int l,int r){
    if(l==r) printf("%s\n", str);
    else{
        for(int i=l;i<=r;i++){
            swap(&str[l],&str[i]);
            permute(str,l+1,r);
            swap(&str[l],&str[i]);
        }
    }
}

int main(){
    char str[100];
    fgets(str,sizeof(str),stdin); str[strcspn(str,"\n")]=0;
    permute(str,0,strlen(str)-1);
}
```

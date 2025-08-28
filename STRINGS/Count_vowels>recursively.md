# C Program to Count the Number of Vowels in a String Using Recursion

```c
#include <stdio.h>
#include <ctype.h>
#include <string.h>

int countVowels(char str[], int index) {
    if (str[index] == '\0')
        return 0;
    char ch = tolower(str[index]);
    int count = (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') ? 1 : 0;
    return count + countVowels(str, index + 1);
}

int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);

    int vowels = countVowels(str, 0);
    printf("Number of vowels in the string: %d\n", vowels);

    return 0;
}

OUTPUT:
Enter a string: education
Number of vowels in the string: 5

Enter a string: hello
Number of vowels in the string: 2
